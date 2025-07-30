---
demo:
  title: 'Demostración: Generación de documentación de código insertado mediante GitHub Copilot Chat'
  module: 'Module 2: Generate documentation using GitHub Copilot tools'
---

# Demostración: Generación de documentación de código insertado mediante GitHub Copilot Chat

## Instrucciones

Las actividades de demostración están diseñadas para un entorno que incluye los siguientes recursos:

- Visual Studio Code.
- Extensión del kit de desarrollo de C# para Visual Studio Code.
- Las extensiones de GitHub Copilot y GitHub Copilot Chat para Visual Studio Code. Se requiere una cuenta de GitHub con una suscripción activa para GitHub Copilot.
- Proyectos de código de ejemplo creados con C#.

**NOTA**: Se recomienda que los instructores consideren usar su propia cuenta de GitHub y la suscripción a GitHub Copilot para las demostraciones. Esto te permitirá controlar y personalizar el entorno de desarrollo. También harás que sea más fácil ajustar las demostraciones para adaptarlas a las necesidades de tus aulas.

**IMPORTANTE**: Si decides ejecutar las demostraciones en el entorno de laboratorio hospedado en lugar de en el equipo instructor, puedes descomprimir las aplicaciones de ejemplo en el entorno hospedado. Tendrás que configurar las extensiones de GitHub Copilot en el entorno hospedado para poder ejecutar las demostraciones. Es posible que el entorno hospedado sea más lento que el entorno local, por lo que es posible que tengas que ajustar el ritmo de las demostraciones según proceda.

### Presentación de la demostración

Documentar el código es un aspecto importante del proceso de desarrollo de software. La documentación insertada (comentarios de código) ayuda a los desarrolladores a comprender el código base, su propósito y cómo usarlo.

El chat de GitHub Copilot puede ayudarle a documentar el código de forma rápida y precisa. Tiene algunas opciones para generar documentación insertada mediante Chat de GitHub Copilot:

- Construya su propio símbolo del lenguaje natural que se puede solicitar para generar documentación específica.
- Use el comando `/doc` durante una sesión de chat en línea para generar comentarios para el código seleccionado.
- Use el **Generar documentos** acción inteligente para generar comentarios para el código seleccionado.

Documentar correctamente el código crea un código base más legible y fácil de mantener que sea más fácil de entender y con el que puedan trabajar otros desarrolladores.

### Generación de documentación de código insertado mediante la vista Chat

En esta demostración, usarás GitHub Copilot Chat para generar la documentación del código insertado para el proyecto `APL2007M2Sample1`.

Completa los siguientes pasos para usar esta sección de la demostración:

1. Asegúrese de tener abierto el proyecto `APL2007M2Sample1` en Visual Studio Code.

1. Abra el archivo `MainWindow.xaml.cs` .

1. Seleccione todo el código a partir de la declaración de espacio de nombres hasta el final del archivo.

1. Abra la vista Chat.

1. Para ver cómo el Chat de GitHub Copilot documentaría el código seleccionado, escriba la indicación siguiente:

    ```output
    @workspace #selection generate inline code documentation for the selected code
    ```

1. Dedique un minuto a revisar la documentación de código sugerida.

    La respuesta generada debe tener un aspecto similar al ejemplo de código siguiente:

    ```csharp

    namespace ParallelAsyncExample
    {
        public partial class MainWindow : Window
        {
            // HttpClient instance with a maximum response content buffer size of 1,000,000 bytes
            private readonly HttpClient _client = new HttpClient { MaxResponseContentBufferSize = 1_000_000 };
            // List of URLs to download content from
            private readonly IEnumerable<string> _urlList = new string[]
            {
                "https://docs.microsoft.com",
                "https://docs.microsoft.com/azure",
                "https://docs.microsoft.com/powershell",
                "https://docs.microsoft.com/dotnet",
                "https://docs.microsoft.com/aspnet/core",
                "https://docs.microsoft.com/windows",
                "https://docs.microsoft.com/office",
                "https://docs.microsoft.com/enterprise-mobility-security",
                "https://docs.microsoft.com/visualstudio",
                "https://docs.microsoft.com/microsoft-365",
                "https://docs.microsoft.com/sql",
                "https://docs.microsoft.com/dynamics365",
                "https://docs.microsoft.com/surface",
                "https://docs.microsoft.com/xamarin",
                "https://docs.microsoft.com/azure/devops",
                "https://docs.microsoft.com/system-center",
                "https://docs.microsoft.com/graph",
                "https://docs.microsoft.com/education",
                "https://docs.microsoft.com/gaming"
            };
            // Event handler for the start button click event
            private void OnStartButtonClick(object sender, RoutedEventArgs e)
            {
                // Disable the start button and clear the results text box
                _startButton.IsEnabled = false;
                _resultsTextBox.Clear();
                // Start the asynchronous operation to sum page sizes
                Task.Run(() => StartSumPageSizesAsync());
            }
            // Starts the asynchronous operation to sum page sizes
            private async Task StartSumPageSizesAsync()
            {
                // Perform the main download operation
                await SumPageSizesAsync();
                // Update the UI to re-enable the start button and indicate that control has returned
                await Dispatcher.BeginInvoke(() =>
                {
                    _resultsTextBox.Text += $"\nControl returned to {nameof(OnStartButtonClick)}.";
                    _startButton.IsEnabled = true;
                });
            }
            // Asynchronously sums the sizes of the pages from the URLs
            private async Task SumPageSizesAsync()
            {
                // Start a stopwatch to measure elapsed time
                var stopwatch = Stopwatch.StartNew();
                // Create tasks to download content from each URL
                IEnumerable<Task<int>> downloadTasksQuery =
                    from url in _urlList
                    select ProcessUrlAsync(url, _client);
                // Convert the sequence of tasks into an array
                Task<int>[] downloadTasks = downloadTasksQuery.ToArray();
                // Wait for all tasks to complete and sum the lengths of the downloaded content
                int[] lengths = await Task.WhenAll(downloadTasks);
                int total = lengths.Sum();
                // Update the UI with the total bytes and elapsed time
                await Dispatcher.BeginInvoke(() =>
                {
                    stopwatch.Stop();
                    _resultsTextBox.Text += $"\nTotal bytes returned:  {total:#,#}";
                    _resultsTextBox.Text += $"\nElapsed time:          {stopwatch.Elapsed}\n";
                });
            }
            // Asynchronously processes a URL by downloading its content and returning the length of the content
            private async Task<int> ProcessUrlAsync(string url, HttpClient client)
            {
                try
                {
                    // Download the content of the URL
                    byte[] byteArray = await client.GetByteArrayAsync(url);
                    // Update the UI with the URL and content length
                    await DisplayResultsAsync(url, byteArray);
                    // Return the length of the downloaded content
                    return byteArray.Length;
                }
                catch (HttpRequestException e)
                {
                    // Handle HTTP request exceptions by updating the UI with an error message
                    await Dispatcher.BeginInvoke(() =>
                    {
                        _resultsTextBox.Text += $"{url,-60} {"Error",-10}\n";
                        _resultsTextBox.Text += $"Exception: {e.Message}\n";
                    });
                    // Return 0 to indicate failure
                    return 0;
                }
            }
            // Updates the UI with the URL and the length of the downloaded content
            private Task DisplayResultsAsync(string url, byte[] content) =>
                Dispatcher.BeginInvoke(() =>
                    _resultsTextBox.Text += $"{url,-60} {content.Length,10:#,#}\n")
                          .Task;
            // Disposes of the HttpClient instance when the window is closed to free up resources
            protected override void OnClosed(EventArgs e) => _client.Dispose();
        }
    }

    ```

    La respuesta incluye comentarios de código sugeridos y *una parte* del código asociado. Es posible que se omita parte del código para mayor brevedad. Puede mover manualmente los comentarios de código al archivo de código real.

    El chat insertado proporciona un enfoque más directo para agregar comentarios al código.

### Generación de documentación de código insertado mediante chat insertado

1. Desplácese a la parte superior del archivo `MainWindow.xaml.cs`.

1. Seleccione el método `OnStartButtonClick`.

1. Para abrir un chat insertado, presiona **Ctrl+I**.

1. Para generar documentación insertada para el método `OnStartButtonClick`, escriba la siguiente indicación:

    ```output
    /doc
    ```

1. Dedique un minuto a revisar la documentación de código generada.

    Observe que la documentación sugerida para el método `OnStartButtonClick` incluye un resumen y descripciones de los dos parámetros. Cuando un método incluye un valor devuelto, también se incluye una descripción de ese valor.

    > [!IMPORTANT]
    > Revise siempre las actualizaciones sugeridas de GitHub Copilot antes de aceptarlas. Si detecta un problema en una actualización de código sugerida, puede descartar la actualización o intentar corregir el problema antes de aceptarla.

1. Para descartar la actualización sugerida, seleccione **Descartar**.

    En la sección siguiente, generará documentación para todos los métodos a la vez.

### Generación de documentación de código insertado mediante la acción inteligente **Generar documentos**

La acción inteligente **Generar documentos** es otra manera de generar documentación de código insertada. Puede usar esta acción inteligente para generar comentarios que describan el código seleccionado.

Completa los siguientes pasos para usar esta sección de la demostración:

1. En el editor de Visual Studio Code, seleccione todos los métodos *dentro* de la clase `MainWindow`.

1. Haga clic con el botón derecho en el código seleccionado, elija **Copilot** y, a continuación, seleccione **Generar documentos**.

    Espere a que se genere la documentación.

1. Revise los cambios sugeridos.

    > [!IMPORTANT]
    > Si encuentra problemas en la documentación generada, modifique los cambios sugeridos antes de continuar.

1. Seleccione **Aceptar**.

    Cada uno de los métodos de la clase `MainWindow` ahora incluye comentarios generados.

### Resumen

En esta demostración, has usado GitHub Copilot Chat para generar documentación del código insertado para la aplicación `APL2007M2Sample1`. Ha aprendido a generar documentación de código insertada mediante la vista Chat, el chat insertado y la acción inteligente **Generar documentos**. Al generar comentarios de código, puede crear un código base más legible y fácil de mantener que sea más fácil de entender y con el que puedan trabajar otros desarrolladores. La documentación de código insertada es una parte esencial del desarrollo de software que ayuda a los desarrolladores a comprender el código base, su propósito y cómo usarlo.

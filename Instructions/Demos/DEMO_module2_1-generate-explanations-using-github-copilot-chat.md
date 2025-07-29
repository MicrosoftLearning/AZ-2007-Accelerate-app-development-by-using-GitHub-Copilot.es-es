---
demo:
  title: 'Demostración: Generación de explicaciones de código mediante GitHub Copilot Chat'
  module: 'Module 2: Generate documentation using GitHub Copilot tools'
---

# Demostración: Generación de explicaciones de código mediante GitHub Copilot Chat

## Instrucciones

Las actividades de demostración están diseñadas para un entorno que incluye los siguientes recursos:

- Visual Studio Code.
- Extensión del kit de desarrollo de C# para Visual Studio Code.
- Las extensiones de GitHub Copilot y GitHub Copilot Chat para Visual Studio Code. Se requiere una cuenta de GitHub con una suscripción activa para GitHub Copilot.
- Proyectos de código de ejemplo creados con C#.

**NOTA**: Se recomienda que los instructores consideren usar su propia cuenta de GitHub y la suscripción a GitHub Copilot para las demostraciones. Esto te permitirá controlar y personalizar el entorno de desarrollo. También harás que sea más fácil ajustar las demostraciones para adaptarlas a las necesidades de tus aulas.

**IMPORTANTE**: Si decides ejecutar las demostraciones en el entorno de laboratorio hospedado en lugar de en el equipo instructor, puedes descomprimir las aplicaciones de ejemplo en el entorno hospedado. Tendrás que configurar las extensiones de GitHub Copilot en el entorno hospedado para poder ejecutar las demostraciones. Es posible que el entorno hospedado sea más lento que el entorno local, por lo que es posible que tengas que ajustar el ritmo de las demostraciones según proceda.

### Presentación de la demostración

GitHub Copilot Chat usa asistencia conversacional de IA y comandos inteligentes para ayudarle con las tareas relacionadas con la codificación. Un ejemplo es la capacidad de explicar un código desconocido y complejo.

Puede usar GitHub Copilot Chat para generar explicaciones por varios motivos. Por ejemplo:

- GitHub Copilot Chat puede explicarle toda un área de trabajo o archivos de proyecto específicos cuando se une a un proyecto existente.
- GitHub Copilot Chat puede explicar líneas de código específicas o secciones cuando el código es complejo o difícil de entender.
- GitHub Copilot Chat puede explicarle los errores de su código y sugerirle formas de solucionarlos.
- GitHub Copilot Chat puede explicarle cómo agregar características a su proyecto y proporcionarle fragmentos de código que demuestran cómo implementar el nuevo código.

### Explicaciones del área de trabajo y del archivo de proyecto

El chat de GitHub Copilot puede ayudarte a comprender nuevos proyectos o archivos de proyectos específicos. Puede usar una combinación `@workspace`, `/explain` y `#file` en la vista de chat o en una ventana de chat rápido para generar una explicación de su proyecto o de archivos de proyecto específicos.

Completa los siguientes pasos para usar esta sección de la demostración:

1. Abra la carpeta **APL2007M2Sample1** en Visual Studio Code.

    1. Abra Visual Studio Code en el equipo.
    1. En Visual Studio Code, en el menú **Archivo**, seleccione **Abrir archivo**.
    1. Vaya a la carpeta Escritorio de Windows, abra la carpeta **SampleApps** y busque la carpeta **APL2007M2Sample1**.
    1. Seleccione **APL2007M2Sample1** y luego seleccione **Seleccionar carpeta**.

    La vista Visual Studio Code EXPLORER debería mostrar un proyecto de código APL2007M2Sample1 que contenga los siguientes archivos:

    - APL2007M2Sample1.csproj
    - APL2007M2Sample1.sln
    - App.xaml
    - App.xaml.cs
    - MainWindow.xaml
    - MainWindow.xaml.cs

1. En la barra de menús superior de Visual Studio Code, seleccione **Abrir chat**.

    El botón Abrir chat se encuentra en la barra de menús de la parte superior de la ventana de Visual Studio Code, justo a la derecha del cuadro de búsqueda. Muestra un pequeño logotipo de GitHub Copilot.

1. Use el siguiente comando para pedir al chat de Copilot que explique el proyecto de `APL2007M2Sample1`:

    ```plaintext
    @workspace Explain this project
    ```

1. Tómese un minuto para revisar la respuesta en la vista de chat.

    GitHub Copilot Chat genera una explicación del proyecto APL2007M2Sample1 similar a la siguiente respuesta:

    > [!IMPORTANT]
    > GitHub Copilot Chat usa un modelo de IA para generar respuestas. Las respuestas que reciba son similares a las que se muestran en este entrenamiento, pero no son idénticas.

1. En la parte inferior de la vista de chat, observa que el chat de GitHub Copilot ha sugerido una pregunta de seguimiento.

    La respuesta que recibe puede incluir una pregunta de seguimiento diferente.

    GitHub Copilot Chat crea un historial de la conversación de chat. El historial ayuda a GitHub Copilot Chat a comprender sus intereses. A medida que construye un historial de chat, el modelo de IA aprende de sus interacciones y le proporciona preguntas de seguimiento más pertinentes. No se recomienda explorar preguntas de seguimiento "aleatorias".

1. Abra el archivo `MainWindow.xaml.cs` en el editor.

1. Use el siguiente comando para pedir a Copilot que explique el archivo `MainWindow.xaml.cs`:

    ```plaintext
    @workspace /explain #file:MainWindow.xaml.cs
    ```

1. Tómese un minuto para revisar la respuesta en la vista de chat.

    Observe que el chat GitHub Copilot genera una explicación detallada del archivo `MainWindow.xaml.cs`. La explicación incluye información sobre la finalidad, la estructura y los componentes clave del archivo. También puede ver una sección que describe posibles problemas y mejoras.

    Una vez más, el chat de GitHub Copilot sugiere una pregunta de seguimiento.

    > [!IMPORTANT]
    > El chat de GitHub Copilot mantiene un historial de su conversación de chat. A medida que siga haciéndole preguntas, perfeccionará sus respuestas. El contexto de sus preguntas, especialmente en lo que respecta a su proyecto de código, influye en las respuestas posteriores del chat de GitHub Copilot. Esto le ayuda a proporcionar respuestas más precisas y pertinentes. También significa que es probable que la respuesta que reciba para una pregunta concreta varíe en función de su historial de conversaciones.

### Explicaciones de código seleccionadas

Incluso los desarrolladores experimentados se encuentran con código difícil de entender. En lugar de perder tiempo intentando descifrar un código complejo, puede pedir al chat de GitHub Copilot que le proporcione una explicación. La vista de chat, el chat en línea y las acciones inteligentes pueden utilizarse para generar explicaciones de las líneas o secciones de código seleccionadas.

En esta sección de la demostración, usarás la acción inteligente **Explicar** para generar una explicación de las líneas de código seleccionadas.

1. Asegúrese de que tiene el archivo `MainWindow.xaml.cs` abierto en el editor.

1. Desplácese hacia abajo para buscar el método `SumPageSizesAsync()`.

    ```csharp

    private async Task SumPageSizesAsync()
    {
        var stopwatch = Stopwatch.StartNew();
        IEnumerable<Task<int>> downloadTasksQuery =
            from url in _urlList
            select ProcessUrlAsync(url, _client);
        Task<int>[] downloadTasks = downloadTasksQuery.ToArray();
        int[] lengths = Task.WhenAll(downloadTasks);
        int total = lengths.Sum();
        await Dispatcher.BeginInvoke(() =>
        {
            stopwatch.Stop();
    
            _resultsTextBox.Text += $"\nTotal bytes returned:  {total:#,#}";
            _resultsTextBox.Text += $"\nElapsed time:          {stopwatch.Elapsed}\n";
        });
    }

    ```

1. Seleccione las siguientes líneas de código y, a continuación, use la acción inteligente **Explicar** para generar una explicación.

    Para seleccionar la acción inteligente **Explicar**, haga clic con el botón derecho del ratón en las líneas de código seleccionadas, seleccione **Copilot** y, después, seleccione **Explicar** en el menú contextual.

    ```csharp

    IEnumerable<Task<int>> downloadTasksQuery =
        from url in _urlList
        select ProcessUrlAsync(url, _client);
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();

    ```

1. Tómese un minuto para revisar la respuesta en la vista de chat.

1. Observe el nivel de detalle incluido en la explicación.

    GitHub Copilot Chat genera explicaciones detalladas que incluyen información sobre las líneas de código seleccionadas, su finalidad y su funcionamiento. Las respuestas incluyen fragmentos de código y descripciones en lenguaje natural que le ayudarán a comprender el código.

### Explicaciones de errores

La administración de errores es un aspecto esencial del desarrollo de software. Algunos errores son fáciles de detectar y corregir, mientras que otros pueden ser más complicados. Cuando encuentre un error en su código que sea difícil de entender, puede pedir al Chat de GitHub Copilot que le proporcione una explicación. Por ejemplo, puede pedir al chat de GitHub Copilot que le explique por qué una línea de código específica está causando un error.

Completa los siguientes pasos para usar esta sección de la demostración:

1. Asegúrese de que tiene `MainWindow.xaml.cs` abierto en el editor.

1. En el método `SumPageSizesAsync()`, busque la siguiente línea de código:

    ```csharp
    int[] lengths = Task.WhenAll(downloadTasks);
    ```

1. Pase el mouse sobre `downloadTasks` para ver el mensaje de error.

    Los mensajes de error no siempre explican cómo corregir problemas de codificación. Cuando la solución no es obvia, puede pedir a GitHub Copilot Chat para explicar un error y sugerir maneras de corregirla.

1. Selecciona la línea de código que contiene el error y presiona **Ctrl+I** para abrir un chat insertado.

1. Para generar una explicación del error, escriba el siguiente mensaje:

    ```plaintext
    /explain why is the selection causing an error
    ```

1. Tómese un minuto para revisar la respuesta en la vista de chat.

    Observe que la respuesta incluye información sobre el error y las sugerencias para corregirlo. En este caso, el chat de GitHub Copilot explica que la línea `Task.WhenAll(downloadTasks)` está causando un error porque le falta la palabra clave `await`. La respuesta también proporciona un fragmento de código que muestra cómo corregir el error agregando la palabra clave `await` antes de la línea `Task.WhenAll(downloadTasks)`.

1. Use la explicación proporcionada por GitHub Copilot Chat para corregir el error en el código.

    Agregue la palabra clave `await` antes de la línea `Task.WhenAll(downloadTasks)`, como se muestra en el siguiente fragmento de código:

    ```csharp
    int[] lengths = await Task.WhenAll(downloadTasks);
    ```

    Después de realizar este cambio, se debería resolver el error.

### Nuevas explicaciones de características o funcionalidades

GitHub Copilot Chat puede explicarle cómo agregar nuevas características o funcionalidad a su proyecto.

Considere el proyecto APL2007M2Sample1. Su código descarga páginas web y calcula el tamaño total de las páginas descargadas. Supongamos que necesita agregar el control de excepciones a la aplicación. En esta sección de la demostración, usarás GitHub Copilot Chat para explicar cómo administrar excepciones durante el proceso de descarga.

Completa los siguientes pasos para usar esta sección de la demostración:

1. Seleccione las líneas de código que incluyen los métodos `SumPageSizesAsync` y `ProcessUrlAsync`.

1. En la vista de Chat, para que el chat de GitHub Copilot explique cómo controlar las excepciones producidas durante el proceso de descarga, escriba la siguiente pregunta:

    ```plaintext
    @workspace /explain #MainWindow.xaml.cs How can I handle exceptions thrown during the download process?
    ```

1. Tómese un minuto para revisar la respuesta en la vista de chat.

    El chat Copilot genera una respuesta similar a la siguiente explicación:

    La respuesta proporciona una explicación detallada de cómo controlar las excepciones producidas durante el proceso de descarga. También obtendrá un fragmento de código que implementa el código sugerido para el control de excepciones. Puede copiar el fragmento de código o insertarlo en su proyecto de código en la ubicación del cursor.

    En lugar de copiar o insertar el fragmento de código de la vista de chat, el siguiente paso investiga usando el chat insertado para implementar el código de control de excepciones sugerido.

1. Para preguntar al chat insertado cómo implementar el control de excepciones, selecciona el método `ProcessUrlAsync`, presiona **Ctrl+I** y, a continuación, escribe la indicación siguiente:

    ```plaintext
    How can I handle exceptions thrown during the download process?
    ```

1. Tómese un minuto para revisar la respuesta insertada.

1. Para aceptar el código de control de errores propuesto, seleccione **Aceptar**.

    Observe que el bloque propuesto `try-catch` está implementado.

### Resumen

En esta demostración, has usado GitHub Copilot Chat para generar explicaciones sobre líneas de código, errores y nuevas características. El chat de GitHub Copilot ofrece un potente conjunto de características que pueden ayudarle a impulsar rápidamente un nuevo proyecto. Mediante el chat insertada y la vista Chat, podrá obtener ayuda del chat de GitHub Copilot sin salir del entorno de Visual Studio Code. El modelo de IA del chat de GitHub Copilot genera respuestas precisas y útiles que pueden ayudarle a convertirse en un desarrollador más eficiente y eficaz.

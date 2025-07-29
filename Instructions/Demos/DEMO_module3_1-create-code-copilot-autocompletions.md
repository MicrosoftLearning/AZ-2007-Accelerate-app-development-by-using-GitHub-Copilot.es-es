---
demo:
  title: 'Demostración: Creación de código mediante finalizaciones de línea de código'
  module: 'Module 3: Develop code features using GitHub Copilot tools'
---

# Demostración: Creación de código mediante finalizaciones de línea de código

## Instrucciones

Las actividades de demostración están diseñadas para un entorno que incluye los siguientes recursos:

- Visual Studio Code.
- Extensión del kit de desarrollo de C# para Visual Studio Code.
- Las extensiones de GitHub Copilot y GitHub Copilot Chat para Visual Studio Code. Se requiere una cuenta de GitHub con una suscripción activa para GitHub Copilot.
- Proyectos de código de ejemplo creados con C#.

**NOTA**: Se recomienda que los instructores consideren usar su propia cuenta de GitHub y la suscripción a GitHub Copilot para las demostraciones. Esto te permitirá controlar y personalizar el entorno de desarrollo. También harás que sea más fácil ajustar las demostraciones para adaptarlas a las necesidades de tus aulas.

**IMPORTANTE**: Si decides ejecutar las demostraciones en el entorno de laboratorio hospedado en lugar de en el equipo instructor, puedes descomprimir las aplicaciones de ejemplo en el entorno hospedado. Tendrás que configurar las extensiones de GitHub Copilot en el entorno hospedado para poder ejecutar las demostraciones. Es posible que el entorno hospedado sea más lento que el entorno local, por lo que es posible que tengas que ajustar el ritmo de las demostraciones según proceda.

### Presentación de la demostración

GitHub Copilot puede proporcionar sugerencias de finalización de código para numerosos lenguajes de programación y una amplia variedad de marcos, pero funciona especialmente bien para Python, JavaScript, TypeScript, Ruby, Go, C# y C++. Las finalizaciones de línea de código se generan en función del contexto del código que está escribiendo. Puede aceptar, rechazar o aceptar parcialmente las sugerencias proporcionadas por GitHub Copilot.

GitHub Copilot proporciona dos maneras de generar finalizaciones de línea de código:

- **A partir de un comentario**: Puede generar finalizaciones de línea de código escribiendo un comentario que describa el código que desea generar. GitHub Copilot proporciona sugerencias de finalización de código en función del comentario que escriba.

- **De código**: Puede generar finalizaciones de línea de código iniciando una línea de código o presionando Entrar después de una línea de código completada. GitHub Copilot proporciona sugerencias de finalización de código basadas en el código que escribe.

En esta demostración, usarás GitHub Copilot para generar finalizaciones de línea de código en el entorno de Visual Studio Code.

### Creación de una aplicación de consola en el entorno de Visual Studio Code

En esta demostración, crearás una aplicación de consola mediante las herramientas de GitHub Copilot.

Completa los siguientes pasos para usar esta sección de la demostración:

1. Abra una instancia nueva de Visual Studio Code y, a continuación, abra la vista Chat.

    Para abrir la vista Chat, seleccione **Abrir chat** en el Centro de comandos de Visual Studio Code o mediante el método abreviado de teclado **Ctrl+Alt+I**.

1. En la vista Chat, escriba el siguiente símbolo del sistema:

    ```plaintext
    @workspace /new console application named APL2007M3. Use C# LangVersion 12 and NET8.0. Only .cs and .csproj files. Enable ImplicitUsings and Nullable
    ```

1. En la vista Chat, seleccione **Crear área de trabajo**.

    GitHub Copilot usa el mensaje para crear el área de trabajo para una nueva aplicación de consola. La aplicación usa `C#` y `.NET8.0`. El proyecto de código se denomina `APL2007M3` e incluye los archivos `.cs` y `.csproj`. El archivo `APL2007M3.csproj` especifica `LangVersion 12` de C# y habilita `ImplicitUsings` y `Nullable`.

1. En el cuadro de diálogo Seleccionar carpeta, vaya a la carpeta Escritorio, seleccione **Escritorio**, y a continuación, seleccione **Seleccionar como carpeta primaria**.

    Se le pedirá que seleccione una carpeta primaria para el área de trabajo nueva. Seleccionar la carpeta Escritorio es una buena opción para esta demostración. La carpeta Escritorio es fácil de encontrar. Recuerde limpiar cuando complete este entrenamiento.

1. Cuando se le pida que abra el nuevo proyecto, seleccione **Abrir**.

1. En la vista Explorador, seleccione **Program.cs**.

1. Reemplace el contenido del archivo Program.cs por el código siguiente:

    ```csharp

    namespace ReportGenerator
    {
        class QuarterlyIncomeReport
        {
            static void Main(string[] args)
            {
                // create a new instance of the class
                QuarterlyIncomeReport report = new QuarterlyIncomeReport();
                // call the GenerateSalesData method
                // call the QuarterlySalesReport method
            }
            public void QuarterlySalesReport()
            {
                Console.WriteLine("Quarterly Sales Report");
            }
        }    
    }

    ```

Se han completado los requisitos de configuración y ya estás listo para comenzar con la demostración.

### Uso de GitHub Copilot para generar finalizaciones de línea de código a partir de un comentario

GitHub Copilot genera sugerencias de finalización de código basadas en el comentario y en el contexto existente de la aplicación. Puede usar comentarios para describir fragmentos de código, métodos, estructuras de datos y otros elementos de código.

Completa los siguientes pasos para usar esta sección de la demostración:

1. En el archivo **Program.cs**, cree dos líneas de código vacías debajo del método `Main`.

1. Para crear una estructura de datos que se pueda usar para generar datos de prueba, cree el siguiente comentario de código y presione Entrar:

    ```C#
    // public struct SalesData. Include the following fields: date sold, department name, product ID, quantity sold, unit price
    ```

    GitHub Copilot genera una o varias sugerencias de finalización de código basadas en el comentario de código y en cualquier código existente que encuentre en la aplicación.

1. Dedique un minuto a revisar las sugerencias de finalización de código proporcionadas por GitHub Copilot.

    > [!NOTE]
    > Si GitHub Copilot genera sugerencias para un método en lugar de una estructura de datos, escriba **public str** y espere a que se actualice la sugerencia de finalización de código. GitHub Copilot usa la información adicional para mejorar sus sugerencias.

    Observe los tipos de datos usados para declarar los campos de la estructura de datos. GitHub Copilot selecciona los tipos de datos y los nombres de variables en función del código existente y el comentario de código. GitHub Copilot intenta determinar cómo la aplicación usa variables y define los tipos de datos en consecuencia.

    Cuando GitHub Copilot genera más de una sugerencia, puede recorrer las sugerencias seleccionando las flechas izquierda o derecha (`>` o `<`) situadas a la izquierda del botón **Aceptar**. Esto le permite revisar y seleccionar la sugerencia que mejor se adapte a sus necesidades.

    Está bien aceptar una sugerencia de finalización de código que no coincida exactamente con lo que desea. Sin embargo, los cambios necesarios para "corregir" la sugerencia deben estar claros. En este caso, algunos de los tipos de datos no son los que desea, pero puede ajustarlos después de aceptar la acción de autocompletar sugerida.

    Si ninguna de las opciones sugeridas es similar a lo que necesita, hay dos cosas que puede probar. Para abrir una nueva pestaña Editor que contenga una lista de otras sugerencias, presione las teclas **Ctrl** + **Entrar**. Esta combinación de teclas de acceso rápido abre una nueva pestaña que contiene hasta 10 sugerencias más. Cada sugerencia va seguida de un botón que puede usar para aceptarla. La pestaña se cierra automáticamente después de aceptar una sugerencia. La otra opción consiste en presionar la tecla **Esc** para descartar las sugerencias e intentarlo de nuevo. Puede ajustar el comentario de código para proporcionar más contexto con el que GitHub Copilot funcione.

    > [!NOTE]
    > GitHub Copilot puede proponer ocasionalmente una sugerencia en fases. Si esto sucede, puede presionar Entrar para ver las fases adicionales de la sugerencia después de presionar la tecla Tab.

1. Para aceptar una estructura de datos sugerida, presione la tecla Tab o seleccione **Aceptar**.

1. Para modificar los tipos de datos de campo, actualice el código de la siguiente manera:

    ```csharp

    public struct SalesData
    {
        public DateOnly dateSold;
        public string departmentName;
        public int productID;
        public int quantitySold;
        public double unitPrice;
    }

    ```

    Realizar ajustes rápidos en las sugerencias de finalización de código ayuda a garantizar su compilación del código deseado. Es especialmente importante realizar correcciones al principio del proceso de desarrollo cuando todavía es necesario desarrollar partes grandes del código base. Las finalizaciones de código posteriores se basarán en el código que ya ha escrito, por lo que es importante asegurarse de que el código sea lo más preciso posible.

1. Cree dos líneas de código vacías debajo de la estructura de datos `SalesData`.

1. Para crear un método que genere datos de prueba mediante la estructura de datos `SalesData`, escriba el siguiente comentario de código y presione Entrar:

    ```C#
    /* the GenerateSalesData method returns 1000 SalesData records. It assigns random values to each field of the data structure */
    ```

1. Dedique un minuto a revisar las sugerencias de finalización de código proporcionadas por GitHub Copilot.

    Observe que el método `GenerateSalesData` está diseñado para devolver una matriz de objetos `SalesData`. El método genera 1000 registros de datos de prueba, con valores aleatorios asignados a cada campo de la estructura de datos `SalesData`.

    Siempre debe revisar las sugerencias propuestas por GitHub Copilot y GitHub Copilot Chat, incluso si parecen correctas.

    > [!NOTE]
    > Si GitHub Copilot sugiere una sola línea de código en lugar de un método completado `GenerateSalesData`, presiona **Ctrl+Entrar** para abrir la pestaña Sugerencias de GitHub Copilot. Revisa las sugerencias de la nueva pestaña. En el paso siguiente, usa el botón "Aceptar sugerencia n.º" para aceptar la sugerencia. GitHub Copilot presenta sugerencias incrementalmente en ocasiones. Aunque puede aceptar las finalizaciones de código incrementalmente, es mejor usar la pestaña Sugerencias de GitHub Copilot para revisar la sugerencia completa antes de tomar una decisión para aceptar o descartar.

1. Desplácese por las sugerencias de finalización de código y seleccione la mejor coincidencia para los requisitos.

1. Para aceptar la finalización de código, presione la tecla Tab.

    Observe que la sugerencia de finalización de código incluye un error de sintaxis en el código usado para generar el campo `DateSold`. `DateOnly` acepta tres valores enteros que deben aparecer en el orden correcto: **Año**, **Mes**, **Día**.

1. Para especificar un solo año para el código usado para generar el campo `DateSold`, actualice la línea de código de la siguiente manera:

    ```C#
    salesData[i].DateSold = new DateOnly(2023, random.Next(1, 13), random.Next(1, 29));
    ```

1. Si es necesario, ajuste las otras líneas de código para que coincidan con el siguiente fragmento de código:

    ```csharp

    public SalesData[] GenerateSalesData()
    {
        SalesData[] salesData = new SalesData[1000];
        Random random = new Random();
        for (int i = 0; i < salesData.Length; i++)
        {
            salesData[i].dateSold = new DateOnly(2023, random.Next(1, 13), random.Next(1, 29));
            salesData[i].departmentName = "Department " + random.Next(1, 11);
            salesData[i].productID = random.Next(1, 101);
            salesData[i].quantitySold = random.Next(1, 101);
            salesData[i].unitPrice = random.NextDouble() * 100;
        }
        return salesData;
    }

    ```

La capacidad de generar código a partir de comentarios de código es una característica eficaz de GitHub Copilot. Con solo dos comentarios, pudo generar una estructura de datos y un método que genera datos de prueba.

### Uso de GitHub Copilot para generar finalizaciones de línea de código

GitHub Copilot puede generar finalizaciones de línea de código en función del código que escriba. Puede generar finalizaciones de línea de código de dos maneras:

- Empiece a escribir una línea de código y espere a que GitHub Copilot sugiera un autocompletado para la línea de código sin terminar.
- Escriba una línea de código completa, presione la tecla **Entrar** y espere a que GitHub Copilot sugiera una acción de autocompletar para la siguiente línea de código.

> [!NOTE]
> GitHub Copilot genera finalizaciones de código sugeridas en función del código que escriba y el contexto definido por el código dentro de la aplicación. Cuanto más código tenga en la aplicación, suponiendo que sea de buena calidad, más contexto tiene disponible GitHub Copilot. A medida que aumenta el volumen y la calidad del código existente, también aumenta la calidad y confiabilidad de las finalizaciones de línea de código sugeridas por GitHub Copilot. GitHub Copilot es muy bueno al generar finalizaciones de línea de código para tareas y patrones de programación comunes, especialmente cuando es necesario generar una secuencia de componentes relacionados.

En esta parte de la demostración, trabajarás con el método `QuarterlySalesReport`.

Estas son las tareas que debe completar:

- Actualice el constructor de métodos con un parámetro que acepte la colección de objetos `SalesData`.
- Use GitHub Copilot para generar finalizaciones de línea de código que procesan los datos de ventas del informe trimestral.
- Ejecute la aplicación y revise el informe de ventas trimestrales.

Completa los siguientes pasos para usar esta sección de la demostración:

1. Actualice el constructor del método para `QuarterlySalesReport` de la manera siguiente:

    ```C#
    public void QuarterlySalesReport(SalesData[] salesData)
    ```

1. Dedique un minuto a considerar las actualizaciones que necesita implementar.

    El concepto es sencillo. Desea que el código calcule las ventas trimestrales en función de los datos de ventas y, a continuación, escriba un informe. Para ello, el código debe:

    - Recorra en iteración la colección `salesData`.
    - Calcule el valor de cada venta en función de la cantidad vendida y el precio unitario.
    - Use la fecha de venta para determinar a qué trimestre pertenece una venta.
    - Sume las ventas de cada trimestre.
    - Escriba un informe de las ventas por trimestre.

    Una opción consiste en empezar a escribir el código para un bucle `foreach` y, a continuación, ver lo que sugiere GitHub Copilot.

1. En el método `QuarterlySalesReport`, cree una nueva línea de código en la parte superior del bloque de código.

    Debe haber al menos una línea de código en blanco entre la nueva línea de código y la línea de código que contiene `Console.WriteLine()`.

1. Para generar una finalización de línea de código, escriba `foreach (` y espere a que GitHub Copilot sugiera opciones de finalización de línea de código.

1. Revise la finalización del código sugerida por GitHub Copilot.

    La finalización de código sugerida no es lo que quería.

    Aunque GitHub Copilot sugiere un bucle `foreach` que recorre en iteración el `salesData`, no hay análisis ni cálculos dentro del bucle. Cada una de las opciones sugeridas incluye instrucciones `Console.WriteLine` que no quiere o necesita.

1. Dedique un minuto a tener en cuenta por qué GitHub Copilot sugiere `Console.WriteLine` instrucciones.

    Recuerde que GitHub Copilot genera sugerencias de finalización de código en función del contexto del código. En este caso, realmente no tiene mucho código para que GitHub Copilot tenga en cuenta. Y la situación empeora.

    El código que GitHub Copilot ve dentro del método es una instrucción `Console.WriteLine`. Sin ningún otro contexto disponible en el método ni métodos similares en el código base en los que basarse, GitHub Copilot concluye que es posible que *desee* instrucciones `Console.WriteLine` dentro del bucle `foreach`.

    GitHub Copilot funciona mejor cuando el código está limpio y centrado. Si ve comentarios de código superfluos o instrucciones en el código, es posible que quiera quitarlos antes de intentar usar finalizaciones de código de GitHub Copilot.

1. Para limpiar el código antes de dar a GitHub Copilot otro intento, complete los pasos siguientes:

    - Cancele la finalización del código `foreach (` sugerida.
    - Elimine la instrucción `foreach (` parcial que especificó.
    - Elimine la instrucción `Console.WriteLine` del método `QuarterlySalesReport`.

    Ahora debería estar listo para probar GitHub Copilot de nuevo.

1. Asegúrese de que el método `QuarterlySalesReport` tenga un aspecto similar al código siguiente:

    ```C#
    public void QuarterlySalesReport(SalesData[] salesData)
    {


    }
    ```

1. Coloque el cursor en una línea de código en blanco dentro del método `QuarterlySalesReport` y presione Entrar.

    GitHub Copilot puede tardar un momento en generar la finalización del código sugerido.

1. Dedique un minuto a revisar las finalizaciones de código sugeridas.

    > [!NOTE]
    > Aunque GitHub Copilot solo tiene un nombre de método y un parámetro con el que trabajar, puede que sea suficiente para generar sugerencias útiles. Debería ver sugerencias que calculan las ventas por trimestre. Rechazar las sugerencias y volver a intentarlo puede proporcionar resultados diferentes.

    Puede recorrer las sugerencias seleccionando `>` o `<`.

    Observe que la finalización de código sugerida recorre en iteración los datos de ventas y realiza cálculos trimestrales de ventas.

1. Para aceptar la finalización del código sugerida, presione la tecla Tab.

    La finalización del código sugerido calcula y muestra los ingresos trimestrales en función de los datos de ventas.

    ```csharp

    // create a dictionary to store the quarterly sales data
    Dictionary<string, double> quarterlySales = new Dictionary<string, double>();
    // iterate through the sales data
    foreach (SalesData data in salesData)
    {
        // calculate the total sales for each quarter
        string quarter = GetQuarter(data.dateSold.Month);
        double totalSales = data.quantitySold * data.unitPrice;
        if (quarterlySales.ContainsKey(quarter))
        {
            quarterlySales[quarter] += totalSales;
        }
        else
        {
            quarterlySales.Add(quarter, totalSales);
        }
    }
    // display the quarterly sales report
    Console.WriteLine("Quarterly Sales Report");
    Console.WriteLine("----------------------");
    foreach (KeyValuePair<string, double> quarter in quarterlySales)
    {
        Console.WriteLine(entry.Key + ": $" + entry.Value);
    }

    ```

1. Observe que el método `GetQuarter` se usa para determinar el trimestre en función del mes de la venta.

    Este método no se implementa en el código, pero es necesario para que el código se compile y ejecute.

1. Cree dos líneas de código en blanco debajo del método `QuarterlySalesReport`.

1. Observe que GitHub Copilot sugiere una finalización de código para el método `GetQuarter`.

    Con el contexto proporcionado por el método `QuarterlySalesReport`, GitHub Copilot puede generar fácilmente una finalización de código para el método `GetQuarter` que determina el trimestre en función del mes de la venta.

1. Dedique un minuto a revisar la finalización de la línea de código sugerida para el método `GetQuarter`.

1. Para aceptar la finalización del código sugerida, presione la tecla Tab.

    ```csharp

    public string GetQuarter(int month)
    {
        if (month >= 1 && month <= 3)
        {
            return "Q1";
        }
        else if (month >= 4 && month <= 6)
        {
            return "Q2";
        }
        else if (month >= 7 && month <= 9)
        {
            return "Q3";
        }
        else
        {
            return "Q4";
        }
    }

    ```

1. Tenga en cuenta que el método `Main` debe completarse para poder ejecutar el código.

    Puede usar los comentarios del método `Main` para actualizar el código.

1. Coloque el cursor al final del `// call the GenerateSalesData method` comentario de código y presione Entrar.

    GitHub Copilot usa el comentario para proponer una instrucción de llamada para el método.

1. Revise y acepte la finalización del código sugerida por GitHub Copilot.

1. Repita el proceso para el comentario de código de `// call the QuarterlySalesReport method`.

1. El método `Main` debe contener el código siguiente:

    ```csharp

    static void Main(string[] args)
    {
        // create a new instance of the class
        QuarterlyIncomeReport report = new QuarterlyIncomeReport();
        // call the GenerateSalesData method
        SalesData[] salesData = report.GenerateSalesData();
        // call the QuarterlySalesReport method
        report.QuarterlySalesReport(salesData);
    }

    ```

1. Dedique un minuto a revisar el código de la clase `QuarterlyIncomeReport`.

    ```csharp

    namespace ReportGenerator
    {
        class QuarterlyIncomeReport
        {
            static void Main(string[] args)
            {
                // create a new instance of the class
                QuarterlyIncomeReport report = new QuarterlyIncomeReport();
                // call the GenerateSalesData method
                SalesData[] salesData = report.GenerateSalesData();
                // call the QuarterlySalesReport method
                report.QuarterlySalesReport(salesData);
            }
            /* public struct SalesData includes the following fields: date sold, department name, product ID, quantity sold, unit price */
            public struct SalesData
            {
                public DateOnly dateSold;
                public string departmentName;
                public int productID;
                public int quantitySold;
                public double unitPrice;
            }
            /* the GenerateSalesData method returns 1000 SalesData records. It assigns random values to each field of the data structure */
            public SalesData[] GenerateSalesData()
            {
                SalesData[] salesData = new SalesData[1000];
                Random random = new Random();
                for (int i = 0; i < 1000; i++)
                {
                    salesData[i].dateSold = new DateOnly(2023, random.Next(1, 13), random.Next(1, 29));
                    salesData[i].departmentName = "Department " + random.Next(1, 11);
                    salesData[i].productID = random.Next(1, 101);
                    salesData[i].quantitySold = random.Next(1, 101);
                    salesData[i].unitPrice = random.NextDouble() * 100;
                }
                return salesData;
            }
            public void QuarterlySalesReport(SalesData[] salesData)
            {
                // create a dictionary to store the quarterly sales data
                Dictionary<string, double> quarterlySales = new Dictionary<string, double>();
                // iterate through the sales data
                foreach (SalesData data in salesData)
                {
                    // calculate the total sales for each quarter
                    string quarter = GetQuarter(data.dateSold.Month);
                    double totalSales = data.quantitySold * data.unitPrice;
                    if (quarterlySales.ContainsKey(quarter))
                    {
                        quarterlySales[quarter] += totalSales;
                    }
                    else
                    {
                        quarterlySales.Add(quarter, totalSales);
                    }
                }
                // display the quarterly sales report
                Console.WriteLine("Quarterly Sales Report");
                Console.WriteLine("----------------------");
                foreach (KeyValuePair<string, double> quarter in quarterlySales)
                {
                    Console.WriteLine(entry.Key + ": $" + entry.Value);
                }
            }
            public string GetQuarter(int month)
            {
                if (month >= 1 && month <= 3)
                {
                    return "Q1";
                }
                else if (month >= 4 && month <= 6)
                {
                    return "Q2";
                }
                else if (month >= 7 && month <= 9)
                {
                    return "Q3";
                }
                else
                {
                    return "Q4";
                }
            }
        }
    }
    
    ```

    Este código se creó, casi por completo, mediante finalizaciones de línea de código generadas por GitHub Copilot. Sin embargo, es importante revisar las sugerencias de código y se requieren correcciones. Siempre debe revisar las finalizaciones de código sugeridas por GitHub Copilot para asegurarse de que el código cumple sus requisitos.

1. Para revisar la salida del informe, ejecute la aplicación.

    Abra una ventana terminal en Visual Studio Code y escriba el siguiente comando:

    ```bash
    dotnet run
    ```

    La salida debe mostrar el informe de ingresos trimestrales, que muestra el nombre del departamento, el trimestre y los ingresos de cada departamento y trimestre representados en los datos de prueba.

1. Revise la salida en la ventana Terminal.

    Aunque los resultados trimestrales se basan en valores numéricos aleatorios, debería ver un informe con formato similar al siguiente resultado:

    ```output

    Quarterly Sales Report
    ----------------------
    Q3: $635637.5019563352
    Q4: $672247.315297204
    Q2: $667269.194630603
    Q1: $642769.2700531208

    ```

    Todavía hay trabajo necesario para completar la clase `QuarterlyIncomeReport`. En la unidad siguiente, usará GitHub Copilot Chat para ampliar y actualizar la aplicación.

### Resumen

En esta demostración, has usado GitHub Copilot para generar finalizaciones de línea de código en el entorno de Visual Studio Code. Ha usado comentarios de código para generar una estructura de datos y un método que genera datos de prueba. También ha usado finalizaciones de línea de código para generar el código que procesa los datos de ventas de un informe de ingresos trimestral.

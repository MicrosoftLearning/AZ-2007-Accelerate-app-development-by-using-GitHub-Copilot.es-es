---
demo:
  title: 'Demostración: Creación de código con GitHub Copilot Inline Chat'
  module: 'Module 3: Develop code features using GitHub Copilot tools'
---

# Demostración: Creación de código con GitHub Copilot Inline Chat

## Instrucciones

Las actividades de demostración están diseñadas para un entorno que incluye los siguientes recursos:

- Visual Studio Code.
- Extensión del kit de desarrollo de C# para Visual Studio Code.
- Las extensiones de GitHub Copilot y GitHub Copilot Chat para Visual Studio Code. Se requiere una cuenta de GitHub con una suscripción activa para GitHub Copilot.
- Proyectos de código de ejemplo creados con C#.

**NOTA**: Se recomienda que los instructores consideren usar su propia cuenta de GitHub y la suscripción a GitHub Copilot para las demostraciones. Esto te permitirá controlar y personalizar el entorno de desarrollo. También harás que sea más fácil ajustar las demostraciones para adaptarlas a las necesidades de tus aulas.

**IMPORTANTE**: Si decides ejecutar las demostraciones en el entorno de laboratorio hospedado en lugar de en el equipo instructor, puedes descomprimir las aplicaciones de ejemplo en el entorno hospedado. Tendrás que configurar las extensiones de GitHub Copilot en el entorno hospedado para poder ejecutar las demostraciones. Es posible que el entorno hospedado sea más lento que el entorno local, por lo que es posible que tengas que ajustar el ritmo de las demostraciones según proceda.

### Presentación de la demostración

La extensión de Chat de GitHub Copilot para Visual Studio Code incluye tres interfaces de chat:

- La **Vista de chat** proporciona un asistente de IA que está disponible para ayudarle en cualquier momento.
- Se puede usar una ventana de **Chat rápido** para formular una pregunta rápida y, a continuación, volver a lo que estaba haciendo.
- La interfaz de **chat insertado** se abre directamente en el editor para interacciones contextuales mientras está codificando.

La Vista de chat y la ventana Chat rápido habilitan conversaciones interactivas multiturno con la inteligencia artificial. Ambas interfaces proporcionan una manera de formular preguntas, obtener ayuda con un problema de codificación y generar código. Durante una conversación, las respuestas de GitHub Copilot incluyen texto de lenguaje natural, bloques de código y otros elementos. Cuando se proporcionan bloques de código en una respuesta, puede copiarlos o insertarlos directamente en el editor de código.

La interfaz de chat insertado está diseñada para proporcionar ayuda contextual y sugerencias de código mientras está codificando.

En esta demostración, usarás la característica de chat insertada de GitHub Copilot para generar nuevas características de código. La demostración es una continuación del escenario del proyecto de la demostración anterior. Usa la aplicación de ejemplo preparada, `APL2007M3SalesReport-InlineChat`, para iniciar la demostración. Durante la demostración, actualizarás la estructura de datos `SalesData` y el método `GenerateSalesData`. También actualizarás el método `QuarterlySalesReport` para incluir cálculos adicionales y opciones de visualización.

#### Revisar las tareas de codificación y los objetivos del proyecto

Esta demostración se centra en el uso de GitHub Copilot para acelerar las siguientes tareas:

1. Actualizarás la estructura de datos `SalesData` y el método `GenerateSalesData` para generar un ejemplo de datos similares a los datos "reales".

    - dateSold: no se requieren cambios.
    - departmentName: Los valores de cadena deben seleccionarse aleatoriamente en una lista de 8 departamentos. Para cada nombre de departamento, cree una abreviatura de 4 caracteres que se pueda incluir en el productID.
    - productID: cambie de `int` al tipo de datos `string`. Los valores de productID deben tener formato con el patrón "`DDDD-###-SS-CC-MMM`" donde los componentes del id. se definen de la siguiente manera:

        - Un código de 4 caracteres que representa el departamento.
        - Un número de 3 dígitos que representa el producto.
        - Un código de 2 caracteres que representa el tamaño del producto.
        - Un código de 2 caracteres que representa el color del producto.
        - Un código de 3 caracteres que representa el sitio de fabricación (seleccionado aleatoriamente de una lista de 10 sitios de fabricación). Los códigos deben ser un código de país ISO de 2 letras seguido de un dígito (por ejemplo, US1, CA2, MX3, etc.).

    - quantitySold: no se requieren cambios.
    - unitPrice: Aumente el límite inferior del intervalo de precios a 25 y el límite superior a 300.
    - baseCost: Agregue un campo para el costo de fabricación del artículo. Los valores de baseCost deben generarse con el descuento generado aleatoriamente a partir del unitPrice (de 5 a 20 por ciento).
    - volumeDiscount: Agregue un campo para un porcentaje de descuento por volumen. El valor asignado a volumeDiscount debe ser el componente entero del 10 por ciento de la quantitySold (10 % de 19 unidades = 1 % volumeDiscount).
    - Aumente el número de registros generados a 10 000.

1. Actualizarás el método `QuarterlySalesReport` de la siguiente manera:

    1. Al mostrar los resultados de ventas, enumere los resultados en un orden lógico. Por ejemplo, al enumerar las ventas totales por trimestre, los trimestres deben aparecer en orden de Q1 a Q4.
    1. Muestre los valores de moneda mediante la configuración regional.
    1. Incluir los cálculos de beneficios trimestrales y el porcentaje de beneficio
    1. Incluya los cálculos para las ventas trimestrales, los beneficios y el porcentaje de beneficios por departamento.

#### Explicación de tu enfoque para desarrollar indicaciones de GitHub Copilot Chat

La característica de chat en línea de GitHub Copilot usa el mensaje que envía para comprender la tarea o el problema que está intentando resolver. Las indicaciones deben ser específicas y concisas. Las buenas indicaciones producen mejores respuestas.

Cuando desarrolle solicitudes para GitHub Copilot, tenga en cuenta los procedimientos recomendados siguientes:

- Ser concreto y mantener la sencillez: Proporcione mensajes claros y concisos que describan la tarea o el problema que está intentando resolver. Evite el uso de lenguajes complejos o jerga que puedan confundir la inteligencia artificial.
- Usar lenguaje natural: Escriba mensajes en un tono conversacional. Use un lenguaje natural que usaría al hablar con un compañero o un miembro del equipo.
- Desglosar tareas complejas: Si la tarea es compleja, divídala en pasos más pequeños. Proporcione avisos para cada paso para ayudar a GitHub Copilot a generar el código correcto.
- Proporcionar contexto: Incluya información relevante que ayude a GitHub Copilot a comprender la tarea o el problema que está intentando resolver. Incluya detalles sobre los datos, variables o bloques de código que son relevantes para el símbolo del sistema.
- Usar participantes de chat, comandos de barra diagonal y variables de chat: La característica de chat en línea de GitHub Copilot admite participantes de chat, comandos de barra diagonal y variables de chat. Use estas características para interactuar con GitHub Copilot y proporcionar contexto adicional para las solicitudes.

### Generar estructuras de datos mediante el chat insertado

Los proyectos suelen comenzar con las características o parámetros que son fijos o conocidos. La selección de un origen de datos o la creación de datos de ejemplo suele ser un buen punto de partida.

En esta sección de la demostración, usarás estructuras de datos para ayudar a crear datos de ventas simulados. Los datos proporcionan un contexto útil para GitHub Copilot al actualizar el método `QuarterlySalesReport`.

> [!NOTE]
> En un proyecto empresarial real, probablemente usaría datos históricos en lugar de generar datos simulados. En este entrenamiento, la generación de datos simulados ofrece la oportunidad de practicar con las herramientas de GitHub Copilot. No se sugiere la simulación de datos como procedimiento recomendado para proyectos empresariales.

Los objetivos del proyecto indican que debe trabajar en las siguientes estructuras de datos:

- Necesita una lista de 8 nombres de departamento. Cada nombre de departamento debe abreviarse mediante una cadena de 4 caracteres. Elija un sector para su empresa ficticia, como Ropa o Equipo deportivo, y luego haga que GitHub Copilot genere un diccionario de nombres de departamento y códigos de 4 caracteres.
- Necesita una lista de 10 sitios de fabricación. Cada sitio debe representarse mediante un código de 3 caracteres. Los códigos pueden ser un código de país ISO de 2 letras seguido de un dígito (por ejemplo, US1, CA2, MX3, etc.). Haga que GitHub Copilot genere un diccionario de 10 sitios de fabricación mediante 3-4 códigos de país.
- Debe actualizar la estructura de datos `SalesData`. Debe incluir los nuevos campos para: código de departamento, código de sitio de fabricación. También debe cambiar el tipo de datos de productID de `int` a `string`.

Para crear y actualizar la estructura de datos, complete los pasos siguientes:

1. Abra la carpeta del proyecto **APL2007M3SalesReport-InlineChat** en Visual Studio Code.

1. Asegúrese de que la aplicación se ejecuta y genera un informe similar al siguiente resultado:

    ```plaintext
    Quarterly Sales Report
    ----------------------
    Q3: $690095.7142725277
    Q4: $600536.3320750712
    Q2: $678194.7943550209
    Q1: $595963.0477790226
    ```

    Dado que los datos se generan aleatoriamente, los valores numéricos variarán con cada ejecución.

1. Abra el archivo Program.cs.

1. Coloque el cursor en una línea en blanco debajo de la estructura de datos `SalesData`.

1. Para abrir la interfaz de chat insertado, presiona **Ctrl+I** en el teclado.

1. Escriba la siguiente indicación:

    ```output
    I need a public struct ProdDepartments that contains a static string array for 8 clothing industry departments. Create separate string array containing 4-character abbreviations for each department name. The abbreviation must be unique. The department names should represent real department names for the clothing industry.
    ```

    Si tiene una lista específica de nombres de campo, puede proporcionarlos en la indicación. Por ejemplo, se pueden usar los datos reales de la empresa para especificar los nombres de departamento.

1. Revise las sugerencias proporcionadas por GitHub Copilot.

    Siempre que la solicitud esté clara y sea específica, GitHub Copilot debería proporcionar una sugerencia útil. Si la sugerencia no es lo que esperaba, puede rechazarla e intentarlo de nuevo. En este caso, los nombres de los departamentos no son importantes, por lo que probablemente pueda aceptar la sugerencia.

    La estructura de datos debe ser similar al código siguiente:

    ```csharp

    public struct ProdDepartments
    {
        public static string[] DepartmentNames =  ["Men's Clothing", "Women's Clothing", "Children's Clothing", "Accessories", "Footwear", "Outerwear", "Sportswear", "Undergarments"];
        public static string[] DepartmentAbbreviations =  ["MENS", "WOMN", "CHLD", "ACCS", "FOOT", "OUTR", "SPRT", "UNDR" ];
    }

    ```

1. Para aceptar la sugerencia, presione la tecla Tab o seleccione **Aceptar**.

    También puede usar la característica de chat insertado para documentar el nuevo código. Selecciona el código, presiona **Ctrl+I** para abrir el chat insertado, escribe `/doc`, revisa la documentación insertada sugerida y, a continuación, acepta la actualización.

1. Coloque el cursor en una línea en blanco debajo de la estructura de datos `ProdDepartments`.

1. Para abrir la interfaz de chat insertado, presiona **Ctrl+I** en el teclado.

1. Escriba la siguiente indicación:

    ```output
    I need a public struct ManufacturingSites that contains a static string array for 10 manSites. Manufacturing sites should be represented by a 3-character code that includes a 2-letter ISO country code followed by a digit. Use 3 ISO country codes.
    ```

    Si tiene una lista específica de nombres de campo, puede proporcionarlos en la indicación. Por ejemplo, se pueden usar los datos reales de la empresa para especificar los nombres de campo.

1. Revise las sugerencias proporcionadas por GitHub Copilot.

    Las estructuras de datos deben ser similares al código siguiente:

    ```csharp

    public struct ManufacturingSites
    {
        public static string[] manSites = [ "US1", "US2", "US3", "UK1", "UK2", "UK3", "JP1", "JP2", "JP3", "MX1" ];
    }

    ```

1. Para aceptar la sugerencia, presione la tecla Tab o seleccione **Aceptar**.

1. Selecciona la estructura de datos `SalesData` y presiona **Ctrl+I** para abrir la interfaz de chat insertado.

    Debe agregar campos para `baseCost` y `volumeDiscount` a la estructura de datos `SalesData` (un `double` y un `int`). También debe cambiar el tipo de datos para `productID` de `int` a `string`.

1. Escriba lo siguiente:

    ```output
    add double field baseCost and int field volumeDiscount to SalesData. Change productID from int to string.
    ```

    En la práctica, puede ser más fácil realizar estos cambios manualmente. Sin embargo, el uso de GitHub Copilot puede ayudarle a aprender a estructurar las indicaciones para obtener mejores resultados.

1. Revise las sugerencias proporcionadas por GitHub Copilot y seleccione **Aceptar**.

    Las estructuras de datos SalesData actualizadas deben ser similares al código siguiente:

    ```csharp

    public struct SalesData
    {
        public DateOnly dateSold;
        public string departmentName;
        public string productID;
        public int quantitySold;
        public double unitPrice;
        public double baseCost;
        public int volumeDiscount;
    }

    ```

Con las estructuras de datos nuevas y actualizadas, ahora puede trabajar en la actualización del método `GenerateSalesData`.

### Actualizar el método GenerateSalesData mediante el chat insertado

Los objetivos del proyecto indican que necesita actualizar el método `GenerateSalesData` para generar un ejemplo de datos similar a los datos "reales". Ya ha actualizado la estructura de datos `SalesData` para incluir nuevos campos para el código de departamento y el código del sitio de fabricación. También ha cambiado el tipo de datos para `productID` de `int` a `string`. Ahora debe actualizar el método `GenerateSalesData` para generar datos para los campos actualizados.

Debe implementar las siguientes actualizaciones:

- departmentName: Actualice el valor asignado. Asigne un nombre de departamento seleccionado aleatoriamente a partir de la estructura de datos `ProdDepartments`.
- productID: Actualice el valor asignado. Dé formato a productID mediante el patrón "`DDDD-###-SS-CC-MMM`" donde los componentes del id. se definen de la siguiente manera:

    - Un código de 4 caracteres que representa el departamento. Use la abreviatura de la estructura de datos `ProdDepartments` correspondiente al nombre del departamento asignado.
    - Un número de 3 dígitos que representa el producto. El primer dígito debe ser el número de índice del departamento seleccionado aleatoriamente. Los dos dígitos siguientes deben ser un número aleatorio de 1 a 99, pero que incluya 0 al inicio. Por ejemplo, 1 debe tener el formato 01.
    - Un código de 2 caracteres que representa el tamaño del producto. Seleccione aleatoriamente un tamaño de producto de una lista de 5 tamaños: XS, S, M, L, XL.
    - Un código de 2 caracteres que representa el color del producto. Seleccione aleatoriamente un color de producto de una lista de 8 abreviaturas de color de 2 caracteres: BK, BL, GR, RD, YL, OR, WT, GY.
    - un código de 3 caracteres que representa el sitio de fabricación. Seleccione aleatoriamente un sitio de fabricación de la estructura de datos `ManufacturingSites`.

- unitPrice: Aumente el límite inferior del intervalo de precios a 25 y el límite superior a 300. Supongamos que el tamaño y el color no afectan al precio unitario.
- baseCost: Asigne un valor a baseCost que represente los costos de fabricación. Los valores se pueden generar mediante el descuento generado aleatoriamente a partir de unitPrice (de 5 a 20 por ciento). Esto no es realista, pero es aceptable para esta demostración.
- volumeDiscount: Asigne un valor a volumeDiscount que represente un porcentaje de descuento concedido al comprador minorista. El valor asignado a volumeDiscount debe ser el componente entero del 10 por ciento de la quantitySold (10 % de 19 unidades = 1 % volumeDiscount).

Para actualizar el método `GenerateSalesData`, complete los pasos siguientes:

1. Ubique el método `GenerateSalesData` en el archivo Program.cs.

1. Seleccione la línea de código usada para asignar el valor `departmentName`.

1. Para abrir la interfaz de chat insertado, presiona **Ctrl+I** en el teclado.

1. Escriba lo siguiente:

    ```output
    Update the departmentName assignment to randomly select a department name. Use the ProdDepartments data structure. 
    ```

1. Revise las sugerencias proporcionadas por GitHub Copilot y seleccione **Aceptar**.

1. Cree tres líneas de código en blanco después de la asignación`departmentName`.

1. Dedique un minuto a considerar cómo desea construir el valor asignado a `productID`.

    Los valores de productID deben tener el formato "`DDDD-###-SS-CC-MMM`" donde los componentes del id. se definen de la siguiente manera:

    - `DDDD` es un código de 4 caracteres que representa el departamento. Use la abreviatura de la estructura de datos `ProdDepartments` correspondiente al nombre del departamento asignado.
    - `###` tiene 3 caracteres numéricos que representan un producto. El primer dígito es el número de índice del departamento. A continuación se muestra un número aleatorio entre 1 y 99 con un 0 inicial (por ejemplo: "07").
    - `SS` es un código de 2 caracteres que representa el tamaño del producto. Seleccione aleatoriamente un tamaño de producto de una lista de 5 tamaños: XS, S, M, L, XL.
    - `CC` es un código de 2 caracteres que representa el color del producto. Seleccione aleatoriamente un color de producto de una lista de 8 abreviaturas de color de 2 caracteres: BK, BL, GR, RD, YL, OR, WT, GY.
    - `MMM` es un código de 3 caracteres que representa el sitio de fabricación. Seleccione aleatoriamente un sitio de fabricación de la estructura de datos `ManufacturingSites`.

    Esta especificación de formato es demasiado compleja para describirla como una sola indicación. Debe dividirse en pasos más pequeños.

    Vale la pena tener en cuenta que el número de índice del departmentName seleccionado se puede usar para seleccionar el departmentAbbreviation y para calcular el primer dígito del número de producto.

1. Copie las siguientes declaraciones de variable y péguelas en la ubicación de la segunda línea de código en blanco que creó.

    ```csharp

    int indexOfDept = 0;
    string deptAbb = "";
    string firstDigit = "";
    string nextTwoDigits = "";
    string sizeCode = "";
    string colorCode = "";
    string manufacturingSite = "";

    ```

    Debe tener una línea de código en blanco antes y después de las declaraciones de variable.

    Las declaraciones de variables no son necesarias para que el chat en línea genere sugerencias de actualización de código desde un símbolo del sistema, pero ayudan a delimitar GitHub Copilot a una línea de código específica a la que pertenece la actualización.

1. Seleccione la línea de código `int indexOfDept = 0;`, abra el chat insertado y escriba la siguiente indicación:

    ```output
    Assign the array index for departmentName to indexOfDept.
    ```

1. Revise las sugerencias proporcionadas por GitHub Copilot.

    Debería ver una sugerencia que asigne el número de índice de matriz correspondiente al departmentName seleccionado para indexOfDept.

    Si no obtiene la sugerencia esperada, puede seleccionar **Descartar** para rechazar la sugerencia e intentarlo de nuevo. La siguiente indicación proporciona contexto adicional para la asignación:

    ```output
    Create an int named indexOfDept. Assign the array index number corresponding to the selected departmentName to indexOfDept.
    ```

    Esta indicación especifica la creación de una variable de entero denominada `indexOfDept` así como cómo asignar un valor. Puede ejecutar esta indicación sin crear o seleccionar la declaración de variable, pero GitHub Copilot puede perder ocasionalmente su punto de anclaje al abrir el chat insertado sin ningún código seleccionado.

    > [!NOTE]
    > El botón **Alternar cambios** (accesible desde el menú desplegable **Más acciones** a la derecha de los botones **Aceptar** y **Descartar**) se puede usar para mostrar u ocultar el código eliminado por la actualización sugerida. Esto puede ser útil cuando desea ver el código original y la actualización de código sugerida.

1. Para aceptar la sugerencia proporcionada por GitHub Copilot, seleccione **Aceptar**.

1. Seleccione la línea de código `string deptAbb = "";`, abra el chat insertado y escriba la siguiente indicación:

    ```output
    Use indexOfDept to assign a department abbreviation to deptAbb.
    ```

1. Revise las sugerencias proporcionadas por GitHub Copilot.

    Debería ver una sugerencia que asigne el número de índice de matriz correspondiente al departmentName seleccionado para indexOfDept.

1. Para aceptar la sugerencia proporcionada por GitHub Copilot, seleccione **Aceptar**.

1. Seleccione la línea de código `string firstDigit = "";`, abra el chat insertado y escriba la siguiente indicación:

    ```output
    Assign indexOfDept + 1 to firstDigit.
    ```

1. Revise las sugerencias proporcionadas por GitHub Copilot y seleccione **Aceptar**.

1. Seleccione la línea de código `string string nextTwoDigits = ""; = "";`, abra el chat insertado y escriba la siguiente indicación:

    ```output
    Assign a random number 1-99 to nextTwoDigits. Include a leading 0 for numbers less than 10.
    ```

1. Revise las sugerencias proporcionadas por GitHub Copilot y seleccione **Aceptar**.

1. Seleccione la línea de código `string sizeCode = "";`, abra el chat insertado y escriba la siguiente indicación:

    ```output
    From the list {XS, S, M, L, XL}, randomly select a product size and assign it to sizeCode.
    ```

1. Revise las sugerencias proporcionadas por GitHub Copilot y seleccione **Aceptar**.

    En este caso, debería ver una sugerencia que asigne un tamaño de producto seleccionado aleatoriamente a la variable `sizeCode`. GitHub Copilot podría sugerir el uso de una o varias líneas de código para satisfacer este mensaje. En cualquier caso, probablemente sugerirá crear una matriz de cadenas de tamaños de producto y, a continuación, usar `random` para asignar uno de los tamaños a `sizeCode`.

1. Seleccione la línea de código `string colorCode = "";`, abra el chat insertado y escriba la siguiente indicación:

    ```output
    From the list {BK, BL, GR, RD, YL, OR, WT, GY}, randomly select a product color and assign it to colorCode.
    ```

1. Revise las sugerencias proporcionadas por GitHub Copilot y seleccione **Aceptar**.

1. Seleccione la línea de código `string manufacturingSite = "";`, abra el chat insertado y escriba la siguiente indicación:

    ```output
    Assign a randomly selected manufacturing site to manufacturingSite.
    ```

1. Revise las sugerencias proporcionadas por GitHub Copilot y seleccione **Aceptar**.

1. Tómese un minuto para examinar el código.

    Debe tener una serie de líneas de código que asignen valores a las variables usadas para construir el productID. El siguiente paso consiste en construir el valor de productID.

    ```csharp

    int indexOfDept = Array.IndexOf(ProdDepartments.departmentNames, salesData[i].departmentName);
    string deptAbb = ProdDepartments.departmentAbbreviations[indexOfDept];
    string firstDigit = (indexOfDept + 1).ToString();
    string nextTwoDigits = random.Next(1, 100).ToString("D2");
    string sizeCode = new string[] { "XS", "S", "M", "L", "XL" }[random.Next(0, 5)];
    string colorCode = new string[] { "BK", "BL", "GR", "RD", "YL", "OR", "WT", "GY" }[random.Next(0, 8)];
    string manufacturingSite = ManufacturingSites.manufacturingSites[random.Next(0, ManufacturingSites.manufacturingSites.Length)];

    ```

1. Seleccione la línea de código `salesData[i].productID = random.Next(1, 101);`, abra el chat insertado y escriba la siguiente indicación:

    ```output
    Add a "-" to deptAbb, nextTwoDigits, sizeCode, and colorCode. Combine deptAbb, firstDigit, nextTwoDigits, sizeCode, colorCode, and manufacturingSite to create the productID.
    ```

1. Revise las sugerencias proporcionadas por GitHub Copilot y seleccione **Aceptar**.

    Debería ver una sugerencia que construya el valor de productID mediante las variables que asignó anteriormente. La sugerencia debe incluir el código necesario para dar formato al productID como "`DDDD-###-SS-CC-MMM`".

1. Actualice manualmente la asignación `unitPrice` para usar un intervalo de 25 a 300 como se indica a continuación:

    ```csharp
    salesData[i].unitPrice = random.Next(25, 300) + random.NextDouble();
    ```

1. Cree una línea en blanco después de la asignación `unitPrice`.

1. Acepte la finalización de la línea de código que aparece:

    GitHub Copilot debe proporcionar una sugerencia que asigne un valor a `baseCost` que parezca similar a la siguiente línea de código:

    ```csharp
    salesData[i].baseCost = random.Next(10, 100) + random.NextDouble();
    ```

1. Seleccione la línea de código que se usa para asignar un valor a `salesData[i].baseCost`, abra el chat en línea y escriba el siguiente símbolo del sistema:

    ```output
    Discount the unitPrice by a random percentage between 5 and 20. Assign the result to baseCost.
    ```

1. Revise las sugerencias proporcionadas por GitHub Copilot y seleccione **Aceptar**.

1. Cree una línea en blanco después de la asignación `baseCost` y acepte la finalización de la línea de código que aparece.

    GitHub Copilot debe proporcionar una sugerencia que asigne un valor a `volumeDiscount`.

1. Seleccione la línea de código que se usa para asignar un valor a `salesData[i].volumeDiscount`, abra el chat en línea y escriba el siguiente símbolo del sistema:

    ```output
    Assign 10 percent of quantitySold to volumeDiscount. Truncate any fractional values.
    ```

1. Revise las sugerencias proporcionadas por GitHub Copilot y seleccione **Aceptar**.

1. El método GenerateSalesData actualizado debería parecerse ahora al siguiente fragmento de código:

    ```csharp

    public SalesData[] GenerateSalesData()
    {
        SalesData[] salesData = new SalesData[1000];
        Random random = new Random();
        for (int i = 0; i < 1000; i++)
        {
            salesData[i].dateSold = new DateOnly(2023, random.Next(1, 13), random.Next(1, 29));
            salesData[i].departmentName = ProdDepartments.departmentNames[random.Next(0, ProdDepartments.departmentNames.Length)];
            int indexOfDept = Array.IndexOf(ProdDepartments.departmentNames, salesData[i].departmentName);
            string deptAbb = ProdDepartments.departmentAbbreviations[indexOfDept];
            string firstDigit = (indexOfDept + 1).ToString();
            string nextTwoDigits = random.Next(1, 100).ToString("D2");
            string sizeCode = new string[] { "XS", "S", "M", "L", "XL" }[random.Next(0, 5)];
            string colorCode = new string[] { "BK", "BL", "GR", "RD", "YL", "OR", "WT", "GY" }[random.Next(0, 8)];
            string manufacturingSite = ManufacturingSites.manufacturingSites[random.Next(0, ManufacturingSites.manufacturingSites.Length)];
            salesData[i].productID = $"{deptAbb}-{firstDigit}{nextTwoDigits}-{sizeCode}-{colorCode}-{manufacturingSite}";
            salesData[i].quantitySold = random.Next(1, 101);
            salesData[i].unitPrice = random.Next(25, 300) + random.NextDouble();
            salesData[i].baseCost = salesData[i].unitPrice * (1 - (random.Next(5, 21) / 100.0));
            salesData[i].volumeDiscount = (int)(salesData[i].quantitySold * 0.1);
        }
        return salesData;
    }

    ```

1. Guarde los cambios.

### Actualizar el método QuarterlySalesReport mediante el chat insertado

Debe actualizar el método `QuarterlySalesReport`. En función de los objetivos del proyecto, debe implementar las siguientes actualizaciones:

- Al mostrar los resultados de ventas, enumere los resultados en un orden lógico. Por ejemplo, al enumerar las ventas totales por trimestre, los trimestres deben aparecer en orden de Q1 a Q4.
- Muestre los valores de moneda mediante la configuración regional.
- Agregar cálculos para el porcentaje de beneficios y los beneficios trimestrales
- Agregue cálculos específicos de departamentos individuales: ventas trimestrales, beneficios y porcentaje de beneficios.
- Agregue cálculos para ubicaciones de fabricación específicas: ventas trimestrales, beneficios y porcentaje de beneficios.

En este momento, el método `QuarterlySalesReport` debe ser similar al siguiente fragmento de código:

```csharp

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
        Console.WriteLine("{0}: ${1}", quarter.Key, quarter.Value);
    }
}

```

Para actualizar el método `QuarterlySalesReport`, complete los pasos siguientes:

1. Para comprobar la salida actual del informe de ventas trimestrales, ejecute la aplicación.

    Debería ver una lista de los resultados de ventas trimestrales que se muestran en la ventana de la consola. Se usan valores aleatorios, por lo que los datos numéricos varían con cada ejecución.

    La salida del informe de ventas trimestral debe ser similar a la siguiente:

    ```output
    Quarterly Sales Report
    ----------------------
    Q3: $2060165.1045630067
    Q2: $2000706.5521363618
    Q4: $2168920.603583816
    Q1: $2174302.3663762277
    ```

    Observe que los trimestres no aparecen en orden y los valores de moneda no tienen el formato correcto.

    La primera tarea consiste en corregir estos problemas.

1. Ubique el método `QuarterlySalesReport` en el archivo Program.cs.

1. Seleccione todo el método.

1. Abra la interfaz de chat en línea y escriba el siguiente símbolo del sistema:

    ```output
    Update the QuarterlySalesReport method to display quarterly results in order. Format currency using regional settings. 
    ```

1. Dedique un minuto a revisar las sugerencias proporcionadas por GitHub Copilot.

    Debería ver una sugerencia que incluya el código necesario para calcular el porcentaje de beneficios y los beneficios trimestrales. La sugerencia debe incluir el código necesario para calcular el porcentaje de beneficios y los beneficios de cada trimestre.

1. Para aceptar la sugerencia proporcionada por GitHub Copilot, seleccione **Aceptar**.

1. Guarde los cambios.

1. Ejecute la aplicación y compruebe que los resultados de las ventas trimestrales ahora se muestren en orden y que los valores de moneda tengan el formato correcto.

    Aunque los valores numéricos son diferentes, la salida del informe de ventas trimestral debe tener ahora un formato similar al siguiente:

    ```output
    Quarterly Sales Report
    ----------------------
    Q1: $2,174,302.37
    Q2: $2,000,706.55
    Q3: $2,060,165.10
    Q4: $2,168,920.60

    ```

    El siguiente paso es agregar los cálculos para el beneficio trimestral y el porcentaje de beneficio.

1. Ubique el método `QuarterlySalesReport` en el archivo Program.cs.

1. Seleccione todo el método.

1. Abra la interfaz de chat en línea y escriba el siguiente símbolo del sistema:

    ```output
    Update the QuarterlySalesReport method to include calculations for quarterly profit and profit percentage. Include the new calculations in the report output.
    ```

1. Dedique un minuto a revisar las sugerencias proporcionadas por GitHub Copilot.

    Debería ver una sugerencia que incluya el código necesario para calcular el porcentaje de beneficios y los beneficios trimestrales. La sugerencia debe incluir el código necesario para calcular el porcentaje de beneficios y los beneficios de cada trimestre.

1. Para aceptar la sugerencia proporcionada por GitHub Copilot, seleccione **Aceptar**.

1. Continúe seleccionando **Aceptar** para las sugerencias restantes.

1. Guarde los cambios.

1. Ejecute la aplicación y compruebe que los resultados de ventas trimestrales ahora incluyan los cálculos de beneficio y el porcentaje de los beneficios.

    Aunque los valores numéricos son diferentes, la salida del informe de ventas trimestral debe tener ahora un formato similar al siguiente:

    ```output
    Quarterly Sales Report
    ----------------------
    Q1: Sales: $1,881,091.17, Profit: $231,351.24, Profit Percentage: 12.00%
    Q2: Sales: $1,949,240.91, Profit: $244,649.35, Profit Percentage: 11.00%
    Q3: Sales: $2,298,017.35, Profit: $273,622.53, Profit Percentage: 5.00%
    Q4: Sales: $2,279,185.96, Profit: $272,548.80, Profit Percentage: 16.00%    

    ```

    El siguiente paso es agregar cálculos para las ventas trimestrales, los beneficios y el porcentaje de beneficios por departamento.

1. Seleccione todo el método.

1. Para abrir la interfaz de chat en línea y, a continuación, escribir el siguiente símbolo del sistema:

    ```output
    Update the QuarterlySalesReport method to include calculations for quarterly sales, profit, and profit percentage by department. Include the new calculations in the report output. 
    ```

1. Dedique un minuto a revisar las sugerencias proporcionadas por GitHub Copilot.

    Debería ver una sugerencia que incluya el código necesario para calcular el porcentaje de beneficios y los beneficios trimestrales. La sugerencia debe incluir el código necesario para calcular el porcentaje de beneficios y los beneficios de cada trimestre.

1. Para aceptar la sugerencia proporcionada por GitHub Copilot, seleccione **Aceptar**.

1. Continúe seleccionando **Aceptar** para las sugerencias restantes.

1. Guarde los cambios.

1. Ejecute la aplicación y compruebe que los resultados de ventas trimestrales ahora incluyan los cálculos de beneficio y el porcentaje de los beneficios.

    Aunque los valores numéricos son diferentes, la salida del informe de ventas trimestral debe tener ahora un formato similar al siguiente:

    ```output
    Quarterly Sales Report
    ----------------------
    Q1: Sales: $2,043,493.57, Profit: $262,571.72, Profit Percentage: 14.00%
    By Department:
    Department: Accessories, Sales: $188,977.90, Profit: $25,229.53, Profit Percentage: 14.00%
    Department: Children's Clothing, Sales: $186,552.49, Profit: $25,511.74, Profit Percentage: 13.00%
    Department: Footwear, Sales: $293,706.49, Profit: $39,224.99, Profit Percentage: 19.00%
    Department: Men's Clothing, Sales: $301,385.47, Profit: $36,756.06, Profit Percentage: 19.00%
    Department: Outerwear, Sales: $238,099.65, Profit: $24,371.92, Profit Percentage: 15.00%
    Department: Sportswear, Sales: $251,349.38, Profit: $34,142.40, Profit Percentage: 8.00%
    Department: Undergarments, Sales: $297,690.60, Profit: $35,305.13, Profit Percentage: 9.00%
    Department: Women's Clothing, Sales: $285,731.58, Profit: $42,029.95, Profit Percentage: 19.00%
    
    Q2: Sales: $1,925,948.90, Profit: $232,929.95, Profit Percentage: 17.00%
    By Department:
    Department: Accessories, Sales: $251,572.42, Profit: $33,250.17, Profit Percentage: 11.00%
    Department: Children's Clothing, Sales: $311,862.99, Profit: $36,537.33, Profit Percentage: 8.00%
    Department: Footwear, Sales: $203,148.87, Profit: $23,041.46, Profit Percentage: 11.00%
    Department: Men's Clothing, Sales: $229,781.14, Profit: $26,226.68, Profit Percentage: 9.00%
    Department: Outerwear, Sales: $211,610.47, Profit: $23,684.65, Profit Percentage: 9.00%
    Department: Sportswear, Sales: $204,083.63, Profit: $20,750.56, Profit Percentage: 8.00%
    Department: Undergarments, Sales: $264,733.26, Profit: $35,155.66, Profit Percentage: 15.00%
    Department: Women's Clothing, Sales: $249,156.13, Profit: $34,283.45, Profit Percentage: 17.00%
    
    Q3: Sales: $2,113,223.50, Profit: $256,591.16, Profit Percentage: 7.00%
    By Department:
    Department: Accessories, Sales: $288,161.91, Profit: $32,279.54, Profit Percentage: 10.00%
    Department: Children's Clothing, Sales: $198,313.55, Profit: $24,146.72, Profit Percentage: 7.00%
    Department: Footwear, Sales: $205,840.60, Profit: $27,630.49, Profit Percentage: 5.00%
    Department: Men's Clothing, Sales: $229,279.26, Profit: $26,618.62, Profit Percentage: 13.00%
    Department: Outerwear, Sales: $353,696.46, Profit: $44,634.82, Profit Percentage: 14.00%
    Department: Sportswear, Sales: $229,490.12, Profit: $27,697.91, Profit Percentage: 5.00%
    Department: Undergarments, Sales: $316,942.44, Profit: $40,518.71, Profit Percentage: 5.00%
    Department: Women's Clothing, Sales: $291,499.15, Profit: $33,064.35, Profit Percentage: 10.00%
    
    Q4: Sales: $1,896,279.88, Profit: $248,226.28, Profit Percentage: 15.00%
    By Department:
    Department: Accessories, Sales: $336,698.68, Profit: $44,714.55, Profit Percentage: 11.00%
    Department: Children's Clothing, Sales: $193,345.18, Profit: $23,261.33, Profit Percentage: 13.00%
    Department: Footwear, Sales: $215,183.23, Profit: $29,616.00, Profit Percentage: 15.00%
    Department: Men's Clothing, Sales: $171,663.38, Profit: $24,299.37, Profit Percentage: 5.00%
    Department: Outerwear, Sales: $229,791.52, Profit: $28,211.17, Profit Percentage: 15.00%
    Department: Sportswear, Sales: $230,031.90, Profit: $32,732.40, Profit Percentage: 8.00%
    Department: Undergarments, Sales: $300,824.19, Profit: $34,649.79, Profit Percentage: 6.00%
    Department: Women's Clothing, Sales: $218,741.80, Profit: $30,741.67, Profit Percentage: 20.00%

    ```

### Resumen

En esta demostración, has utilizado la característica de chat insertado para actualizar los métodos `GenerateSalesData` y `QuarterlySalesReport`. Ha agregado nuevos campos a la estructura de datos `SalesData` y, a continuación, ha actualizado el método `GenerateSalesData` para generar datos para los nuevos campos. También ha actualizado el método `QuarterlySalesReport` para incluir cálculos de los beneficios y el porcentaje de beneficios trimestrales. También ha agregado cálculos para las ventas trimestrales,los beneficios y el porcentaje de beneficios por departamento.

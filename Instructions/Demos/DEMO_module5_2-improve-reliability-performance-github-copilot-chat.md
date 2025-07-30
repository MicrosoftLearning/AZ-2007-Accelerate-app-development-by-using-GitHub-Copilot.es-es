---
demo:
  title: 'Demostración: Mejora de la confiabilidad y el rendimiento del código mediante GitHub Copilot Chat'
  module: 'Module 5: Implement code improvements using GitHub Copilot tools'
---

# Demostración: Mejora de la confiabilidad y el rendimiento del código mediante GitHub Copilot Chat

## Instrucciones

Las actividades de demostración están diseñadas para un entorno que incluye los siguientes recursos:

- Visual Studio Code.
- Extensión del kit de desarrollo de C# para Visual Studio Code.
- Las extensiones de GitHub Copilot y GitHub Copilot Chat para Visual Studio Code. Se requiere una cuenta de GitHub con una suscripción activa para GitHub Copilot.
- Proyectos de código de ejemplo creados con C#.

**NOTA**: Se recomienda que los instructores consideren usar su propia cuenta de GitHub y la suscripción a GitHub Copilot para las demostraciones. Esto te permitirá controlar y personalizar el entorno de desarrollo. También harás que sea más fácil ajustar las demostraciones para adaptarlas a las necesidades de tus aulas.

**IMPORTANTE**: Si decides ejecutar las demostraciones en el entorno de laboratorio hospedado en lugar de en el equipo instructor, puedes descomprimir las aplicaciones de ejemplo en el entorno hospedado. Tendrás que configurar las extensiones de GitHub Copilot en el entorno hospedado para poder ejecutar las demostraciones. Es posible que el entorno hospedado sea más lento que el entorno local, por lo que es posible que tengas que ajustar el ritmo de las demostraciones según proceda.

### Presentación de la demostración

La confiabilidad y el rendimiento del código están estrechamente relacionados con los aspectos de la calidad del software. Son interdependientes de las siguientes maneras:

- Las mejoras en un área pueden afectar positivamente a la otra.
- Las deficiencias en uno pueden provocar problemas en el otro.

> [!IMPORTANT]
> Explica a los alumnos que esta demostración no trata sobre los procedimientos recomendados para desarrollar código confiable o de alto rendimiento. En su lugar, se centra en cómo usar GitHub Copilot Chat para generar sugerencias para mejorar la confiabilidad y el rendimiento del código en una aplicación de ejemplo. Las sugerencias no representan las mejores prácticas ni soluciones integrales para la fiabilidad y el rendimiento del código. Los desarrolladores deben usar su criterio y experiencia para evaluar e implementar las sugerencias proporcionadas por GitHub Copilot Chat. La implementación de sugerencias propuestas por GitHub Copilot no reemplaza la necesidad de realizar revisiones y pruebas exhaustivas de código.

#### Fiabilidad y rendimiento del código

Los desarrolladores deben esforzarse por un equilibrio entre la confiabilidad y el rendimiento del código. Un equilibrio correcto genera los siguientes resultados mutuamente beneficiosos:

- Aplicaciones que cumplen los requisitos funcionales.
- Aplicaciones que ofrecen una experiencia de usuario perfecta y eficaz.

En las secciones siguientes se proporciona información general sobre la confiabilidad y el rendimiento del código, junto con otros factores que los alumnos deben tener en cuenta.

##### Examen de la confiabilidad del código

La confiabilidad del código hace referencia a la probabilidad de que el software funcione correctamente en condiciones específicas y durante un período de tiempo determinado. Mejorar la confiabilidad del código ayuda a garantizar que el software funciona según lo previsto y cumple los requisitos del usuario.

Los desarrolladores pueden tener en cuenta los siguientes factores al trabajar en mejoras de confiabilidad de código:

- Posibles problemas: La identificación de posibles problemas en el código puede ayudar a evitar que se produzcan errores y errores. La identificación de posibles problemas debe incluir revisar el código para detectar problemas comunes y abordarlos de forma proactiva.
- Prueba: Las pruebas adecuadas son cruciales para identificar y corregir errores antes de que se publique el producto. Las pruebas adecuadas deben incluir pruebas unitarias, pruebas de integración, pruebas del sistema y pruebas de aceptación.
- Control de excepciones: Los mecanismos adecuados de control de excepciones pueden impedir que un sistema produzca errores cuando se produzcan condiciones inesperadas.

> [!NOTE]
> Asegúrese de que la calidad del código sea alta antes de empezar a trabajar en la confiabilidad del código. La refactorización de código, junto con los estándares y las directrices, puede ayudar a garantizar código de alta calidad.

Hay otros factores que afectan a la confiabilidad del código. Algunos de estos factores no son responsabilidades del desarrollador, mientras que otros deben considerarse antes o después de la confiabilidad del código. Entre estos factores se incluyen:

- Prácticas de desarrollo: Los siguientes procedimientos recomendados en el desarrollo de software, como las revisiones de código, la programación de pares y la conformidad con los estándares de codificación, pueden dar lugar a código más confiable.
- Objetivos y métricas de confiabilidad: Establecer objetivos claros de confiabilidad y tener métricas para medirlos puede guiar el proceso de desarrollo hacia la creación de software más confiable.
- Documentación: La documentación completa puede ayudar a comprender el sistema y sus componentes, lo que es esencial para mantener y solucionar problemas del sistema.
- Dependencias: Las bibliotecas externas y los servicios de los que depende el código pueden afectar a su confiabilidad. Si se produce un error en un servicio de terceros, también puede provocar un error en el sistema dependiente.
- Rendimiento: Los problemas de rendimiento también pueden afectar a la confiabilidad. Es importante asegurarse de que el sistema funciona bien bajo diferentes cargas.
- Supervisión y solución de problemas: La supervisión continua y una guía de solución de problemas confiable pueden ayudar a mantener la confiabilidad de un servicio mediante la identificación y solución rápida de problemas.
- Diseño y arquitectura: Un sistema bien diseñado con una arquitectura sólida puede controlar los errores correctamente y mantener la funcionalidad incluso cuando se produce un error en algunos componentes.
- Factores externos: Los problemas de confiabilidad posteriores a la versión pueden surgir debido a factores externos, como actualizaciones de hardware y sistema operativo, que pueden presentar problemas de compatibilidad o errores del sistema.

Mejorar la confiabilidad del código puede ayudarle a reducir la probabilidad de errores, errores y comportamientos inesperados.

##### Examen del rendimiento del código

El rendimiento del código hace referencia a la eficacia de las ejecuciones de un programa o aplicación, especialmente en términos de velocidad, uso de memoria y consumo general de recursos. Para garantizar o mejorar el rendimiento del código, los desarrolladores pueden realizar varias acciones:

Los desarrolladores deben tener en cuenta los siguientes factores al trabajar en mejoras en el rendimiento del código:

- Optimización de algoritmos: elige los algoritmos y estructuras de datos más eficaces para la tarea a mano. Incluso pequeñas mejoras pueden tener un impacto significativo en el rendimiento.
- Evite cálculos innecesarios: Almacene en caché los resultados de operaciones costosas siempre que sea posible y evite cálculos redundantes.
- Use la programación multithreading y asincrónica: Aproveche las arquitecturas de CPU modernas mediante la paralelización de tareas y la realización de operaciones de E/S de forma asincrónica.
- Minimizar las operaciones de E/S: la E/S de disco y red puede ser lenta, por lo que es importante minimizar estas operaciones o realizarlas de forma asincrónica para evitar bloquear el subproceso de ejecución principal.

> [!NOTE]
> Asegúrese de que la calidad del código sea alta antes de empezar a trabajar en el rendimiento del código. La refactorización de código, junto con los estándares y las directrices, puede ayudar a garantizar código de alta calidad.

Hay otros factores que afectan al rendimiento del código. Algunos de estos factores no son responsabilidades del desarrollador, mientras que otros deben considerarse antes o después de trabajar en el rendimiento del código. Entre estos factores se incluyen:

- Perfil y banco de pruebas: Use herramientas de generación de perfiles para identificar cuellos de botella de rendimiento. Las pruebas comparativas antes y después de realizar cambios pueden cuantificar el impacto de las optimizaciones.
- Administrar la memoria de forma eficaz: Use herramientas de generación de perfiles de memoria para detectar fugas y asegurarse de que la memoria se asigna y desasigna correctamente.
- Optimizar las interacciones de la base de datos: Use consultas eficaces, indexación adecuada y almacenamiento en caché de bases de datos para minimizar la sobrecarga de rendimiento de las interacciones de la base de datos.
- Revisiones de código: Revise periódicamente el código para detectar problemas de rendimiento. Las revisiones del mismo nivel pueden ayudar a detectar ineficiencias que el desarrollador original podría haber perdido.
- Manténgase actualizado: Use las versiones más recientes de lenguajes, bibliotecas y marcos, ya que a menudo incluyen mejoras de rendimiento.
- Educar y colaborar: Manténgase informado sobre los procedimientos recomendados para la optimización del rendimiento y colabore con otros desarrolladores para aprender de sus experiencias.

Cuando los desarrolladores se centran en estas áreas, pueden mejorar significativamente el rendimiento de su código, lo que conduce a aplicaciones más rápidas y con mayor capacidad de respuesta. La optimización del rendimiento es un proceso continuo y es’importante supervisar y mejorar continuamente el rendimiento de las aplicaciones.

El chat de GitHub Copilot puede ayudarle a mejorar el rendimiento del código proporcionando sugerencias para optimizar algoritmos, reducir cálculos innecesarios, usar programación multiproceso y asincrónico, y minimizar las operaciones de E/S.

### Desarrollo de mensajes para chat de GitHub Copilot

Las solicitudes que escriba para GitHub Copilot Chat deben proporcionar un contexto y una intención claramente definidos. Tenga en cuenta las siguientes sugerencias al desarrollar las solicitudes:

- Defina un contexto externo cuyo ámbito esté en un nivel superior al código que desea actualizar. Por ejemplo, si desea mejorar un método, especifique la clase o el archivo que incluye el método como contexto externo. Identifique el método como un contexto interno.
- Use participantes de chat y variables de chat para ayudar a especificar el contexto. Puede usar las variables de chat `#file:` y `#selection` para identificar el código específico en el que se centra. También puede incluir el área de trabajo completa (`@workspace`) cuando corresponda. Consulte la selección de código o archivo en la parte del lenguaje natural del símbolo del sistema.
- La intención debe ser clara, concisa y específica. El mensaje debe especificar el tipo de mejora que desea lograr.

Durante esta parte de la demostración, revisarás el proyecto de **APL2007M5BankAccount-Reliability** y crearás tres solicitudes de GitHub Copilot Chat. Las indicaciones se centran en mejorar la confiabilidad y el rendimiento del código.

Sigue estos pasos para completar esta parte de la demostración:

1. Abra la aplicación de ejemplo **APL2007M5BankAccount-Reliability** en Visual Studio Code.

1. Abra la vista Explorador de soluciones.

1. Expanda el proyecto **BankAccount** de y, a continuación, revise los archivos de código **BankAccount.cs** y **Program.cs**.

    El archivo **BankAccount.cs** contiene el código de la clase `BankAccount`, que representa una cuenta bancaria con propiedades como AccountNumber, Balance, AccountHolderName, AccountType y DateOpened. Contiene los métodos siguientes:

    - Crédito(double amount): Este método aumenta el saldo de la cuenta por la cantidad especificada.
    - Débito(double amount): Este método reduce el saldo de la cuenta por la cantidad especificada. Si el saldo es menor que el importe, produce una excepción con el mensaje "Saldo insuficiente para el débito".
    - GetBalance(): Este método devuelve el saldo actual de la cuenta.
    - Transferir(BankAccount toAccount, double amount): Este método transfiere una cantidad especificada de la cuenta actual a toAccount. Si el saldo es menor que el importe, produce una excepción con el mensaje "Saldo insuficiente para la transferencia". Si AccountHolderName es diferente y la cantidad es superior a 500, produce una excepción con el mensaje "La cantidad de transferencia supera el límite máximo para distintos propietarios de cuentas".
    - PrintStatement(): Este método imprime AccountNumber y Balance en la consola.
    - CalculateInterest(double interestRate): Este método calcula el interés en el saldo actual utilizando el valor interestRate especificado.

    El archivo **Program.cs** contiene una aplicación de consola que simula un sistema bancario. Incluye los siguientes métodos:

    - El método Main: Este método es el punto de partida de la aplicación. Crea una lista de cuentas bancarias y simula transacciones y transferencias en estas cuentas.
    - Método CreateBankAccounts: Este método crea un número especificado de cuentas bancarias con saldos iniciales aleatorios, nombres de titulares de cuenta, tipos de cuenta y fechas de apertura. Usa un bloque try-catch para controlar las excepciones que pueden producirse durante la creación de la cuenta.
    - Método SimulateTransactions: Este método simula un número especificado de transacciones en cada cuenta de la lista proporcionada. Cada transacción es un importe de dólar aleatorio y puede ser un crédito (depósito) o un débito (retiro), dependiendo de si la cantidad es positiva o negativa.
    - Método SimulateTransfers: Este método es idéntico a SimulateTransactions. Parece que está diseñado para simular transferencias entre cuentas, pero actualmente, simplemente duplica la funcionalidad de SimulateTransactions.
    - Método GenerateRandomDollarAmount: Este método genera una cantidad de dólar aleatoria dentro de un intervalo especificado. El intervalo y el método de cálculo difieren en función de si la cantidad es para un saldo de cuenta o una transacción
    - Método GenerateRandomAccountHolder: Este método selecciona un nombre de titular de cuenta aleatorio de una lista predefinida.
    - Método GenerateRandomAccountType: Este método selecciona un tipo de cuenta aleatorio de una lista predefinida.
    - Método GenerateRandomDateOpened: Este método genera una fecha aleatoria dentro de un intervalo especificado para la fecha de apertura de la cuenta.

1. Dedica un minuto a describir las indicaciones que podrían ayudarte a mejorar la confiabilidad y el rendimiento del código.

    Desarrolle solicitudes para la clase BankAccount y la clase Program. Tenga en cuenta los siguientes factores de confiabilidad y rendimiento al desarrollar las solicitudes:

    - Posibles problemas: La identificación de posibles problemas en el código puede ayudar a evitar que se produzcan errores y errores. Esto incluye revisar el código de los problemas comunes y abordarlos de forma proactiva.
    - Prueba: Las pruebas adecuadas son cruciales para identificar y corregir errores antes de que se publique el producto. Esto incluye pruebas unitarias, pruebas de integración, pruebas del sistema y pruebas de aceptación.
    - Control de excepciones: Los mecanismos adecuados de control de excepciones pueden impedir que un sistema produzca errores cuando se produzcan condiciones inesperadas.

    - Optimización de algoritmos: Elija los algoritmos y estructuras de datos más eficaces para la tarea a mano. Incluso pequeñas mejoras pueden tener un impacto significativo en el rendimiento.
    - Evite cálculos innecesarios: Almacene en caché los resultados de operaciones costosas siempre que sea posible y evite cálculos redundantes.
    - Use la programación multithreading y asincrónica: Aproveche las arquitecturas de CPU modernas mediante la paralelización de tareas y la realización de operaciones de E/S de forma asincrónica.
    - Minimizar las operaciones de E/S: La E/S de disco y red puede ser lenta, por lo que es’importante minimizar estas operaciones o realizarlas de forma asincrónica para evitar bloquear el subproceso de ejecución principal.

    Para este proyecto, puede utilizar las siguientes indicaciones para generar sugerencias para mejorar la fiabilidad de su código:

    Aviso: `@workspace /explain How can I improve exception handling the [selected code]?` (adjuntar BankAccount.cs al contexto de Chat)

    Aviso: `@workspace /explain How can I reduce unexpected issues for the [selected code]?` (adjuntar BankAccount.cs al contexto de Chat)

    Aviso: `@workspace /explain How can I improve unit test support for the [selected code]?` (adjuntar BankAccount.cs al contexto de Chat)

    Aviso: `@workspace /explain How can I avoid future bugs or issues in the [selected code]?` (adjuntar Program.cs al contexto de Chat)

    Aviso: `@workspace /explain How can I improve exception handling for the [selected code]?` (adjuntar Program.cs al contexto de Chat)

    Aviso: `@workspace /explain How can I improve the efficiency of algorithms or data structures for the [selected code]?` (adjuntar Program.cs al contexto de Chat)

    Aviso: `@workspace /explain How can I improve performance with asynchronous tasks or methods in the [selected code]?` (adjuntar Program.cs al contexto de Chat)

    Aviso: `@workspace /explain How can I improve unit test support for the [selected code]?` (adjuntar BankAccountTests.cs y BankAccount.cs al contexto de Chat)

1. Selecciona dos indicaciones que puedas utilizar para mejorar la clase BankAccount durante esta demostración.

    Para la clase BankAccount, intente seleccionar avisos que se centren en la confiabilidad.

1. Selecciona dos indicaciones que puedas utilizar para mejorar la clase del Programa durante esta demostración.

    Para la clase del Programa, intente seleccionar una indicación que se centre en la fiabilidad y otra en el rendimiento.

### Mejorar la fiabilidad del código de la clase BankAccount utilizando GitHub Copilot Chat

Garantizar la confiabilidad del código de producción es esencial para cualquier proyecto de software. La aplicación de ejemplo APL2007M5BankAccount-Reliability usa la clase Program para simular el escenario bancario, pero es la clase BankAccount que se implementa en un entorno de producción. Mejorar la confiabilidad de la clase BankAccount ayuda a garantizar que funciona según lo previsto y cumple los requisitos del usuario.

El chat de GitHub Copilot se puede usar para ayudar a mejorar la confiabilidad del código. Las indicaciones pueden dirigir a GitHub Copilot para generar sugerencias que mejoran el control de excepciones, reducen los problemas inesperados y mejoran la compatibilidad con pruebas unitarias. También puede crear avisos de amplio alcance que le pidan sugerencias generales para mejorar la fiabilidad del código. Una combinación de indicaciones específicas y generales puede ayudarle a identificar las áreas que necesitan mejorar y a aplicar los cambios necesarios.

> [!NOTE]
> La implementación y las pruebas de las actualizaciones sugeridas tardan tiempo, y el tiempo puede ser un factor durante esta demostración. Seleccionar indicaciones que se centren en áreas específicas de mejora puede ayudarle a gestionar su tiempo. Las indicaciones demasiado amplias pueden generar un gran número de sugerencias o sugerencias complejas difíciles de evaluar y aplicar en poco tiempo. Una vez que empiece, puede actualizar las solicitudes con detalles más específicos si encuentra que las actualizaciones sugeridas tienen un ámbito demasiado amplio o demasiado complejo.

Sigue estos pasos para completar esta parte de la demostración:

1. Asegúrese de que el proyecto se crea y ejecuta sin errores.

    Las advertencias son aceptables siempre que la aplicación se ejecute, pero los errores no controlados que provocan que la aplicación se bloquee se deben resolver antes de empezar a trabajar con GitHub Copilot Chat.

1. Abra el archivo BankAccount.cs en Visual Studio Code y seleccione todo el código del archivo.

1. Abra la vista Chat.

1. En la vista Chat, agrega los archivos pertinentes al contexto de Chat y, a continuación, escribe tu indicación.

1. Revise las sugerencias proporcionadas por GitHub Copilot Chat.

    Por ejemplo, suponga que completa las siguientes acciones:

    - Abra el archivo BankAccount.cs y seleccione todo el código.
    - Elegir la siguiente solicitud: `@workspace /explain How can I improve exception handling in the BankAccount.cs file?`
    - Abra la vista Chat y adjunte los archivos BankAccount.cs y Program.cs al contexto Chat.
    - Escribir la solicitud en la vista Chat.

    GitHub Copilot Chat sugiere actualizaciones similares a la siguiente respuesta:

    *Para mejorar el control de excepciones en el archivo BankAccount.cs, tenga en cuenta las sugerencias siguientes:*

    *1. **Usar excepciones específicas**: En lugar de iniciar la clase base `Exception`, usa excepciones más específicas. Esto facilita que el código de llamada comprenda y controle tipos específicos de errores. Por ejemplo, podrías iniciar una excepción InvalidOperationException al intentar hacer cargos en cuenta o transferencias con fondos insuficientes.*

    *2. **Incluir más información en los mensajes de excepción**: Los mensajes de excepción podrían proporcionar más detalles sobre la operación que produjo un error. Por ejemplo, en el método `Debit`, el mensaje de excepción podría incluir el importe que se ha intentado cargar en cuenta y el saldo actual.*

    *3. **Considerar excepciones personalizadas**: Si hay condiciones de error específicas que son únicas para la aplicación, es conveniente que cree clases de excepción personalizadas. La creación de excepciones personalizadas te permite encapsular más información sobre la condición de error y hace que el código esté más autodocumentado.*

    *Aquí se muestra cómo puede mejorar el método `Debit` con estas sugerencias:*

    ```csharp

    public void Debit(double amount)
    {
        if (Balance >= amount)
        {
            Balance -= amount;
        }
        else
        {
            throw new InvalidOperationException($"Insufficient balance for debit. Attempted to debit {amount}, but current balance is {Balance}.");
        }
    }

    ```

    *Y este es un ejemplo de una clase de excepción personalizada:*

    ```csharp

    public class InsufficientFundsException : Exception
    {
        public double AttemptedAmount { get; }
        public double CurrentBalance { get; }
        public InsufficientFundsException(double attemptedAmount, double currentBalance)
            : base($"Insufficient balance for debit. Attempted to debit {attemptedAmount}, but current balance is {currentBalance}.")
        {
            AttemptedAmount = attemptedAmount;
            CurrentBalance = currentBalance;
        }
    }

    ```

    *Podría iniciar esta excepción personalizada en el método Debit:*

    ```csharp

    public void Debit(double amount)
    {
        if (Balance >= amount)
        {
            Balance -= amount;
        }
        else
        {
            throw new InsufficientFundsException(amount, Balance);
        }
    }

    ```

    *De este modo, el código de llamada puede detectar InsufficientFundsException y tener acceso a las propiedades AttemptedAmount y CurrentBalance para controlar la condición de error de forma más eficaz.*

1. Implemente las actualizaciones sugeridas que ayudan a mejorar la confiabilidad del código para la clase `BankAccount`.

1. Para asegurarse de que los cambios no introdujeron ningún error, compile y ejecute la solución antes de continuar.

    > [!TIP]
    > En el ejemplo anterior, la vista Chat proporcionó fragmentos de código que implementan un ejemplo de la actualización sugerida (con excepciones específicas, incluida más información en el mensaje de excepción y la creación de excepciones personalizadas). Después de implementar sugerencias, intente usar finalizaciones de línea de código para generar código nuevo que duplique la actualización. En el caso de este ejemplo, se pueden usar finalizaciones de línea de código para crear más clases de excepciones personalizadas. A continuación, puede usar finalizaciones de línea de código para actualizar los otros métodos con las nuevas excepciones personalizadas. También puede volver a ejecutar el mensaje original para ver otras sugerencias.

1. Seleccione todo el código del archivo BankAccount.cs.

1. Abra la vista Chat.

1. Use el botón **Asociar contexto** para agregar archivos relevantes al contexto de Chat y, a continuación, escriba el segundo mensaje de "confiabilidad".

1. Revise las sugerencias proporcionadas por GitHub Copilot Chat.

    Por ejemplo, si escribe `@workspace /explain How can I reduce unexpected issues for the selected code?` en la vista Chat, GitHub Copilot Chat sugiere actualizaciones similares a la siguiente respuesta:

    *Para reducir problemas inesperados en la clase BankAccount, puede implementar las siguientes mejoras:*

    *1. Usar Enum para tipo de cuenta: En lugar de usar una cadena para el tipo de cuenta y comprobar si es "Ahorro" o "Actual", considera la posibilidad de usar una enumeración. Esto evitaría posibles problemas con la comparación de cadenas (como la distinción entre mayúsculas y minúsculas) y limitaría el tipo de cuenta a valores predefinidos.*

    ```csharp

    public enum AccountType
    {
        Savings,
        Current
    }

    ```

    *2. Use Decimal para valores monetarios: Por lo general, se recomienda usar el tipo decimal en lugar de double para los valores monetarios para evitar errores de redondeo.*

    *3. Agregar más validaciones: Puedes agregar más validaciones en los métodos. Por ejemplo, en el método Transfer, podrías comprobar si toAccount no es null antes de continuar con la transferencia.*

    *4. Utilizar constantes para números mágicos: En el método Transfer, hay un número mágico 500. Sería mejor definirlo como una constante con un nombre significativo en la parte superior de la clase.*

    ```csharp
    private const double MaxTransferAmountForDifferentOwners = 500;
    ```

    *5. Excepción personalizada para el límite de transferencia: En lugar de iniciar una excepción general cuando el importe de la transferencia supera el límite para distintos propietarios de cuentas, considere la posibilidad de crear una excepción personalizada como ExceededTransferLimitException.*

    *6. Registro: Considerar la posibilidad de agregar el registro a la aplicación. Esto puede ayudarte a comprender el flujo de la aplicación y a diagnosticar problemas.*

    *7. Pruebas unitarias: Escribe pruebas unitarias para los métodos para asegurarte de que se comportan según lo previsto en varios escenarios. Esto puede ayudar a detectar problemas al principio del proceso de desarrollo.*

1. Tenga en cuenta el ámbito y la amplitud de las sugerencias proporcionadas por GitHub Copilot Chat.

    Algunas indicaciones pueden generar un gran número de sugerencias que afectan a un amplio ámbito. Si esto sucede, compruebe si se puede usar un único elemento de sugerencia para definir un mensaje nuevo que proporcione una intención o un contexto más específicos.

1. Use la lista de sugerencias para crear un mensaje que incluya una intención o contexto más detallados.

    Cada una de las sugerencias proporcionadas por GitHub Copilot Chat se puede investigar e implementar por separado. A partir de la parte superior de la lista y trabajar hacia abajo puede ayudarle a centrarse en una mejora cada vez.

1. Introduzca su consulta detallada en la vista Chat y, a continuación, revise las sugerencias proporcionadas por GitHub Copilot Chat.

    Supongamos que utiliza el segundo ejemplo de solicitud de fiabilidad. La respuesta de GitHub Copilot Chat incluye el siguiente elemento de sugerencia:

    *Agregar más validaciones: Puedes agregar más validaciones en los métodos. Por ejemplo, en el método Transfer, podrías comprobar si toAccount no es null antes de continuar con la transferencia.*

    Puede usar esta sugerencia para crear un nuevo mensaje que se centre en agregar más validaciones al método Transfer. Puede seleccionar el método Transfer y, a continuación, escribir el siguiente símbolo del sistema en la vista Chat:

    `@workspace /explain #file:BankAccount.cs How can I improve method validations for the selected code?`

    En este caso, el chat GitHub Copilot sugiere actualizaciones similares a la siguiente respuesta:

    *El código que has proporcionado está bien estructurado y sigue los procedimientos recomendados para el control de excepciones. Sin embargo, hay algunas áreas en las que podrías realizar mejoras:*

    *1. Consolidar la lógica de validación: Podrías crear una clase o un método de validación independiente para controlar toda la lógica de validación. Esto haría que la clase BankAccount esté más limpia y más centrada en sus principales responsabilidades.*

    *2. Utilizar atributos de validación personalizados: Para parte de la validación, podrías utilizar atributos de validación personalizados. Esto te permitiría anotar las propiedades que necesitan validación y mantener la lógica de validación independiente de la lógica de negocios.*

    *3. Utilizar Fluent Validation: Fluent Validation es una biblioteca de .NET que usa una interfaz fluida y expresiones lambda para crear reglas de validación. Puede hacer que el código de validación sea más intuitivo y fácil de leer.*

    *4. Evitar números mágicos: En el método Transfer, tienes un valor 500 codificado de forma rígida. Por lo general, es recomendable evitar "números mágicos" y definirlos como constantes con nombres significativos en la parte superior de la clase.*

    Este es un ejemplo de cómo puede implementar algunas de estas sugerencias:

    ```csharp

    public class BankAccount
    {
        private const double MaxTransferAmountForDifferentOwners = 500;
        // ...
        public void Transfer(BankAccount toAccount, double amount)
        {
            ValidateTransferAmount(amount);
            ValidateTransferLimitForDifferentOwners(toAccount, amount);
    
            if (Balance >= amount)
            {
                Debit(amount);
                toAccount.Credit(amount);
            }
            else
            {
                throw new InsufficientFundsException(amount, Balance);
            }
        }
        private void ValidateTransferAmount(double amount)
        {
            if (amount < 0)
            {
                throw new InvalidTransferAmountException(amount);
            }
        }
        private void ValidateTransferLimitForDifferentOwners(BankAccount toAccount, double amount)
        {
            if (AccountHolderName != toAccount.AccountHolderName && amount > MaxTransferAmountForDifferentOwners)
            {
                throw new Exception("Transfer amount exceeds maximum limit for different account owners.");
            }
        }
    }

    ```

    Puede seguir trabajando a través de las sugerencias proporcionadas por el Chat de GitHub Copilot hasta que implemente todas las mejoras que considere necesarias.

1. Implemente las actualizaciones sugeridas y, a continuación, compile y ejecute su solución antes de continuar.

    Corrija los errores introducidos por los cambios antes de continuar.

### Mejore la fiabilidad del código y el rendimiento de la clase Programa utilizando el chat GitHub Copilot

1. Abra el archivo BankAccount.cs en Visual Studio Code y seleccione todo el código del archivo.

1. Abra el archivo BankAccount.cs en Visual Studio Code y seleccione todo el código del archivo.

1. Abra la vista Chat.

1. En la vista Chat, use el botón **Adjuntar contexto** para agregar archivos pertinentes al contexto de chat y, a continuación, escriba el mensaje.

1. Revise las sugerencias proporcionadas por GitHub Copilot Chat.

    Por ejemplo, si escribe `@workspace /explain How can I improve performance with asynchronous tasks or methods in the Program.cs file?` en la vista Chat, GitHub Copilot Chat sugiere actualizaciones similares a la siguiente respuesta:

    *Para mejorar el rendimiento con tareas o métodos asincrónicos en el archivo Program.cs, puedes usar la programación asincrónica con las palabras clave async y await. Esto permitirá al programa realizar operaciones enlazadas a E/S sin bloquear el subproceso principal, lo que hace que sea más dinámico y eficaz.*

    *Esta es una versión mejorada del archivo Program.cs con métodos asincrónicos:*

    ```csharp

    using System;
    using System.Collections.Generic;
    using System.Threading.Tasks;
    namespace BankAccountApp
    {
        class Program
        {
            private static readonly Random random = new Random();
            private const int MaxYearsBack = 10;
            private const int NumberOfAccounts = 20;
            private const int NumberOfTransactions = 100;
            private const double minTransactionAmount = -500.0;
            private const double maxTransactionAmount = 500.0;
            private const double minAccountStart = 200.0;
            private const double maxAccountStart = 1000.0;
            static async Task Main(string[] args)
            {
                List<BankAccount> accounts = await CreateBankAccountsAsync(NumberOfAccounts);
                await SimulateTransactionsAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
                await SimulateTransfersAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
            }
            static async Task<List<BankAccount>> CreateBankAccountsAsync(int numberOfAccounts)
            {
                List<BankAccount> accounts = new List<BankAccount>();
                int createdAccounts = 0;
                while (createdAccounts < numberOfAccounts)
                {
                    try
                    {
                        double initialBalance = GenerateRandomDollarAmount(true, minAccountStart, maxAccountStart);
                        string accountHolderName = GenerateRandomAccountHolder();
                        string accountType = GenerateRandomAccountType();
                        DateTime dateOpened = GenerateRandomDateOpened();
                        BankAccount account = new BankAccount($"Account {createdAccounts + 1}", initialBalance, accountHolderName, accountType, dateOpened);
                        accounts.Add(account);
                        createdAccounts++;
                    }
                    catch (Exception ex)
                    {
                        Console.WriteLine($"Account creation failed: {ex.Message}");
                    }
                    await Task.Yield(); // Yield control to allow other tasks to run
                }
                return accounts;
            }
            static async Task SimulateTransactionsAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                List<Task> tasks = new List<Task>();
                foreach (BankAccount account in accounts)
                {
                    tasks.Add(Task.Run(async () =>
                    {
                        for (int i = 0; i < numberOfTransactions; i++)
                        {
                            double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                            try
                            {
                                if (transactionAmount >= 0)
                                {
                                    account.Credit(transactionAmount);
                                    Console.WriteLine($"Credit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                                else
                                {
                                    account.Debit(-transactionAmount);
                                    Console.WriteLine($"Debit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                            }
                            catch (Exception ex)
                            {
                                Console.WriteLine($"Transaction failed: {ex.Message}");
                            }
                            await Task.Yield(); // Yield control to allow other tasks to run
                        }
                        Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                    }));
                }
                await Task.WhenAll(tasks);
            }
            static async Task SimulateTransfersAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                List<Task> tasks = new List<Task>();
                foreach (BankAccount account in accounts)
                {
                    tasks.Add(Task.Run(async () =>
                    {
                        for (int i = 0; i < numberOfTransactions; i++)
                        {
                            double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                            try
                            {
                                if (transactionAmount >= 0)
                                {
                                    account.Credit(transactionAmount);
                                    Console.WriteLine($"Credit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                                else
                                {
                                    account.Debit(-transactionAmount);
                                    Console.WriteLine($"Debit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                            }
                            catch (Exception ex)
                            {
                                Console.WriteLine($"Transaction failed: {ex.Message}");
                            }
                            await Task.Yield(); // Yield control to allow other tasks to run
                        }
                        Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                    }));
                }
                await Task.WhenAll(tasks);
            }
            static double GenerateRandomDollarAmount(bool isAccount, double min, double max)
            {
                if (isAccount)
                {
                    double accountStartingValue = random.NextDouble() * (max - min) + min;
                    return Math.Round(accountStartingValue, 2);
                }
                else
                {
                    double transactionAmount = random.NextDouble() * random.Next((int)min, (int)max) + random.NextDouble();
                    return Math.Round(transactionAmount, 2);
                }
            }
            static string GenerateRandomAccountHolder()
            {
                string[] accountHolderNames = { "John Smith", "Maria Garcia", "Mohammed Khan", "Sophie Dubois", "Liam Johnson", "Emma Martinez", "Noah Lee", "Olivia Kim", "William Chen", "Ava Wang", "James Brown", "Isabella Nguyen", "Benjamin Wilson", "Mia Li", "Lucas Anderson", "Charlotte Liu", "Alexander Taylor", "Amelia Patel", "Daniel Garcia", "Sophia Kim" };
                var accountHolderName = accountHolderNames[random.Next(0, accountHolderNames.Length)];
                return accountHolderName;
            }
            static string GenerateRandomAccountType()
            {
                string[] accountTypes = { "Savings", "Checking", "Money Market", "Certificate of Deposit", "Retirement" };
                return accountTypes[random.Next(0, accountTypes.Length)];
            }
            static DateTime GenerateRandomDateOpened()
            {
                DateTime startDate = new DateTime(DateTime.Today.Year - MaxYearsBack, 1, 1);
                int daysRange = (DateTime.Today - startDate).Days;
                DateTime randomDate = startDate.AddDays(random.Next(daysRange));
                if (randomDate.Year == DateTime.Today.Year && randomDate >= DateTime.Today)
                {
                    randomDate = randomDate.AddDays(-1);
                }
                return randomDate;
            }
        }
    }

    ```

1. Implemente las actualizaciones sugeridas que ayudan a mejorar el rendimiento del código (o confiabilidad) de la clase `Program`.

1. Para asegurarse de que los cambios no introdujeron ningún error, compile y ejecute la solución antes de continuar.

1. Seleccione todo el código del archivo Program.cs y, a continuación, escriba el símbolo del sistema de "confiabilidad" en la vista Chat.

1. Revise las sugerencias proporcionadas por GitHub Copilot Chat.

    > [!NOTE]
    > No es necesario implementar las sugerencias de actualización que GitHub Copilot generó a partir de este cuarto aviso, pero debe revisar las sugerencias.

    Por ejemplo, si escribe `@workspace /explain How can I improve exception handling for the selected code?` en la vista Chat, GitHub Copilot Chat sugiere actualizaciones similares a la siguiente respuesta:

    *Para mejorar el control de excepciones en el archivo Program.cs, puede implementar las sugerencias siguientes:*

    *1. Usar tipos de excepción específicos: En lugar de detectar excepciones genéricas, capture excepciones específicas siempre que sea posible.*

    *2. Agregue más contexto a excepciones: Proporcione más contexto en los mensajes de excepción para facilitar la depuración.*

    *3. Excepciones de registro: En lugar de simplemente imprimir excepciones en la consola, considere la posibilidad de registrarlas para mejorar la rastreabilidad.*

    *Esta es una versión mejorada del archivo Program.cs con un mejor control de excepciones:*

    ```csharp

    using System;
    using System.Collections.Generic;
    using System.Threading.Tasks;
    namespace BankAccountApp
    {
        class Program
        {
            private static readonly Random random = new Random();
            private const int MaxYearsBack = 10;
            private const int NumberOfAccounts = 20;
            private const int NumberOfTransactions = 100;
            private const double minTransactionAmount = -500.0;
            private const double maxTransactionAmount = 500.0;
            private const double minAccountStart = 200.0;
            private const double maxAccountStart = 1000.0;
            static async Task Main(string[] args)
            {
                List<BankAccount> accounts = await CreateBankAccountsAsync(NumberOfAccounts);
                await SimulateTransactionsAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
                await SimulateTransfersAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
            }
            static async Task<List<BankAccount>> CreateBankAccountsAsync(int numberOfAccounts)
            {
                List<BankAccount> accounts = new List<BankAccount>();
                int createdAccounts = 0;
                while (createdAccounts < numberOfAccounts)
                {
                    try
                    {
                        double initialBalance = GenerateRandomDollarAmount(true, minAccountStart, maxAccountStart);
                        string accountHolderName = GenerateRandomAccountHolder();
                        string accountType = GenerateRandomAccountType();
                        DateTime dateOpened = GenerateRandomDateOpened();
                        BankAccount account = new BankAccount($"Account {createdAccounts + 1}", initialBalance, accountHolderName, accountType, dateOpened);
                        accounts.Add(account);
                        createdAccounts++;
                    }
                    catch (ArgumentException ex)
                    {
                        Console.WriteLine($"Account creation failed due to invalid argument: {ex.Message}");
                    }
                    catch (Exception ex)
                    {
                        Console.WriteLine($"Account creation failed: {ex.Message}");
                    }
                    await Task.Yield(); // Yield control to allow other tasks to run
                }
                return accounts;
            }
            static async Task SimulateTransactionsAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                List<Task> tasks = new List<Task>();
                foreach (BankAccount account in accounts)
                {
                    tasks.Add(Task.Run(async () =>
                    {
                        for (int i = 0; i < numberOfTransactions; i++)
                        {
                            double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                            try
                            {
                                if (transactionAmount >= 0)
                                {
                                    account.Credit(transactionAmount);
                                    Console.WriteLine($"Credit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                                else
                                {
                                    account.Debit(-transactionAmount);
                                    Console.WriteLine($"Debit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                            }
                            catch (ArgumentException ex)
                            {
                                Console.WriteLine($"Transaction failed due to invalid argument: {ex.Message}");
                            }
                            catch (InsufficientBalanceException ex)
                            {
                                Console.WriteLine($"Transaction failed due to insufficient balance: {ex.Message}");
                            }
                            catch (Exception ex)
                            {
                                Console.WriteLine($"Transaction failed: {ex.Message}");
                            }
                            await Task.Yield(); // Yield control to allow other tasks to run
                        }
                        Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                    }));
                }
                await Task.WhenAll(tasks);
            }
            static async Task SimulateTransfersAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                List<Task> tasks = new List<Task>();
                foreach (BankAccount account in accounts)
                {
                    tasks.Add(Task.Run(async () =>
                    {
                        for (int i = 0; i < numberOfTransactions; i++)
                        {
                            double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                            try
                            {
                                if (transactionAmount >= 0)
                                {
                                    account.Credit(transactionAmount);
                                    Console.WriteLine($"Credit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                                else
                                {
                                    account.Debit(-transactionAmount);
                                    Console.WriteLine($"Debit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                            }
                            catch (ArgumentException ex)
                            {
                                Console.WriteLine($"Transaction failed due to invalid argument: {ex.Message}");
                            }
                            catch (InsufficientBalanceException ex)
                            {
                                Console.WriteLine($"Transaction failed due to insufficient balance: {ex.Message}");
                            }
                            catch (Exception ex)
                            {
                                Console.WriteLine($"Transaction failed: {ex.Message}");
                            }
                            await Task.Yield(); // Yield control to allow other tasks to run
                        }
                        Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                    }));
                }
                await Task.WhenAll(tasks);
            }
            static double GenerateRandomDollarAmount(bool isAccount, double min, double max)
            {
                if (isAccount)
                {
                    double accountStartingValue = random.NextDouble() * (max - min) + min;
                    return Math.Round(accountStartingValue, 2);
                }
                else
                {
                    double transactionAmount = random.NextDouble() * random.Next((int)min, (int)max) + random.NextDouble();
                    return Math.Round(transactionAmount, 2);
                }
            }
            static string GenerateRandomAccountHolder()
            {
                string[] accountHolderNames = { "John Smith", "Maria Garcia", "Mohammed Khan", "Sophie Dubois", "Liam Johnson", "Emma Martinez", "Noah Lee", "Olivia Kim", "William Chen", "Ava Wang", "James Brown", "Isabella Nguyen", "Benjamin Wilson", "Mia Li", "Lucas Anderson", "Charlotte Liu", "Alexander Taylor", "Amelia Patel", "Daniel Garcia", "Sophia Kim" };
                var accountHolderName = accountHolderNames[random.Next(0, accountHolderNames.Length)];
                return accountHolderName;
            }
            static string GenerateRandomAccountType()
            {
                string[] accountTypes = { "Savings", "Checking", "Money Market", "Certificate of Deposit", "Retirement" };
                return accountTypes[random.Next(0, accountTypes.Length)];
            }
            static DateTime GenerateRandomDateOpened()
            {
                DateTime startDate = new DateTime(DateTime.Today.Year - MaxYearsBack, 1, 1);
                int daysRange = (DateTime.Today - startDate).Days;
                DateTime randomDate = startDate.AddDays(random.Next(daysRange));
                if (randomDate.Year == DateTime.Today.Year && randomDate >= DateTime.Today)
                {
                    randomDate = randomDate.AddDays(-1);
                }
                return randomDate;
            }
        }
    }

    ```

## Resumen

En esta demostración, has utilizado GitHub Copilot Chat para generar sugerencias que te ayuden a mejorar la confiabilidad y el rendimiento del código en una aplicación de ejemplo. Ha desarrollado mensajes que dirigen a GitHub Copilot para proporcionar sugerencias que mejoran el control de excepciones, reducen problemas inesperados y mejoran la compatibilidad con pruebas unitarias. También ha creado avisos que se centran en mejorar el rendimiento con tareas o métodos asincrónicos.

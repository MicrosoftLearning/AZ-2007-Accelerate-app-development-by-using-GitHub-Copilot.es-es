---
demo:
  title: 'Demostración: Mejora de la calidad del código con GitHub Copilot Chat'
  module: 'Module 5: Implement code improvements using GitHub Copilot tools'
---

# Demostración: Mejora de la calidad del código con GitHub Copilot Chat

## Instrucciones

Las actividades de demostración están diseñadas para un entorno que incluye los siguientes recursos:

- Visual Studio Code.
- Extensión del kit de desarrollo de C# para Visual Studio Code.
- Las extensiones de GitHub Copilot y GitHub Copilot Chat para Visual Studio Code. Se requiere una cuenta de GitHub con una suscripción activa para GitHub Copilot.
- Proyectos de código de ejemplo creados con C#.

**NOTA**: Se recomienda que los instructores consideren usar su propia cuenta de GitHub y la suscripción a GitHub Copilot para las demostraciones. Esto te permitirá controlar y personalizar el entorno de desarrollo. También harás que sea más fácil ajustar las demostraciones para adaptarlas a las necesidades de tus aulas.

**IMPORTANTE**: Si decides ejecutar las demostraciones en el entorno de laboratorio hospedado en lugar de en el equipo instructor, puedes descomprimir las aplicaciones de ejemplo en el entorno hospedado. Tendrás que configurar las extensiones de GitHub Copilot en el entorno hospedado para poder ejecutar las demostraciones. Es posible que el entorno hospedado sea más lento que el entorno local, por lo que es posible que tengas que ajustar el ritmo de las demostraciones según proceda.

### Presentación de la demostración

El término "calidad del código" hace referencia a la calidad general del código base, incluida la legibilidad, el mantenimiento y la modularidad. La calidad del código es una medida de lo "bien estructurado" que es el código y de la facilidad con la que se puede entender, mantener y ampliar.

> [!IMPORTANT]
> Explica a los alumnos que esta demostración no trata sobre los procedimientos recomendados para desarrollar código de alta calidad. En su lugar, se centra en cómo usar GitHub Copilot Chat para generar sugerencias para mejorar la calidad del código en una aplicación de ejemplo. Las sugerencias no representan procedimientos recomendados ni soluciones integrales para el desarrollo de código de alta calidad. Los desarrolladores deben usar su criterio y experiencia para evaluar e implementar las sugerencias proporcionadas por el chat de GitHub Copilot. La implementación de sugerencias propuestas por GitHub Copilot no reemplaza la necesidad de realizar revisiones y pruebas exhaustivas de código.

En las secciones siguientes se proporciona información general sobre la refactorización del código y la calidad del código que los alumnos deben tener en cuenta.

#### Refactorización de código y código de alta calidad

La refactorización de código es el proceso de reestructuración del código existente sin cambiar su comportamiento externo. El objetivo de la refactorización de código es mejorar la estructura interna del código base, lo que facilita la comprensión, el mantenimiento y la ampliación. La refactorización de código puede ayudarle a generar código de alta calidad mejorando la legibilidad, reduciendo la complejidad, mejorando la modularidad y aumentando la reutilización. Cada uno de estos factores ayuda a crear un código base más fácil de administrar y mantener.

Los desarrolladores deben tener en cuenta los siguientes factores al trabajar en mejoras en la calidad del código:

- Legibilidad: Mejorar la legibilidad del código puede facilitar la comprensión de los desarrolladores.
- Complejidad: Reducir la complejidad del código facilita la comprensión, administración y mantenimiento del código.
- Modularidad y reutilización: Dividir el código en módulos o componentes más pequeños y reutilizables puede facilitar la administración y el mantenimiento del código.

Los factores enumerados anteriormente representan tres áreas comunes que los desarrolladores identifican al analizar la calidad del código. Otros factores que se pueden asociar con la calidad del código son:

- Capacidad de prueba: La facilidad con la que se puede probar el código para asegurarse de que funciona correctamente. A menudo, un producto de buen diseño y modularidad.
- Extensibilidad: La facilidad con la que se puede ampliar o mejorar el código para agregar nuevas características o funcionalidades. A menudo, un producto de buen diseño y modularidad.

La calidad del código no es el único factor que los desarrolladores consideran durante las revisiones del código. Estos son algunos factores más que los desarrolladores suelen evaluar además de la calidad del código:

- Confiabilidad: La capacidad del código para realizar sus funciones previstas en condiciones especificadas.
- Rendimiento: Con qué eficacia se ejecuta el código.
- Seguridad: La capacidad del código para proteger los datos y los recursos frente al acceso o modificación no autorizados.
- Escalabilidad: La capacidad del código para controlar mayores cargas de trabajo o el crecimiento en el futuro.
- Facilidad de uso: La facilidad con la que los desarrolladores o los usuarios finales pueden usar el código.
- Portabilidad: La capacidad del código para ejecutarse en diferentes plataformas o entornos.

> [!NOTE]
> Las dos unidades siguientes de este módulo tratan sobre cómo mejorar la confiabilidad, el rendimiento y la seguridad del código mediante GitHub Copilot Chat.

La mejora de la calidad del código suele considerarse un precursor de la adición de nuevas características o mejoras. Debes considerar las mejoras en la calidad del código antes de trabajar en la confiabilidad, rendimiento o seguridad del código.

En esta demostración, usarás GitHub Copilot Chat para generar sugerencias que te ayuden a mejorar la calidad del código en una aplicación de ejemplo.

### Desarrollo de mensajes para chat de GitHub Copilot

Reitera la importancia de crear buenas indicaciones.

Las solicitudes que escriba para GitHub Copilot Chat deben proporcionar un *contexto* y una *intención* claramente definidos. La parte de *intención* de la solicitud describe el objetivo que quiere lograr. Por ejemplo, puede pedir a GitHub Copilot que "se refactorice para mejorar la modularidad del código". La parte de *contexto* de la solicitud indica a GitHub Copilot qué recursos se deben tener en cuenta. Por ejemplo, puede que quiera que GitHub Copilot tenga en cuenta todo el área de trabajo, pero que se centre en una sección de código o archivo específica. Tenga en cuenta las siguientes sugerencias al desarrollar las solicitudes:

- Defina un contexto externo cuyo ámbito esté en un nivel superior al código que desea actualizar. Por ejemplo, si desea refactorizar un método, especifique la clase o el archivo que contiene el método como contexto externo. Identifique el método como un contexto interno.
- Use participantes de chat y variables de chat para ayudar a especificar el contexto. Puede usar las variables de chat `#file:` y `#selection` para identificar el código específico en el que se centra. También puede incluir el área de trabajo completa (`@workspace`) cuando corresponda. Supongamos que desea refactorizar un método en un archivo específico. Puede usar la variable de chat `#file:` para indicar a GitHub Copilot qué archivo examinar. Puede seleccionar el método en el editor y usar la variable de chat `#selection` para indicar a GitHub Copilot qué código desea refactorizar. También puede usar la variable de chat `@workspace` para indicar a GitHub Copilot que tenga en cuenta todo el área de trabajo. Para reforzar el contexto especificado, haga referencia a la selección o archivo en la parte del lenguaje natural de la solicitud. Por ejemplo, podría decir: "¿Cómo puedo mejorar la legibilidad del código seleccionado?"
- La intención debe ser clara y concreta, y debe especificar el aspecto de la calidad del código que desea mejorar. Por ejemplo, podría preguntar a GitHub Copilot Chat "¿Cómo puedo mejorar la modularidad del código seleccionado?"

Durante esta parte de la demostración, revisarás el proyecto **APL2007M5BankAccount** y crearás tres indicaciones para GitHub Copilot Chat. Las solicitudes se centran en mejorar la legibilidad, el mantenimiento y la modularidad del código.

Sigue estos pasos para completar esta parte de la demostración:

1. Abra la aplicación de ejemplo **APL2007M5BankAccount** en Visual Studio Code.

1. Abra el archivo **Program.cs** y revise el código.

    Este programa es una aplicación de consola que simula un sistema bancario. Estas son las características clave:

    - El método Main: Este método es el punto de entrada de la aplicación. Crea cuentas bancarias y usa las cuentas para simular transacciones.

    - Constantes: El programa define varias constantes por encima de la clase Program. Las constantes incluyen cosas como: el número de cuentas que se van a crear, el número de transacciones que se van a simular y los límites de transacción.

1. Dedique un minuto a escribir algunas solicitudes que puede usar para mejorar la legibilidad, el mantenimiento y la modularidad del código.

    Para el proyecto BankAccount, debe adjuntar los archivos BankAccount.cs o Program.cs al contexto chat. Las solicitudes podrían ser similares a los ejemplos siguientes:

    Solicitud: `@workspace /explain How can I improve the readability of the [selected code]?`

    Solicitud: `@workspace /explain #selection How can I improve the maintainability of the [selected code]?`

    Solicitud: `@workspace /explainHow can I improve the modularity of the [selected code]?`

    Solicitud: `#selection How can I refactor the [selected code] to improve modularity?`

    Solicitud: `@workspace /explain What are some options for simplifying the [selected code]?`

1. Crea tres indicaciones para usarlas durante el resto de la demostración.

### Refactorice el código mediante GitHub Copilot Chat

Puede usar GitHub Copilot Chat para sugerir actualizaciones de código que refactoricen y mejoren el código. Es importante comprender el código y sus objetivos antes de tomar una decisión sobre cómo refactorizar la aplicación.

Las sugerencias que proporciona GitHub Copilot Chat deben revisarse cuidadosamente. Tenga en cuenta qué sugerencias respaldan sus objetivos antes de implementarlas. Para esta demostración, el tiempo también puede ser un factor en la decisión de qué sugerencias implementar.

Sigue estos pasos para completar esta parte de la demostración:

1. Dedique un minuto a revisar los métodos incluidos en el archivo Program.cs.

    - Método CreateBankAccounts: Este método crea un número especificado de cuentas bancarias con saldos iniciales aleatorios, nombres de titulares de cuenta, tipos de cuenta y fechas de apertura. Usa un bloque try-catch para controlar las excepciones que pueden producirse durante la creación de la cuenta.

    - Método SimulateTransactions: Este método simula un número especificado de transacciones en una lista de cuentas bancarias. Genera un importe de transacción aleatorio para cada transacción y, a continuación, carga o abona en la cuenta este importe, dependiendo de si la cantidad es positiva o negativa. Usa un bloque try-catch para controlar las excepciones que pueden producirse durante las transacciones.

    - Método SimulateTransfers: Este método es idéntico al método SimulateTransactions. Parece estar pensado para simular transferencias entre cuentas, pero actualmente, simplemente simula transacciones en cuentas individuales.

    - Método GenerateRandomDollarAmount: Este método genera un importe en dólares aleatorio dentro de un intervalo especificado. Usa una fórmula diferente para generar el importe en función de si la cantidad es para un saldo de cuenta o una transacción.

    - Método GenerateRandomAccountHolder: Este método selecciona un nombre de titular de cuenta aleatorio de una lista predefinida de nombres.

    - Método GenerateRandomAccountType: Este método selecciona un tipo de cuenta aleatorio de una lista predefinida de tipos.

    - Método GenerateRandomDateOpened: Este método genera una fecha aleatoria dentro de un intervalo de años especificado a partir de la fecha actual.

1. Asegúrese de que el proyecto se crea y ejecuta sin errores.

1. Elija la primera de las solicitudes que preparó.

1. Seleccione el código que desea mejorar y, a continuación, abra la vista Chat.

1. En la vista Chat, use el botón **Adjuntar contexto** para agregar archivos pertinentes al contexto de chat y, a continuación, escriba el mensaje.

    También puedes demostrar el uso de una operación de arrastrar y colocar para adjuntar archivos desde la vista Explorador de soluciones al contexto de Chat.

1. Revise las sugerencias proporcionadas por GitHub Copilot Chat.

    Por ejemplo, suponga que completa las siguientes acciones:

    - Decide trabajar en el archivo Program.cs.
    - Elegir la siguiente solicitud: `@workspace /explain #selection How can I improve the readability of the GenerateRandomBalance, GenerateRandomAccountHolder, GenerateRandomAccountType, and GenerateRandomDateOpened methods?`
    - Abra el archivo Program.cs y seleccione los métodos siguientes: `GenerateRandomBalance`, `GenerateRandomAccountHolder`, `GenerateRandomAccountType`, `GenerateRandomDateOpened`.
    - Abra la vista Chat y adjunte el archivo Program.cs al contexto chat.
    - Escribir la solicitud en la vista Chat.

    Una vez que ha completado estas acciones, GitHub Copilot Chat sugiere actualizaciones similares a la siguiente respuesta:

    *Para mejorar la legibilidad de estos métodos, puede seguir estos pasos:*

    *1. Extrae código repetido en métodos independientes: El objeto Random se crea varias veces en diferentes métodos. Puedes crear un objeto Random estático en el nivel de clase y usarlo en todos los métodos. Esto no solo mejoraría la legibilidad, sino que también proporcionaría una mejor aleatoriedad.*

    `private static readonly Random random = new Random();`

    *2. Usa nombres de variable significativos: El nombre `range` de la variable en el método GenerateRandomDateOpened es un poco impreciso. Se podría usar un nombre más descriptivo, como daysRange.*

    *3. Agregue comentarios: Aunque el código se explica principalmente por sí solo, agregar comentarios para explicar lo que hace cada método puede ser útil para otros desarrolladores que leen el código.*

    *4. Utiliza constantes para números mágicos: En el método GenerateRandomDateOpened, el número `10` se utiliza para representar el número de años hacia atrás que puede tener la fecha de inicio. Esto se podría extraer en una constante con un nombre descriptivo, como `MaxYearsBack`.*

    *5. Usa la palabra clave var: En C#, puedes usar la palabra clave var cuando el lado derecho de la asignación hace que el tipo sea obvio. Esto puede hacer que el código sea más limpio y fácil de leer.*

   *Este es el aspecto que podría tener el código después de estas mejoras:*

    ```csharp

    private static readonly Random random = new Random();
    private const int MaxYearsBack = 10;
    static double GenerateRandomBalance(double min, double max)
    {
        double balance = random.NextDouble() * (max - min) + min;
        return Math.Round(balance, 2);
    }
    static string GenerateRandomAccountHolder()
    {
        string[] accountHolderNames = {  /* names here */  };
        var accountHolderName = accountHolderNames[random.Next(0, accountHolderNames.Length)];
        return accountHolderName;
    }
    static string GenerateRandomAccountType()
    {
        string[] accountTypes = {  /* types here */  };
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

    ```

    > [!IMPORTANT]
    > Observe los valores de marcador de posición (como `/* types here */`) en los métodos `GenerateRandomAccountHolder` y `GenerateRandomAccountType`. GitHub Copilot Chat reemplaza ocasionalmente los detalles del código por marcadores de posición. Estos son fáciles de detectar si presta atención. Deberá reemplazar los valores de marcador de posición por valores de la aplicación al implementar una actualización. Si ve marcadores de posición, debe realizar una copia del código existente antes de implementar las sugerencias de actualización. Si el bloque de código sugerido se alinea con el código de la aplicación, puede usar un comentario de bloque para comentar el código existente y, a continuación, usar el botón **Insertar en cursor** de la vista Chat para implementar las actualizaciones sugeridas sin crear un conflicto de nomenclatura. Una vez que compruebe que la actualización sugerida funciona según lo previsto, puede quitar el comentario de bloque.

1. Implemente las actualizaciones sugeridas que ayudan a mejorar la legibilidad, el mantenimiento y la modularidad del código.

    Si ha usado comentarios de bloque para comentar el código existente, puede usar **Insertar en el cursor** de la vista Chat para insertar las actualizaciones sugeridas. También puede usar la opción Copiar y pegar la actualización en la ubicación que prefiera.

    Tenga en cuenta los estándares de codificación y las directivas implementadas en el área de trabajo antes de elegir qué sugerencias de actualización implementar.

1. Para asegurarse de que no se cometieron errores al implementar las actualizaciones, compile y ejecute la solución antes de continuar.

1. Escriba la segunda solicitud y revise las actualizaciones propuestas por GitHub Copilot Chat.

1. Revise las sugerencias proporcionadas por GitHub Copilot Chat.

    Por ejemplo, suponga que completa las siguientes acciones:

    - Implemente las actualizaciones sugeridas por GitHub Copilot Chat para la primera solicitud de ejemplo.
    - Decide seguir trabajando en el archivo Program.cs.
    - Elija la siguiente solicitud: `@workspace /explain How can I improve the maintainability of the Main, GenerateRandomBalance, GenerateRandomAccountHolder, GenerateRandomAccountType, and GenerateRandomDateOpened methods?`.
    - Seleccione los métodos siguientes: `Main`, `GenerateRandomBalance`, `GenerateRandomAccountHolder`, `GenerateRandomAccountType`, `GenerateRandomDateOpened`.
    - Abra la vista Chat y adjunte el archivo Program.cs al contexto chat.
    - Escribir la solicitud en la vista Chat.

    Una vez que ha completado estas acciones, GitHub Copilot Chat sugiere actualizaciones similares a la siguiente respuesta:

    *Para mejorar la capacidad de mantenimiento de estos métodos, puede seguir estos pasos:*

    *1. Separación de intereses: El método Main está haciendo muchas cosas: crear cuentas, simular transacciones y simular transferencias. Podrían dividirse en métodos independientes para mejorar la legibilidad y el mantenimiento.*

    *2. Control de errores: El código usa una excepción general para el control de errores. Sería mejor crear excepciones personalizadas específicas de la aplicación. Esto facilitaría la comprensión y el control de errores.*

    *3. Números mágicos: El código contiene números mágicos (como 20 para el número de cuentas, 100 para el número de transacciones, etc.). Deben reemplazarse por constantes con nombre.*

    *4. Duplicación de código: El código para generar valores aleatorios se duplica en varios lugares. Esto podría refactorizarse en una clase de utilidad o en métodos.*

    ```csharp

    class Program
    {
        private static readonly Random random = new Random();
        private const int MaxYearsBack = 10;
        private const int NumberOfAccounts = 20;
        private const int NumberOfTransactions = 100;
        static void Main(string[] args)
        {
            List<BankAccount> accounts = CreateBankAccounts(NumberOfAccounts);
            SimulateTransactions(accounts, NumberOfTransactions);
            SimulateTransfers(accounts);
        }
        static List<BankAccount> CreateBankAccounts(int numberOfAccounts)
        {
            List<BankAccount> accounts = new List<BankAccount>();
            int createdAccounts = 0;
            while (createdAccounts < numberOfAccounts)
            {
                try
                {
                    // same code as before...
                }
                catch (Exception ex)
                {
                    Console.WriteLine($"Account creation failed: {ex.Message}");
                }
            }
            return accounts;
        }
        static void SimulateTransactions(List<BankAccount> accounts, int numberOfTransactions)
        {
            // same code as before...
        }
        static void SimulateTransfers(List<BankAccount> accounts)
        {
            // same code as before...
        }
        // same helper methods as before...
    }

    ```

1. Revise las sugerencias proporcionadas por GitHub Copilot Chat.

1. Implemente las actualizaciones sugeridas que ayudan a mejorar la legibilidad, mantenimiento y modularidad del código.

    Si ha usado comentarios de bloque para comentar el código existente, puede usar **Insertar en el cursor** de la vista Chat para insertar las actualizaciones sugeridas. También puede usar la opción Copiar y pegar la actualización en la ubicación que prefiera.

1. Para asegurarse de que los cambios no introdujeron ningún error, compile y ejecute la solución antes de continuar.

1. Escriba la tercera solicitud y, a continuación, revise las sugerencias.

    Por ejemplo, suponga que completa las siguientes acciones:

    - Implemente las actualizaciones sugeridas por GitHub Copilot Chat para los mensajes primero y segundo.
    - Decide seguir trabajando en el archivo Program.cs.
    - Elija la siguiente solicitud: `@workspace /explain How can I improve the modularity of the Program.cs file?`.
    - Seleccione el código siguiente: Seleccione todo el archivo Program.cs.
    - Abra la vista Chat y adjunte el archivo Program.cs al contexto chat.
    - Escribir la solicitud en la vista Chat.

    Una vez que ha completado estas acciones, GitHub Copilot Chat sugiere actualizaciones similares a la siguiente respuesta:

    *Para mejorar la modularidad del archivo Program.cs, puede seguir estos pasos:*

    *1. Separar los intereses: La clase `Program` está haciendo demasiado. Está creando cuentas, simulando transacciones y generando datos aleatorios. Cada una de estas responsabilidades podría ser de una clase independiente. Por ejemplo, podrías tener una clase `BankAccountFactory` responsable de crear cuentas bancarias, una clase `TransactionSimulator` para simular transacciones y una clase `RandomDataGenerator` para generar datos aleatorios.*

    *2. Usar interfaces: Las interfaces se pueden usar para definir un contrato para las clases. Esto puede hacer que el código sea más flexible y fácil de probar. Por ejemplo, podrías definir una interfaz `IAccountFactory` con un método `Create` y, a continuación, hacer que `BankAccountFactory` implemente esta interfaz.*

    *3. Números mágicos: Hay varios "números mágicos" en el código (como 10, 50 000, -500, 500, etc.). Estos números deben reemplazarse por constantes con nombre para que el código sea más legible y fácil de mantener.*

    *4. Duplicación: Los métodos `SimulateTransactions` y `SimulateTransfers` tienen código casi idéntico. Esta duplicación podría eliminarse mediante la creación de un método común al que llamen ambos métodos.*

   *Este es un ejemplo de cómo podría refactorizar el método CreateBankAccounts:*

    **Fragmento de código A: Usar interfaces**

    ```csharp

    interface IAccountFactory
    {
        BankAccount Create(int index);
    }
    class BankAccountFactory : IAccountFactory
    {
        private readonly RandomDataGenerator _randomDataGenerator;
        public BankAccountFactory(RandomDataGenerator randomDataGenerator)
        {
            _randomDataGenerator = randomDataGenerator;
        }
        public BankAccount Create(int index)
        {
            double initialBalance = _randomDataGenerator.GenerateRandomBalance(10, 50000);
            string accountHolderName = _randomDataGenerator.GenerateRandomAccountHolder();
            string accountType = _randomDataGenerator.GenerateRandomAccountType();
            DateTime dateOpened = _randomDataGenerator.GenerateRandomDateOpened();
            return new BankAccount($"Account {index + 1}", initialBalance, accountHolderName, accountType, dateOpened);
        }
    }
    // In the `Program` class, you would then use the `IAccountFactory` to create accounts:
    interface IAccountFactory
    {
        BankAccount Create(int index);
    }
    class BankAccountFactory : IAccountFactory
    {
        private readonly RandomDataGenerator _randomDataGenerator;
        public BankAccountFactory(RandomDataGenerator randomDataGenerator)
        {
            _randomDataGenerator = randomDataGenerator;
        }
        public BankAccount Create(int index)
        {
            double initialBalance = _randomDataGenerator.GenerateRandomBalance(10, 50000);
            string accountHolderName = _randomDataGenerator.GenerateRandomAccountHolder();
            string accountType = _randomDataGenerator.GenerateRandomAccountType();
            DateTime dateOpened = _randomDataGenerator.GenerateRandomDateOpened();
            return new BankAccount($"Account {index + 1}", initialBalance, accountHolderName, accountType, dateOpened);
        }
    }

    ```

    **Fragmento de código B: Duplicación**

    ```csharp

    static void SimulateOperations(List<BankAccount> accounts, int numberOfOperations, Action<BankAccount, double> operation)
    {
        foreach (BankAccount account in accounts)
        {
            for (int i = 0; i < numberOfOperations; i++)
            {
                double transactionAmount = GenerateRandomBalance(-500, 500);
                try
                {
                    operation(account, transactionAmount);
                    Console.WriteLine($"Operation: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                }
                catch (Exception ex)
                {
                    Console.WriteLine($"Operation failed: {ex.Message}");
                }
            }
            Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
        }
    }
    // Then you can call this method like this:
    SimulateOperations(accounts, NumberOfTransactions, (account, amount) => {
        if (amount >= 0)
        {
            account.Credit(amount);
        }
        else
        {
            account.Debit(-amount);
        }
    });

    ```

    > [!NOTE]
    > No es necesario implementar las sugerencias de actualización que GitHub Copilot generó a partir de la tercera solicitud. Revisar las sugerencias puede proporcionar información sobre cómo progresa el proceso de mejora del código.

Tus dos demostraciones siguientes tratan los temas siguientes:

- Mejora de la confiabilidad y el rendimiento del código mediante GitHub Copilot Chat
- Mejora de la seguridad del código con GitHub Copilot Chat

## Resumen

En esta demostración, has usado GitHub Copilot Chat para generar sugerencias que te ayudan a mejorar la calidad del código en una aplicación de ejemplo. Ha desarrollado solicitudes que se centran en mejorar la legibilidad, mantenimiento y modularidad del código. Ha revisado las sugerencias proporcionadas por GitHub Copilot Chat e implementado las actualizaciones que ayudaron a mejorar la calidad del código. También ha considerado sugerencias adicionales que podrían mejorar aún más el código.

---
demo:
  title: 'Demostración: Mejora de la seguridad del código con GitHub Copilot Chat'
  module: 'Module 5: Implement code improvements using GitHub Copilot tools'
---

# Demostración: Mejora de la seguridad del código con GitHub Copilot Chat

## Instrucciones

Las actividades de demostración están diseñadas para un entorno que incluye los siguientes recursos:

- Visual Studio Code.
- Extensión del kit de desarrollo de C# para Visual Studio Code.
- Las extensiones de GitHub Copilot y GitHub Copilot Chat para Visual Studio Code. Se requiere una cuenta de GitHub con una suscripción activa para GitHub Copilot.
- Proyectos de código de ejemplo creados con C#.

**NOTA**: Se recomienda que los instructores consideren usar su propia cuenta de GitHub y la suscripción a GitHub Copilot para las demostraciones. Esto te permitirá controlar y personalizar el entorno de desarrollo. También harás que sea más fácil ajustar las demostraciones para adaptarlas a las necesidades de tus aulas.

**IMPORTANTE**: Si decides ejecutar las demostraciones en el entorno de laboratorio hospedado en lugar de en el equipo instructor, puedes descomprimir las aplicaciones de ejemplo en el entorno hospedado. Tendrás que configurar las extensiones de GitHub Copilot en el entorno hospedado para poder ejecutar las demostraciones. Es posible que el entorno hospedado sea más lento que el entorno local, por lo que es posible que tengas que ajustar el ritmo de las demostraciones según proceda.

### Presentación de la demostración

La seguridad del código hace referencia a las medidas adoptadas para proteger el software contra el acceso no autorizado, las infracciones de datos y otras amenazas de seguridad. La seguridad del código es un aspecto esencial del desarrollo de software que implica proteger aplicaciones y sistemas frente a amenazas de seguridad. Mejorar la seguridad del código puede ayudarle a proteger sus aplicaciones y sistemas frente a amenazas de seguridad.

> [!IMPORTANT]
> Explica a los alumnos que esta demostración no trata sobre los procedimientos recomendados para desarrollar código seguro. En su lugar, se centra en cómo utilizar el chat GitHub Copilot para generar sugerencias para mejorar la seguridad del código en una aplicación de ejemplo. Las sugerencias no representan procedimientos recomendados ni soluciones completas para desarrollar código seguro. Los desarrolladores deben usar su criterio y experiencia para evaluar e implementar las sugerencias proporcionadas por GitHub Copilot Chat. La implementación de sugerencias propuestas por GitHub Copilot no reemplaza la necesidad de realizar revisiones y pruebas exhaustivas de código.

#### Seguridad de código

Garantizar la seguridad del código es responsabilidad de todos, no solo el desarrollador. Sin embargo, los desarrolladores desempeñan un papel fundamental asegurándose de que el código que escribe siguen las prácticas de codificación seguras. Las prácticas de codificación seguras ayudan a garantizar que los atacantes no puedan aprovechar las vulnerabilidades de software. Siguiendo las prácticas de codificación seguras, los desarrolladores pueden ayudar a proteger el software frente a amenazas de seguridad y asegurarse de que es seguro y confiable.

En las secciones siguientes se proporciona información general sobre los procesos de seguridad del código que los alumnos deben tener en cuenta.

##### Evaluación de la seguridad del código mediante un enfoque completo

Al evaluar la seguridad del código, es importante tener en cuenta un enfoque completo que abarque varios aspectos del ciclo de vida de desarrollo de software. Estas son algunas consideraciones clave:

- Prácticas de codificación seguras: cumplimiento de estándares y directrices de codificación seguros para evitar vulnerabilidades.
- Herramientas de análisis de código: uso de herramientas de análisis de código estático y dinámico para detectar errores de seguridad.
- Administración de dependencias: asegurar que las bibliotecas y dependencias de terceros están actualizadas y libres de vulnerabilidades conocidas.
- Autenticación y autorización: implementación de mecanismos sólidos de autenticación y autorización para proteger contra el acceso no autorizado.
- Protección de datos: cifrado de datos confidenciales tanto en reposo como en tránsito para evitar infracciones de datos.
- Tratamiento de errores: desarrollar procedimientos de control de errores seguros que no exponen información confidencial.
- Pruebas de seguridad: realizar pruebas exhaustivas de seguridad, incluidas las pruebas de penetración y las evaluaciones de vulnerabilidades.
- Cumplimiento: asegurar que el código cumple con las normas y regulaciones de seguridad pertinentes.
- Educación y aprendizaje: proporcionar a los desarrolladores formación y educación de seguridad continuas para mantenerlos informados sobre las amenazas y los procedimientos recomendados más recientes.
- Respuesta ante incidentes: tener preparado un plan de respuesta a incidentes bien definido. Si se produce una infracción de seguridad, el plan de respuesta a incidentes debe ser accesible.

Teniendo en cuenta estos factores e integrando los procedimientos recomendados de seguridad en el proceso de desarrollo, contribuye a la creación de contenido y aplicaciones seguros.

##### Realización de revisiones de seguridad de código

Al trabajar para asegurarse de que el código es seguro, los desarrolladores deben revisar los siguientes aspectos de su código:

- Corrección: Compruebe que el código está libre de errores lógicos y defectos que podrían provocar vulnerabilidades de seguridad.
- Seguridad: asegúrate de que el código cumple los procedimientos recomendados de seguridad y no contiene vulnerabilidades.
- Diagnóstico: incluye las funcionalidades de registro y diagnóstico adecuadas para detectar y responder a incidentes de seguridad.
- Errores de diseño o limitaciones: revisa el diseño del código para asegurarte de que no haya errores o limitaciones que se puedan aprovechar.
- Escala y rendimiento: ten en cuenta el rendimiento y la escalabilidad del código. El rendimiento y la escalabilidad deficientes pueden afectar a la seguridad en escenarios de alta carga.
- Localización: asegúrate de que el código controla de forma segura diferentes configuraciones regionales, lo que puede afectar al formato y la representación de datos.
- Accesibilidad (UX): comprueba que las medidas de seguridad no afectan negativamente a la accesibilidad y la experiencia del usuario.
- Prueba: revisa las estrategias de prueba y asegúrate de que las pruebas de seguridad son exhaustivas y cubren todos los aspectos del código.
- Instrumentación: asegúrate de que el código se instrumenta de forma que admita la supervisión de seguridad y la detección de amenazas.
- Convenciones de estilo de código y coherencia: Mantenga un estilo de codificación coherente que siga las directrices y estándares de codificación seguros.

Cuando los desarrolladores revisan estos aspectos de su código, pueden mejorar significativamente la seguridad de su código. Las revisiones de código ayudan a los desarrolladores a contribuir a la posición de seguridad general del software que desarrollan.

##### Análisis de vulnerabilidades de código

Algunas partes de una aplicación son más vulnerables a los ataques de seguridad y es fundamental centrarse en proteger estas áreas. Estas son algunas de las áreas más vulnerables:

- Puntos de integración: Las revisiones de diseño de seguridad deben realizarse para puntos de integración con equipos de productos dependientes. Las revisiones son esenciales para los productos que controlan datos de alto impacto empresarial (HBI) o aplicaciones y servicios empresariales.
- Sistemas internos: Los incidentes internos son una causa común de infracciones de seguridad, especialmente en pequeñas empresas.
- Sistemas de correo electrónico: Los servidores de correo electrónico, especialmente aquellos que no son compatibles o no se han registrado, son vulnerables de forma persistente.
- Bases de datos y almacenamiento: Las bases de datos que esperan que los datos confidenciales se cifren previamente antes de que el almacenamiento pueda ser vulnerable si los datos no están cifrados según lo previsto.
- Entorno en tiempo de ejecución: Las tecnologías como la autoprotección de aplicaciones en tiempo de ejecución (RASP) pueden detectar ataques en una aplicación en tiempo real, lo que hace que el entorno en tiempo de ejecución sea un área crítica para proteger.
- Aplicaciones web: A menudo, los atacantes usan métodos como inyección de código SQL, scripting entre sitios (XSS) y desbordamientos de búfer.
- <bpt i="1000001" x="1000001" type="formatting">{b&gt;</bpt>Puntos de conexión:<ept i="1000001">&lt;b}</ept> Los dispositivos y las aplicaciones corren el riesgo de ataques cibernéticos. Es esencial reducir la superficie expuesta a ataques mediante funcionalidades como mitigación de ransomware, control de aplicaciones, protección web y firewall de red.

Los desarrolladores y los equipos de seguridad deben priorizar estas áreas e implementar medidas de seguridad sólidas para protegerse frente a posibles ataques. Las revisiones periódicas de seguridad, las actualizaciones y el cumplimiento de los procedimientos recomendados pueden ayudar a mitigar estas vulnerabilidades.

##### Búsqueda de errores comunes de seguridad

Los desarrolladores pueden encontrar varios errores de seguridad en su código, lo que puede provocar vulnerabilidades si no se solucionan correctamente. Algunos errores de seguridad típicos incluyen:

- Errores de inyección: Por ejemplo, la inserción de SQL, NoSQL, OS y LDAP, donde los datos que no son de confianza se envían a un intérprete como parte de un comando o consulta.
- Autenticación interrumpida: Cuando la autenticación y la administración de sesiones se implementan incorrectamente, se puede romper la autenticación. Las buenas implementaciones garantizan que los atacantes no pongan en peligro las contraseñas, las claves y los tokens de sesión.
- Exposición de datos sensibles: La protección inadecuada de los datos confidenciales puede provocar la exposición durante la transferencia a través de la red o en reposo.
- Control de acceso roto: Las restricciones que controlan el acceso concedido a los usuarios autenticados no se aplican correctamente.
- Creación de scripts de sitios (XSS): Los errores de XSS se producen cada vez que una aplicación incluye datos que no son de confianza en una página web sin una validación o escape adecuados.
- Deserialización insegura: Esto puede provocar la ejecución remota de código, los ataques de reproducción, los ataques por inyección y los ataques de escalación de privilegios.
- Registro y supervisión insuficientes: El registro y la supervisión insuficientes, junto con la integración faltante o ineficaz con la respuesta a incidentes, permite ataques continuos.
- Referencias directas inseguras a objetos (IDOR): Un tipo de problema de control de acceso que surge cuando una aplicación proporciona acceso directo a objetos en función de la entrada proporcionada por el usuario.
- Falta control de acceso de nivel de función: A veces, una aplicación no protege correctamente los controles de acceso a nivel de función, lo que permite a los atacantes falsificar las solicitudes para acceder a la funcionalidad sin una autorización adecuada.

Muchos otros errores de seguridad se pueden encontrar en el código. Es importante que los desarrolladores usen herramientas y procedimientos recomendados para identificar y corregir estos problemas de forma proactiva.

### Desarrollo de mensajes para chat de GitHub Copilot

Las solicitudes que escriba para GitHub Copilot Chat deben proporcionar un contexto y una intención claramente definidos. Tenga en cuenta las siguientes sugerencias al desarrollar las solicitudes:

- Defina un contexto externo cuyo ámbito esté en un nivel superior al código que desea actualizar. Por ejemplo, si desea mejorar un método, especifique la clase o el archivo que incluye el método como contexto externo. Identifique el método como un contexto interno.
- Use participantes de chat y variables de chat para ayudar a especificar el contexto. Puede usar las variables de chat `#file:` y `#selection` para identificar el código específico en el que se centra. También puede incluir el área de trabajo completa (`@workspace`) cuando corresponda. Consulte la selección de código o archivo en la parte del lenguaje natural del símbolo del sistema.
- La intención debe ser clara, concisa y específica. El mensaje debe especificar el tipo de mejora que desea lograr.

Durante esta parte de la demostración, revisarás el proyecto **APL2007M5BankAccount-Security** y crearás tres indicaciones para GitHub Copilot Chat. Las indicaciones se centran en mejorar la seguridad del código.

Sigue estos pasos para completar esta parte de la demostración:

1. Abra el **proyecto APL2007M5BankAccount-Security** y revise los **archivos de código Program.cs** y **BankAccount.cs**.

    El **archivo Program.cs** contiene el código de una aplicación bancaria sencilla que simula la creación de cuentas bancarias, transacciones y transferencias.

    El **archivo BankAccount.cs** contiene el código de la `BankAccount` clase, que representa una cuenta bancaria con funcionalidades básicas, como depósito, retiro y consulta de saldo.

1. Dedica un minuto a describir algunas indicaciones que podrían usarse para mejorar la seguridad del código.

    Para este proyecto, puede utilizar las siguientes indicaciones para generar sugerencias para mejorar la fiabilidad de su código:

    Aviso: `@workspace /explain How can I implement authentication in the [selected code]?` (adjuntar BankAccount.cs al contexto de Chat)

    Aviso: `@workspace /explain How can I protect sensitive data in the [selected code]?` (adjuntar BankAccount.cs al contexto de Chat)

    Aviso: `@workspace /explain How can I implement logging of suspicious account activities of the [selected code]?` (adjuntar BankAccount.cs al contexto de Chat)

    Aviso: `@workspace /explain How can I improve the security of exception handling in the [selected code]?` (adjuntar BankAccount.cs al contexto de Chat)

    Aviso: `@workspace /explain How can I improve the security of the [selected code]?` (adjuntar BankAccount.cs al contexto de Chat)

    Aviso: `@workspace /explain How can I improve the security of the [selected code]?` (adjuntar Program.cs al contexto de Chat)

1. Selecciona tres indicaciones para usarlas durante el resto de la demostración.

    Intente seleccionar dos mensajes que solucione los problemas de seguridad en el archivo BankAccount.cs y otro para el archivo Program.cs. En esta demostración, la clase BankAccount representa el "producto". El archivo Program.cs usa la clase BankAccount para simular las actividades y transacciones de la cuenta.

### Mejorar la fiabilidad del código de la clase BankAccount utilizando GitHub Copilot Chat

Desarrollar código seguro es esencial para cualquier proyecto de software. El nivel de seguridad requerido depende de la naturaleza de la aplicación y de los datos que procesa.

En esta demostración, usarás GitHub Copilot Chat para generar sugerencias para mejorar la seguridad de la clase BankAccount en el proyecto **APL2007M5BankAccount-Security**.

El chat de GitHub Copilot se puede usar para ayudar a mejorar la seguridad del código. Las indicaciones pueden dirigir a GitHub Copilot para generar sugerencias para mejorar la autenticación, la protección de datos, el registro y docenas de otros temas. También puede crear avisos de amplio alcance que soliciten sugerencias generales para mejorar la seguridad del código. Una combinación de indicaciones específicas y generales puede ayudarle a identificar las áreas que necesitan mejorar y a aplicar los cambios necesarios.

> [!TIP]
> La implementación y las pruebas de las actualizaciones sugeridas tardan tiempo, y el tiempo puede ser un factor durante esta demostración. Seleccionar indicaciones que se centren en áreas específicas de mejora puede ayudarle a gestionar su tiempo. Las indicaciones demasiado amplias pueden generar un gran número de sugerencias o sugerencias complejas difíciles de evaluar y aplicar en poco tiempo. Una vez que empiece, puede actualizar las solicitudes con detalles más específicos si encuentra que las actualizaciones sugeridas tienen un ámbito demasiado amplio o demasiado complejo.

1. Asegúrese de que el proyecto se construye y ejecuta sin errores.

    Las advertencias son aceptables siempre que se ejecute la aplicación, pero los errores deben resolverse antes de empezar a trabajar con El chat de GitHub Copilot.

1. Abra el archivo BankAccount.cs en Visual Studio Code y seleccione todo el código del archivo.

1. Abra la vista Chat.

1. En la vista Chat, use el botón **Adjuntar contexto** para agregar archivos pertinentes al contexto de chat y, a continuación, escriba el mensaje.

1. Revise las sugerencias proporcionadas por GitHub Copilot Chat.

    Por ejemplo, suponga que completa las siguientes acciones:

    - Abra el archivo BankAccount.cs y seleccione todo el código.
    - Elegir la siguiente solicitud: `@workspace /explain How can I implement authentication in the BankAccount.cs file?`
    - Abra la vista Chat y adjunte los archivos BankAccount.cs y Program.cs al contexto Chat.
    - Escribir la solicitud en la vista Chat.

    GitHub Copilot Chat sugiere actualizaciones similares a la siguiente respuesta:

    *La implementación de la autenticación en este contexto normalmente implicaría agregar un método a la clase BankAccount que comprueba la identidad del titular de la cuenta antes de permitir determinadas operaciones. Esto puede hacerse mediante una contraseña, un PIN o alguna otra forma de autenticación.*

    *Este es un ejemplo sencillo de cómo puede agregar la autenticación basada en contraseña a la clase BankAccount:*

    ```csharp

    public class BankAccount
    {
        // Existing code...
        private string password;
        public BankAccount(string accountNumber, double initialBalance, string accountHolderName, string accountType, DateTime dateOpened, string password)
        {
            // Existing code...
    
            this.password = password;
        }
        public bool Authenticate(string password)
        {
            return this.password == password;
        }
        public void Credit(double amount, string password)
        {
            if (!Authenticate(password))
            {
                throw new Exception("Authentication failed.");
            }
            // Existing code...
        }
        // Similar changes would be made to the Debit, Transfer, and other methods...
    }

    ```

    *En este ejemplo, se agrega una contraseña como parámetro al constructor BankAccount y se almacena en un campo privado. Se agrega un método Authenticate que comprueba si la contraseña proporcionada coincide con la contraseña almacenada. El método Credit (y otros métodos que deben requerir autenticación) se modifica para utilizar una contraseña como argumento y llamar a Authenticate antes de realizar la operación.*

    *Se trata de una forma muy básica de autenticación y no es lo suficientemente segura para las aplicaciones reales. En una aplicación real, te gustaría aplicar valores hash y salt a la contraseña antes de almacenarla, y tendrías que usar métodos seguros para transmitir la contraseña del usuario a la aplicación. También puedes considerar la posibilidad de usar la autenticación en dos fases u otros métodos más seguros.*

1. Implemente las actualizaciones sugeridas que ayudan a mejorar la seguridad del código para la clase `BankAccount`.

    El archivo Program.cs debe actualizarse para usar la contraseña y la autenticación agregadas a la clase BankAccount. Puede usar el chat de GitHub Copilot para generar sugerencias para actualizar el archivo Program.cs.

    1. Seleccione el contenido del archivo de Program.cs, adjunte los archivos Program.cs y BankAccount.cs al contexto chat y, a continuación, escriba el siguiente símbolo del sistema en la vista Chat:

        ```plaintext
        @workspace /Explain How can I update the Program.cs file to use the password and authentication added to BankAccount.cs?
        ```

    1. Revise las sugerencias proporcionadas por GitHub Copilot Chat y, a continuación, implemente las actualizaciones sugeridas.

    1. Para asegurarse de que los cambios no introdujeron ningún error, compile y ejecute la solución antes de continuar.

        Use GitHub Copilot para ayudar a resolver los problemas identificados durante el proceso de compilación.

    > [!IMPORTANT]
    > Asegúrate de que los alumnos comprendan que esta forma de autenticación básica no es lo suficientemente segura para las aplicaciones reales. En una aplicación real, le gustaría aplicar hash y sal a la contraseña antes de almacenarla, y tendría que usar métodos seguros para transmitir la contraseña del usuario a la aplicación. También puede considerar la posibilidad de usar la autenticación en dos fases u otros métodos más seguros.

1. Asegúrese de que la aplicación se compila y se ejecuta antes de continuar.

1. Seleccione todo el código del archivo BankAccount.cs y, a continuación, introduzca su segunda consulta en la vista de chat.

1. Revise las sugerencias proporcionadas por GitHub Copilot Chat.

    Por ejemplo, suponga que completa las siguientes acciones:

    - Abra el archivo BankAccount.cs y seleccione todo el código.
    - Elegir la siguiente solicitud: `@workspace /explain How can I protect account numbers and account holder names in the selected code?`
    - Abra la vista Chat y adjunte los archivos BankAccount.cs y Program.cs al contexto Chat.
    - Escribir la solicitud en la vista Chat.

    GitHub Copilot Chat sugiere actualizaciones similares a la siguiente respuesta:

    *Para proteger datos confidenciales, como números de cuenta y nombres de titulares de cuenta en la clase BankAccount, puede seguir estos pasos:*

    *1. Usar encapsulación:*

    *: Haga que las propiedades confidenciales sean privadas y proporcionen acceso controlado a través de métodos.*

    *2. Cifrar datos confidenciales:*

    *: Use el cifrado para almacenar datos confidenciales de forma segura.*

    *3. Evitar el almacenamiento de texto no cifrado:*

    *: Asegúrese de que los datos confidenciales no se almacenan ni transmiten en texto no cifrado.*

    *Implementación actualizada*

    *Esta es una versión actualizada de BankAccount.cs que usa cifrado para números de cuenta y nombres de titular de cuenta:*

    ```csharp

    using System;
    using System.Security.Cryptography;
    using System.Text;
    namespace BankAccountApp
    {
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
        public class InvalidAccountTypeException : Exception
        {
            public string AccountType { get; }
            public InvalidAccountTypeException(string accountType)
                : base($"Invalid account type: {accountType}.")
            {
                AccountType = accountType;
            }
        }
        public class InvalidAccountNumberException : Exception
        {
            public string AccountNumber { get; }
            public InvalidAccountNumberException(string accountNumber)
                : base($"Invalid account number: {accountNumber}.")
            {
                AccountNumber = accountNumber;
            }
        }
        public class InvalidAccountHolderNameException : Exception
        {
            public string AccountHolderName { get; }
            public InvalidAccountHolderNameException(string accountHolderName)
                : base($"Invalid account holder name: {accountHolderName}.")
            {
                AccountHolderName = accountHolderName;
            }
        }
        public class InvalidDateOpenedException : Exception
        {
            public DateTime DateOpened { get; }
            public InvalidDateOpenedException(DateTime dateOpened)
                : base($"Invalid date opened: {dateOpened}.")
            {
                DateOpened = dateOpened;
            }
        }
        public class InvalidInitialBalanceException : Exception
        {
            public double InitialBalance { get; }
            public InvalidInitialBalanceException(double initialBalance)
                : base($"Invalid initial balance: {initialBalance}.")
            {
                InitialBalance = initialBalance;
            }
        }
        public class InvalidInterestRateException : Exception
        {
            public double InterestRate { get; }
            public InvalidInterestRateException(double interestRate)
                : base($"Invalid interest rate: {interestRate}.")
            {
                InterestRate = interestRate;
            }
        }
        public class InvalidTransferAmountException : Exception
        {
            public double TransferAmount { get; }
            public InvalidTransferAmountException(double transferAmount)
                : base($"Invalid transfer amount: {transferAmount}.")
            {
                TransferAmount = transferAmount;
            }
        }
        public class InvalidCreditAmountException : Exception
        {
            public double CreditAmount { get; }
            public InvalidCreditAmountException(double creditAmount)
                : base($"Invalid credit amount: {creditAmount}.")
            {
                CreditAmount = creditAmount;
            }
        }
        public class InvalidDebitAmountException : Exception
        {
            public double DebitAmount { get; }
            public InvalidDebitAmountException(double debitAmount)
                : base($"Invalid debit amount: {debitAmount}.")
            {
                DebitAmount = debitAmount;
            }
        }
        public class AuthenticationException : Exception
        {
            public AuthenticationException(string message) : base(message) { }
        }
        public class BankAccount
        {
            public enum AccountTypes
            {
                Savings,
                Checking,
                MoneyMarket,
                CertificateOfDeposit,
                Retirement
            }
            private string EncryptedAccountNumber { get; }
            private string EncryptedAccountHolderName { get; }
            public double Balance { get; private set; }
            public AccountTypes AccountType { get; }
            public DateTime DateOpened { get; }
            private const double MaxTransferAmountForDifferentOwners = 500;
            private string Username { get; }
            private string Password { get; }
            public BankAccount(string accountNumber, double initialBalance, string accountHolderName, string accountType, DateTime dateOpened, string username, string password)
            {
                if (accountNumber.Length != 10)
                {
                    throw new InvalidAccountNumberException(accountNumber);
                }
                if (initialBalance < 0)
                {
                    throw new InvalidInitialBalanceException(initialBalance);
                }
                if (accountHolderName.Length < 2)
                {
                    throw new InvalidAccountHolderNameException(accountHolderName);
                }
                if (dateOpened > DateTime.Now)
                {
                    throw new InvalidDateOpenedException(dateOpened);
                }
                EncryptedAccountNumber = Encrypt(accountNumber);
                EncryptedAccountHolderName = Encrypt(accountHolderName);
                Balance = initialBalance;
                AccountType = (AccountTypes)Enum.Parse(typeof(AccountTypes), accountType);
                DateOpened = dateOpened;
                Username = username;
                Password = password;
            }
            public void Credit(double amount)
            {
                if (amount < 0)
                {
                    throw new InvalidCreditAmountException(amount);
                }
                Balance += amount;
            }
            public void Debit(double amount)
            {
                if (amount < 0)
                {
                    throw new InvalidDebitAmountException(amount);
                }
                if (Balance >= amount)
                {
                    Balance -= amount;
                }
                else
                {
                    throw new InsufficientFundsException(amount, Balance);
                }
            }
            public double GetBalance()
            {
                return Balance;
            }
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
                if (Decrypt(EncryptedAccountHolderName) != Decrypt(toAccount.EncryptedAccountHolderName) && amount > MaxTransferAmountForDifferentOwners)
                {
                    throw new Exception("Transfer amount exceeds maximum limit for different account owners.");
                }
            }
            public void PrintStatement()
            {
                Console.WriteLine($"Account Number: {Decrypt(EncryptedAccountNumber)}, Balance: {Balance}");
            }
            public double CalculateInterest(double interestRate)
            {
                if (interestRate < 0)
                {
                    throw new InvalidInterestRateException(interestRate);
                }
                return Balance * interestRate;
            }
            public void Authenticate(string username, string password)
            {
                if (Username != username || Password != password)
                {
                    throw new AuthenticationException("Invalid username or password.");
                }
            }
            private string Encrypt(string plainText)
            {
                using (Aes aes = Aes.Create())
                {
                    aes.Key = Encoding.UTF8.GetBytes("A very strong key"); // Use a secure key
                    aes.IV = Encoding.UTF8.GetBytes("A strong IV123456"); // Use a secure IV
                    ICryptoTransform encryptor = aes.CreateEncryptor(aes.Key, aes.IV);
                    using (var ms = new System.IO.MemoryStream())
                    {
                        using (var cs = new CryptoStream(ms, encryptor, CryptoStreamMode.Write))
                        {
                            using (var sw = new System.IO.StreamWriter(cs))
                            {
                                sw.Write(plainText);
                            }
                        }
                        return Convert.ToBase64String(ms.ToArray());
                    }
                }
            }
            private string Decrypt(string cipherText)
            {
                using (Aes aes = Aes.Create())
                {
                    aes.Key = Encoding.UTF8.GetBytes("A very strong key"); // Use a secure key
                    aes.IV = Encoding.UTF8.GetBytes("A strong IV123456"); // Use a secure IV
                    ICryptoTransform decryptor = aes.CreateDecryptor(aes.Key, aes.IV);
                    using (var ms = new System.IO.MemoryStream(Convert.FromBase64String(cipherText)))
                    {
                        using (var cs = new CryptoStream(ms, decryptor, CryptoStreamMode.Read))
                        {
                            using (var sr = new System.IO.StreamReader(cs))
                            {
                                return sr.ReadToEnd();
                            }
                        }
                    }
                }
            }
        }
    }

    ```

    *Uso:*

    *- Asegúrate de que tienes disponibles las bibliotecas criptográficas necesarias. En el ejemplo anterior se usa el cifrado AES con una clave codificada de forma rígida y IV por motivos de simplicidad. En una aplicación real, debes administrar de forma segura las claves e IV, posiblemente mediante un servicio de administración de claves.*

    > [!IMPORTANT]
    > En una aplicación real, debe administrar de forma segura las claves e IVs, posiblemente mediante un servicio de administración de claves. Los ejemplos proporcionados en este entrenamiento identifican áreas para mejorar, pero no representan procedimientos recomendados para el cifrado seguro. Puede usar GitHub Copilot Chat para buscar sugerencias adicionales para mejorar el cifrado y la protección de datos en la aplicación.

1. No es necesario implementar las actualizaciones sugeridas para el segundo aviso.

    En el ejemplo, las actualizaciones sugeridas ayudarán a mejorar la seguridad de la aplicación, pero requieren una configuración y actualizaciones significativas en el código de Program.cs que está fuera del ámbito de esta demostración.

### Mejora de la seguridad del código de la clase Program mediante GitHub Copilot Chat

1. Abra el archivo BankAccount.cs en Visual Studio Code y seleccione todo el código del archivo.

1. Abra la vista Chat y, a continuación, introduzca la primera consulta que preparó para la clase Programa.

1. Revise las sugerencias proporcionadas por GitHub Copilot Chat.

    Por ejemplo, suponga que completa las siguientes acciones:

    - Abra el archivo Program.cs y seleccione todo el código.
    - Elegir la siguiente solicitud: `@workspace /explain How can I improve the security of the Program.cs file?`
    - Abra la vista Chat y adjunte los archivos BankAccount.cs y Program.cs al contexto Chat.
    - Escribir la solicitud en la vista Chat.

    GitHub Copilot Chat sugiere actualizaciones similares a la siguiente respuesta:

    *Para mejorar la seguridad del archivo Program.cs, debe centrarse en las siguientes áreas:*

    *1. Control de contraseñas seguras:*

    *- Utiliza algoritmos has para crear contraseñas seguras y evita almacenar las contraseñas como texto no cifrado.*
    *- Utiliza una biblioteca como BCrypt.Net para aplicar hash a las contraseñas.*

    *2. Cifrar datos confidenciales:*

    *: Cifrar datos confidenciales, como números de cuenta y nombres de titulares de cuenta.*

    *3. Evitar contraseñas codificadas de forma segura:*

    *- Evita utilizar contraseñas codificadas de forma rígida. En su lugar, genera contraseñas aleatorias seguras o pide a los usuarios que creen sus propias contraseñas aleatorias.*

    *4. Usar generación segura de números aleatorios:*

    *: Use un generador de números aleatorios criptográficomente seguro para generar datos confidenciales.*

    *Implementación actualizada*

    *Esta es una versión actualizada de Program.cs que incorpora estas mejoras:*

    ```csharp

    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Security.Cryptography;
    using System.Text;
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
            static async Task Main()
            {
                List<BankAccount> accounts = CreateBankAccounts(NumberOfAccounts);
                await SimulateTransactionsAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
                await SimulateTransfersAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
            }
            static List<BankAccount> CreateBankAccounts(int numberOfAccounts)
            {
                List<BankAccount> accounts = new();
                int createdAccounts = 0;
                while (createdAccounts < numberOfAccounts)
                {
                    try
                    {
                        double initialBalance = GenerateRandomDollarAmount(true, minAccountStart, maxAccountStart);
                        string accountHolderName = GenerateRandomAccountHolder();
                        string accountType = GenerateRandomAccountType();
                        DateTime dateOpened = GenerateRandomDateOpened();
                        string accountNumber = "102000" + random.Next(1000, 9999).ToString();
                        string username = "user" + createdAccounts;
                        string password = GenerateSecurePassword();
                        BankAccount account = new(accountNumber, initialBalance, accountHolderName, accountType, dateOpened, username, password);
                        accounts.Add(account);
                        createdAccounts++;
                    }
                    catch (ArgumentException ex)
                    {
                        Console.WriteLine($"Account creation failed due to invalid argument: {ex.Message}");
                        // Log the exception
                    }
                    catch (Exception ex)
                    {
                        Console.WriteLine($"Account creation failed: {ex.Message}");
                        // Log the exception
                    }
                    finally
                    {
                        // Any cleanup code would go here.
                    }
                }
                return accounts;
            }
            static async Task SimulateTransactionsAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                var tasks = accounts.Select(async account =>
                {
                    for (int i = 0; i < numberOfTransactions; i++)
                    {
                        double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                        try
                        {
                            account.Authenticate(account.Username, account.Password); // Authenticate before transaction
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
                    }
                    Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                });
                await Task.WhenAll(tasks);
            }
            static async Task SimulateTransfersAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                var tasks = accounts.Select(async account =>
                {
                    for (int i = 0; i < numberOfTransactions; i++)
                    {
                        double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                        try
                        {
                            account.Authenticate(account.Username, account.Password); // Authenticate before transfer
                            BankAccount toAccount = accounts[random.Next(accounts.Count)];
                            toAccount.Authenticate(toAccount.Username, toAccount.Password); // Authenticate target account
                            account.Transfer(toAccount, transactionAmount);
                            Console.WriteLine($"Transfer: {transactionAmount}, From: {account.AccountNumber}, To: {toAccount.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                        }
                        catch (Exception ex)
                        {
                            Console.WriteLine($"Transfer failed: {ex.Message}");
                        }
                    }
                    Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                });
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
                DateTime startDate = new(DateTime.Today.Year - MaxYearsBack, 1, 1);
                int daysRange = (DateTime.Today - startDate).Days;
                DateTime randomDate = startDate.AddDays(random.Next(daysRange));
                if (randomDate.Year == DateTime.Today.Year && randomDate >= DateTime.Today)
                {
                    randomDate = randomDate.AddDays(-1);
                }
                return randomDate;
            }
            static string GenerateSecurePassword()
            {
                const int passwordLength = 12;
                const string validChars = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890!@#$%^&*()";
                StringBuilder password = new StringBuilder();
                using (RNGCryptoServiceProvider rng = new RNGCryptoServiceProvider())
                {
                    byte[] uintBuffer = new byte[sizeof(uint)];
                    while (passwordLength > password.Length)
                    {
                        rng.GetBytes(uintBuffer);
                        uint num = BitConverter.ToUInt32(uintBuffer, 0);
                        password.Append(validChars[(int)(num % (uint)validChars.Length)]);
                    }
                }
                return password.ToString();
            }
        }
    }

    ```

1. Tenga en cuenta que las actualizaciones de Program.cs centradas en la generación segura de números aleatorios.

    Las otras sugerencias se aplican a la clase BankAccount y la implementación está fuera del ámbito de este entrenamiento.

1. Cree una solicitud adicional para Program.cs que busca proteger el control de excepciones.

1. Revise las sugerencias proporcionadas por GitHub Copilot Chat.

    Por ejemplo, si escribe `@workspace /explain How can I implement secure exception handling in the Program.cs file?` en la vista Chat, GitHub Copilot Chat sugiere actualizaciones similares a la siguiente respuesta:

    *Para implementar el control seguro de excepciones en el archivo Program.cs, debe seguir estos procedimientos recomendados:*

    *1. Captura de excepciones específicas:*

    *- Captura excepciones específicas en lugar de usar un bloque catch general (excepción). Esto ayuda a comprender y controlar los diferentes tipos de errores de forma adecuada.*

    *2. Registrar excepciones de forma segura:*

    *- Registra excepciones de forma segura sin exponer información confidencial. Utiliza un marco de registro para administrar los registros.*

    *3. Proporcionar mensajes fáciles de usar:*

    *: Proporcione mensajes de error fáciles de usar sin revelar detalles internos.*

    *4. Usar Bloques Finally para la limpieza:*

    *: Use bloques finally para asegurarse de que se realiza cualquier limpieza necesaria, independientemente de si se produjo una excepción.*

    *5. Evitar detectar excepciones no críticas:*

    *: Evite detectar excepciones que se deben permitir para propagar, como OutOfMemoryException o StackOverflowException.*

    *Esta es una versión actualizada de Program.cs con control seguro de excepciones:*

    ```csharp

    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Security.Cryptography;
    using System.Text;
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
            static async Task Main()
            {
                List<BankAccount> accounts = CreateBankAccounts(NumberOfAccounts);
                await SimulateTransactionsAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
                await SimulateTransfersAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
            }
            static List<BankAccount> CreateBankAccounts(int numberOfAccounts)
            {
                List<BankAccount> accounts = new();
                int createdAccounts = 0;
                while (createdAccounts < numberOfAccounts)
                {
                    try
                    {
                        double initialBalance = GenerateRandomDollarAmount(true, minAccountStart, maxAccountStart);
                        string accountHolderName = GenerateRandomAccountHolder();
                        string accountType = GenerateRandomAccountType();
                        DateTime dateOpened = GenerateRandomDateOpened();
                        string accountNumber = "102000" + random.Next(1000, 9999).ToString();
                        string username = "user" + createdAccounts;
                        string password = GenerateSecurePassword();
                        BankAccount account = new(accountNumber, initialBalance, accountHolderName, accountType, dateOpened, username, password);
                        accounts.Add(account);
                        createdAccounts++;
                    }
                    catch (ArgumentException ex)
                    {
                        Console.WriteLine($"Account creation failed due to invalid argument: {ex.Message}");
                        // Log the exception securely
                        LogException(ex);
                    }
                    catch (Exception ex)
                    {
                        Console.WriteLine($"Account creation failed: {ex.Message}");
                        // Log the exception securely
                        LogException(ex);
                    }
                    finally
                    {
                        // Any cleanup code would go here.
                    }
                }
                return accounts;
            }
            static async Task SimulateTransactionsAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                var tasks = accounts.Select(async account =>
                {
                    for (int i = 0; i < numberOfTransactions; i++)
                    {
                        double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                        try
                        {
                            account.Authenticate(account.Username, account.Password); // Authenticate before transaction
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
                        catch (InvalidCreditAmountException ex)
                        {
                            Console.WriteLine($"Invalid credit amount: {ex.Message}");
                            LogException(ex);
                        }
                        catch (InvalidDebitAmountException ex)
                        {
                            Console.WriteLine($"Invalid debit amount: {ex.Message}");
                            LogException(ex);
                        }
                        catch (InsufficientFundsException ex)
                        {
                            Console.WriteLine($"Insufficient funds: {ex.Message}");
                            LogException(ex);
                        }
                        catch (AuthenticationException ex)
                        {
                            Console.WriteLine($"Authentication failed: {ex.Message}");
                            LogException(ex);
                        }
                        catch (Exception ex)
                        {
                            Console.WriteLine($"Transaction failed: {ex.Message}");
                            LogException(ex);
                        }
                    }
                    Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                });
                await Task.WhenAll(tasks);
            }
            static async Task SimulateTransfersAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                var tasks = accounts.Select(async account =>
                {
                    for (int i = 0; i < numberOfTransactions; i++)
                    {
                        double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                        try
                        {
                            account.Authenticate(account.Username, account.Password); // Authenticate before transfer
                            BankAccount toAccount = accounts[random.Next(accounts.Count)];
                            toAccount.Authenticate(toAccount.Username, toAccount.Password); // Authenticate target account
                            account.Transfer(toAccount, transactionAmount);
                            Console.WriteLine($"Transfer: {transactionAmount}, From: {account.AccountNumber}, To: {toAccount.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                        }
                        catch (InvalidTransferAmountException ex)
                        {
                            Console.WriteLine($"Invalid transfer amount: {ex.Message}");
                            LogException(ex);
                        }
                        catch (InsufficientFundsException ex)
                        {
                            Console.WriteLine($"Insufficient funds: {ex.Message}");
                            LogException(ex);
                        }
                        catch (AuthenticationException ex)
                        {
                            Console.WriteLine($"Authentication failed: {ex.Message}");
                            LogException(ex);
                        }
                        catch (Exception ex)
                        {
                            Console.WriteLine($"Transfer failed: {ex.Message}");
                            LogException(ex);
                        }
                    }
                    Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                });
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
                DateTime startDate = new(DateTime.Today.Year - MaxYearsBack, 1, 1);
                int daysRange = (DateTime.Today - startDate).Days;
                DateTime randomDate = startDate.AddDays(random.Next(daysRange));
                if (randomDate.Year == DateTime.Today.Year && randomDate >= DateTime.Today)
                {
                    randomDate = randomDate.AddDays(-1);
                }
                return randomDate;
            }
            static string GenerateSecurePassword()
            {
                const int passwordLength = 12;
                const string validChars = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890!@#$%^&*()";
                StringBuilder password = new StringBuilder();
                using (RNGCryptoServiceProvider rng = new RNGCryptoServiceProvider())
                {
                    byte[] uintBuffer = new byte[sizeof(uint)];
                    while (passwordLength > password.Length)
                    {
                        rng.GetBytes(uintBuffer);
                        uint num = BitConverter.ToUInt32(uintBuffer, 0);
                        password.Append(validChars[(int)(num % (uint)validChars.Length)]);
                    }
                }
                return password.ToString();
            }
            static void LogException(Exception ex)
            {
                // Implement a secure logging mechanism here
                // For example, log to a file, database, or external logging service
                Console.WriteLine($"Logged exception: {ex.Message}");
            }
        }
    }

    ```

1. Implemente las actualizaciones sugeridas que ayudan a mejorar la seguridad del código para el archivo `Program.cs`.

1. Para asegurarse de que los cambios no introdujeron ningún error, compile y ejecute la solución.

## Resumen

En esta demostración, has utilizado GitHub Copilot Chat para generar sugerencias para mejorar la seguridad del código en una aplicación de ejemplo. Ha desarrollado mensajes que dirigen a GitHub Copilot para proporcionar sugerencias para mejorar la autenticación, la protección de datos, el registro y otros temas relacionados con la seguridad. Implementó las actualizaciones sugeridas para mejorar la seguridad de la clase BankAccount y la clase Program en el **proyecto APL2007M5BankAccount-Security**.

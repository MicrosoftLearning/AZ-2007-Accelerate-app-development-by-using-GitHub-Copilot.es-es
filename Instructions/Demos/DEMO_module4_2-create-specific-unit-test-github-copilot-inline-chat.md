---
demo:
  title: 'Demostración: Creación de pruebas unitarias para condiciones específicas mediante GitHub Copilot'
  module: 'Module 4: Develop unit tests using GitHub Copilot tools'
---

# Demostración: Creación de pruebas unitarias para condiciones específicas mediante GitHub Copilot

## Instrucciones

Las actividades de demostración están diseñadas para un entorno que incluye los siguientes recursos:

- Visual Studio Code.
- Extensión del kit de desarrollo de C# para Visual Studio Code.
- Las extensiones de GitHub Copilot y GitHub Copilot Chat para Visual Studio Code. Se requiere una cuenta de GitHub con una suscripción activa para GitHub Copilot.
- Proyectos de código de ejemplo creados con C#.

**NOTA**: Se recomienda que los instructores consideren usar su propia cuenta de GitHub y la suscripción a GitHub Copilot para las demostraciones. Esto te permitirá controlar y personalizar el entorno de desarrollo. También harás que sea más fácil ajustar las demostraciones para adaptarlas a las necesidades de tus aulas.

**IMPORTANTE**: Si decides ejecutar las demostraciones en el entorno de laboratorio hospedado en lugar de en el equipo instructor, puedes descomprimir las aplicaciones de ejemplo en el entorno hospedado. Tendrás que configurar las extensiones de GitHub Copilot en el entorno hospedado para poder ejecutar las demostraciones. Es posible que el entorno hospedado sea más lento que el entorno local, por lo que es posible que tengas que ajustar el ritmo de las demostraciones según proceda.

### Presentación de la demostración

Las extensiones de GitHub Copilot Chat te pueden ayudar a crear pruebas unitarias para condiciones específicas en el código. Por ejemplo, puedes usar GitHub Copilot Chat para probar el comportamiento de un método cuando recibe una entrada específica.

En esta demostración, usarás las extensiones de GitHub Copilot para crear pruebas unitarias para condiciones específicas.

### Creación de pruebas unitarias mediante GitHub Copilot

Puedes crear pruebas unitarias mediante sugerencias de autocompletar de GitHub Copilot. El uso de sugerencias de autocompletar puede ayudarte a generar rápidamente pruebas unitarias para el código.

En esta sección de la demostración, usarás GitHub Copilot para crear pruebas unitarias para el método `IsPrime` de la clase `PrimeService`.

Completa los siguientes pasos para usar esta sección de la demostración:

1. Abra la carpeta de proyecto **APL2007M4PrimeService-UnitTests** en Visual Studio Code.

1. Abre el archivo PrimeServiceTests.cs en el editor.

1. Elimina todo el código dentro de la clase `PrimeServiceTests`.

    El contenido del archivo PrimeServiceTests.cs debe ser similar al fragmento de código siguiente:

    ```csharp

    namespace System.Numbers.UnitTests;
    public class PrimeServiceTests
    {
    }

    ```

1. Guarde el archivo PrimeServiceTests.cs y vuelva a generar la solución.

1. Para que GitHub Copilot genere una finalización insertada, cree una línea en blanco dentro de la clase `PrimeServiceTests`.

    Si espera un segundo o dos, GitHub Copilot sugiere una finalización para la clase `PrimeServiceTests`.

1. Selecciona **Aceptar** y dedica un minuto a revisar las pruebas unitarias que genera GitHub Copilot.

1. Dedique un minuto a revisar la colección de pruebas unitarias generadas por GitHub Copilot para el método `IsPrime`.

    En la siguiente sección de la demostración se muestra cómo usar GitHub Copilot Chat para pedir a GitHub Copilot que sugiera casos perimetrales adicionales que se deben probar.

    ```csharp

    namespace System.Numbers.UnitTests
    {
        public class PrimeServiceTests
        {
            private readonly PrimeService _primeService;
            public PrimeServiceTests()
            {
                _primeService = new PrimeService();
            }
            [Fact]
            public void IsPrime_ReturnsFalse_ForNegativeNumbers()
            {
                // Arrange
                int candidate = -5;
                // Act
                bool result = _primeService.IsPrime(candidate);
                // Assert
                Assert.False(result);
            }
            [Fact]
            public void IsPrime_ReturnsFalse_ForZero()
            {
                // Arrange
                int candidate = 0;
                // Act
                bool result = _primeService.IsPrime(candidate);
                // Assert
                Assert.False(result);
            }
            [Fact]
            public void IsPrime_ReturnsFalse_ForOne()
            {
                // Arrange
                int candidate = 1;
                // Act
                bool result = _primeService.IsPrime(candidate);
                // Assert
                Assert.False(result);
            }
            [Fact]
            public void IsPrime_ReturnsTrue_ForPrimeNumbers()
            {
                // Arrange
                int candidate = 7;
                // Act
                bool result = _primeService.IsPrime(candidate);
                // Assert
                Assert.True(result);
            }
        }
    }

    ```

### Creación de pruebas unitarias para condiciones específicas mediante GitHub Copilot y GitHub Copilot Chat

1. Selecciona el contenido de la clase `PrimeServiceTests`.

1. Abra la vista Chat.

1. Para agregar el archivo PrimeService.cs al contexto de la vista Chat, arrastre y coloque el archivo PrimeService.cs desde la vista Explorador a la vista Chat.

1. Escriba el siguiente símbolo del sistema en la vista Chat:

    ```plaintext
    @workspace #selection are there any edge cases that should also be tested 
    ```

1. Dedique un minuto a revisar las sugerencias proporcionadas por GitHub Copilot.

    ```plaintext
    Yes, there are a few edge cases that should also be tested:
    
    1. Large Prime Numbers: Ensure the function can handle large prime numbers.

    2. Large Non-Prime Numbers: Ensure the function can handle large non-prime numbers.

    3. Even Numbers Greater Than 2: Ensure the function returns false for even numbers greater than 2.

    4. Small Prime Numbers: Ensure the function correctly identifies small prime numbers like 2 and 3.

    Here are the additional test cases:
    ```

    ```csharp

    [Fact]
    public void IsPrime_ReturnsTrue_ForTwo()
    {
        // Arrange
        int candidate = 2;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.True(result);
    }
    [Fact]
    public void IsPrime_ReturnsTrue_ForThree()
    {
        // Arrange
        int candidate = 3;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.True(result);
    }
    [Fact]
    public void IsPrime_ReturnsFalse_ForEvenNumbersGreaterThanTwo()
    {
        // Arrange
        int candidate = 4;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.False(result);
    }
    [Fact]
    public void IsPrime_ReturnsTrue_ForLargePrimeNumber()
    {
        // Arrange
        int candidate = 7919;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.True(result);
    }
    [Fact]
    public void IsPrime_ReturnsFalse_ForLargeNonPrimeNumber()
    {
        // Arrange
        int candidate = 8000;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.False(result);
    }

    ```

1. Cree una línea en blanco después del último método de prueba de la clase `PrimeServiceTests`.

1. En la vista Chat, mantenga el mouse sobre el fragmento de código y seleccione **Insertar en cursor**.

1. Guarde el archivo PrimeServiceTests.cs y vuelva a generar la solución.

1. Dedique un minuto a revisar la colección de pruebas unitarias generadas por GitHub Copilot para el método `IsPrime`.

    Como siempre, es importante revisar el trabajo completado por GitHub Copilot para asegurarse de que las pruebas son válidas y que cubren los casos perimetrales que desea probar. Una vez que esté satisfecho con las pruebas, puede ejecutarlas para comprobar que superan.

1. Mantenga el puntero del mouse sobre una de las "flechas de prueba" verdes.

    Observe el mensaje de información sobre herramientas que indica que puede hacer clic para ejecutar la prueba o hacer clic con el botón derecho para ver más opciones.

1. Haga clic con el botón derecho del ratón en una de las "flechas de prueba" verdes.

1. Seleccione **Mostrar en el Explorador de pruebas**.

    Observe que se abre la vista Explorador de pruebas. La vista Explorador de pruebas se puede usar para ejecutar y depurar pruebas y para ver los resultados de las ejecuciones de pruebas. Para abrir manualmente la vista Explorador de pruebas, seleccione **Pruebas** en la barra de actividad del lado izquierdo de la ventana de Visual Studio Code. El icono de la vista **Prueba** es el que se parece a un flask de laboratorio.

1. En la parte superior de la vista Explorador de pruebas, seleccione **Ejecutar pruebas**.

    Después de unos segundos, el Explorador de pruebas muestra los resultados de la ejecución de la prueba. Debería ver que se superan todas las pruebas. Las marcas de verificación verdes en el Explorador de pruebas y a la izquierda de las pruebas unitarias en el Editor indican que la prueba superada.

### Resumen

En esta demostración, has usado GitHub Copilot y GitHub Copilot Chat para crear pruebas unitarias para condiciones específicas en la clase `PrimeService`. Ha usado finalizaciones de línea de código para generar aserciones para asegurarse de que los parámetros de entrada de función son válidos y ha usado la vista Chat para pedir a GitHub Copilot que sugiera casos perimetrales adicionales que se deben probar. Ha revisado las sugerencias proporcionadas por GitHub Copilot y ejecutó las pruebas para comprobar que superan. También ha aprendido a usar el Explorador de pruebas en Visual Studio Code para ejecutar y ver los resultados de las ejecuciones de pruebas.

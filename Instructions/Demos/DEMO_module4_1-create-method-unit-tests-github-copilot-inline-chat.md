---
demo:
  title: 'Demostración: Creación de pruebas unitarias mediante GitHub Copilot Chat'
  module: 'Module 4: Develop unit tests using GitHub Copilot tools'
---

# Demostración: Creación de pruebas unitarias mediante GitHub Copilot Chat

## Instrucciones

Las actividades de demostración están diseñadas para un entorno que incluye los siguientes recursos:

- Visual Studio Code.
- Extensión del kit de desarrollo de C# para Visual Studio Code.
- Las extensiones de GitHub Copilot y GitHub Copilot Chat para Visual Studio Code. Se requiere una cuenta de GitHub con una suscripción activa para GitHub Copilot.
- Proyectos de código de ejemplo creados con C#.

**NOTA**: Se recomienda que los instructores consideren usar su propia cuenta de GitHub y la suscripción a GitHub Copilot para las demostraciones. Esto te permitirá controlar y personalizar el entorno de desarrollo. También harás que sea más fácil ajustar las demostraciones para adaptarlas a las necesidades de tus aulas.

**IMPORTANTE**: Si decides ejecutar las demostraciones en el entorno de laboratorio hospedado en lugar de en el equipo instructor, puedes descomprimir las aplicaciones de ejemplo en el entorno hospedado. Tendrás que configurar las extensiones de GitHub Copilot en el entorno hospedado para poder ejecutar las demostraciones. Es posible que el entorno hospedado sea más lento que el entorno local, por lo que es posible que tengas que ajustar el ritmo de las demostraciones según proceda.

### Presentación de la demostración

Visual Studio Code y el kit de desarrollo de C# proporcionan un amplio conjunto de características que le ayudarán a crear y administrar pruebas unitarias para los proyectos de C#. Puede habilitar las pruebas para el proyecto, agregar paquetes de marcos de pruebas, ejecutar y administrar pruebas unitarias y generar casos de prueba unitaria mediante el Kit de desarrollo de C#.

GitHub Copilot puede ayudarle a generar pruebas unitarias para el código proporcionando sugerencias de chat en línea.

En esta demostración, crearás pruebas unitarias para un proyecto de código mediante GitHub Copilot Chat en Visual Studio Code.

### Creación de un proyecto de prueba de xUnit para las pruebas unitarias

Normalmente, los proyectos de prueba unitaria se crean en una carpeta que es independiente del proyecto que está probando. Esta separación ayuda a mantener el código de prueba separado del código de producción. En esta demostración, vas a crear un proyecto de prueba xUnit para el proyecto APL2007M4PrimeService.

Para crear un nuevo proyecto de prueba de xUnit, complete los pasos siguientes:

1. Abra la carpeta **APL2007M4PrimeService** en Visual Studio Code.

1. Abra la vista Explorador de soluciones en Visual Studio Code.

    La vista Explorador de soluciones es accesible desde el panel de la Barra lateral de Visual Studio Code. El Explorador de soluciones es similar a la vista Explorador, pero está diseñada específicamente para trabajar con proyectos de Visual Studio Code en lugar de sistemas de archivos generales.

1. En la vista Explorador de soluciones, haz clic con el botón derecho en **APL2007M4PrimeService** y luego selecciona **Nuevo proyecto**.

    Si no ves la opción **Nuevo proyecto**, asegúrate de que estás trabajando en la vista *Explorador de soluciones* y no en la vista *Explorador*.

1. Cuando aparezca la lista de tipos de proyecto, seleccione **xUnit Test Project**.

1. Para el nombre del proyecto, escribe **PrimeService.UnitTests** y luego presiona Entrar.

    El nombre del proyecto debe reflejar el nombre de la clase que está probando y debe ser único dentro de la solución. En este caso, la clase se denomina `PrimeService`, por lo que el proyecto de prueba se denomina `PrimeService.UnitTests`.

1. Selecciona la ubicación predeterminada del directorio.

    También puede crear el proyecto de prueba xUnit mediante el terminal de Visual Studio Code. Abra un terminal, vaya a la carpeta Números y ejecute el siguiente comando:

    ```plaintext
    dotnet new xunit -n PrimeService.UnitTests
    ```

1. Selecciona **Crear proyecto** y luego expande la carpeta PrimeService.UnitTests.

1. Elimina el archivo UnitTest1.cs que se ha creado con el proyecto PrimeService.UnitTests.

    Antes de crear una nueva prueba unitaria, debe agregar una referencia al proyecto de prueba unitaria que apunta al proyecto de clase que desea probar.

1. Para agregar una referencia al proyecto de código, haz clic con el botón derecho en **PrimeService.UnitTests**, selecciona **Agregar referencia de proyecto** y luego **Números**.

1. Para crear una clase para las pruebas unitarias, haga clic con el botón derecho en **PrimeService.UnitTests**, seleccione **Nuevo archivo**, seleccione **Clase**, escriba **PrimeServiceTests** y presione Entrar.

    Visual Studio Code debe abrir el archivo PrimeServiceTests.cs automáticamente.

1. Dedique un minuto a examinar el archivo PrimeServiceTests.cs.

    El archivo debe ser similar al siguiente fragmento de código:

    ```csharp

    namespace PrimeService.UnitTests;
    public class PrimeServiceTests
    {
    }

    ```

1. Para evitar problemas de espacio de nombres al compilar el proyecto, actualice el archivo PrimeServiceTests.cs de la siguiente manera:

    ```csharp

    namespace System.Numbers.UnitTests;
    public class PrimeServiceTests
    {
    }

    ```

    Un espacio de nombres en C# se usa para organizar clases y tipos relacionados. Es una manera de evitar colisiones de nombres y facilitar la comprensión de la organización del código. El sufijo `.UnitTests` en el espacio de nombres del proyecto de prueba es una convención común para indicar que el código de este espacio de nombres está probando el código en el espacio de nombres System.Numbers. Esto hace que, al examinar la estructura del proyecto, esté claro qué parte del código es de producción y qué parte es de prueba.

1. Dedique un minuto a examinar el archivo PrimeService.UnitTests.csproj.

    El archivo PrimeService.UnitTests.csproj debe incluir un `<ItemGroup>` que contenga los siguientes elementos `<PackageReference />`:

    ```xml

    <PackageReference Include="coverlet.collector" Version="6.0.0" />
    <PackageReference Include="Microsoft.NET.Test.Sdk" Version="17.8.0" />
    <PackageReference Include="xunit" Version="2.5.3" />
    <PackageReference Include="xunit.runner.visualstudio" Version="2.5.3" />

    ```

    Estas referencias de paquete son necesarias para usar xUnit como biblioteca de pruebas y para configurar el ejecutor de pruebas. También debería ver los siguientes elementos `<ItemGroup>` en el archivo PrimeService.UnitTests.csproj:

    ```xml

    <ItemGroup>
        <Using Include="Xunit" />
    </ItemGroup>
    <ItemGroup>
        <ProjectReference Include="..\Numbers\Numbers.csproj" />
    </ItemGroup>

    ```

    Estos elementos son necesarios para hacer referencia al proyecto Numbers y para usar el marco de pruebas xUnit.

1. Para compilar la solución, presione **Ctrl+Mayús+B** y, a continuación, seleccione **dotnet: build**.

    También puede compilar la solución mediante un comando de la CLI de .NET (dotnet build) o haciendo clic con el botón derecho en el nodo de solución en la vista Explorador de soluciones y seleccionando **Compilar**.

    > [!NOTE]
    > Si ves algún **error** de compilación, corrige los errores antes de continuar con la demostración. Debe tener una compilación correcta antes de continuar.

Ya estás a punto para crear una prueba unitaria mediante GitHub Copilot Chat.

### Creación de pruebas unitarias mediante la vista Chat

GitHub Copilot y GitHub Copilot Chat pueden ayudarle a generar pruebas unitarias para el código proporcionando sugerencias basadas en el contexto del código base. Puede usar GitHub Copilot Chat para generar pruebas unitarias para métodos o clases específicos en el código.

Completa los siguientes pasos para usar esta sección de la demostración:

1. En la vista Explorador de soluciones, en Números, abra el archivo PrimeService.cs.

1. Seleccione el método **IsPrime**.

1. Abra la vista Chat.

1. Seleccione el botón **Adjuntar contexto**.

    El botón **Adjuntar contexto** (icono de paperclip) se usa para informar a GitHub Copilot del contexto pertinente dentro del código base. El contexto adicional ayuda a GitHub Copilot Chat a proporcionar sugerencias más precisas. En este caso, quiere que GitHub Copilot use el archivo PrimeServiceTests.cs al proponer pruebas unitarias.

1. En la lista desplegable **Buscar datos adjuntos**, en la sección **abierta recientemente**, seleccione **PrimeServiceTests.cs**.

    La lista desplegable **Buscar datos adjuntos** proporciona algunas opciones predeterminadas entre las que puede elegir. También incluye una lista de archivos abiertos recientemente. El archivo PrimeServiceTests.cs debe aparecer en la sección abierta recientemente.

    Las opciones Buscar datos adjuntos incluyen

1. Vuelva a seleccionar el botón **Asociar contexto**.

1. En el cuadro de texto Buscar datos adjuntos, escriba **PrimeService.Unit**, y seleccione **PrimeService.UnitTests.csproj**.

    > [!NOTE]
    > Muestra cómo arrastrar un archivo desde la vista Explorador hasta colocarlo en la vista Chat. En muchos casos, se trata de una manera más rápida de adjuntar contexto.

1. Observe que la vista Chat se actualiza con el contexto adicional.

1. En la vista Chat, seleccione **/tests agregue pruebas unitarias para mi código**.

    La opción **/tests agrega pruebas unitarias para mi código** se usa para generar pruebas unitarias para el código seleccionado en el editor. En este caso, seleccionó el método **IsPrime** en el archivo PrimeService.cs.

1. Dedique un minuto a revisar las sugerencias de GitHub Copilot.

    La sugerencia de GitHub Copilot incluye dos secciones, un "Plan" y un ejemplo de código que contiene pruebas unitarias.

    El plan sugiere crear un nuevo archivo PrimeServiceTest.cs para las pruebas unitarias. También sugiere crear el archivo en la carpeta del proyecto Numbers.

1. En la vista Chat, seleccione **Aplicar ediciones**.

1. Observe que el botón Aplicar ediciones coloca el código de prueba unitaria en una nueva pestaña del editor.

    Puede usar este código para actualizar el archivo PrimeServiceTests.cs en el proyecto PrimeService.UnitTests.

1. En el menú **Archivo**, seleccione **Guardar como** y, a continuación, vaya a la carpeta PrimeService.UnitTests.

1. Seleccione **PrimeServiceTests.cs** y, a continuación, seleccione **Guardar**.

1. Cuando se le pida que sobrescriba el archivo existente, seleccione **Sí**.

1. Dedique un minuto a revisar el archivo de PrimeServiceTests.cs actualizado.

    El código sugerido por GitHub Copilot Chat debe incluir pruebas para números primos y no primos específicos. El código sugerido puede incluir pruebas parametrizadas (mediante `[Theory]` y `[InlineData]` atributos) para probar varios conjuntos de datos de forma más concisa.

    El fragmento de código proporcionado debe ser similar al siguiente:

    ```csharp

    using Xunit;
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
            public void IsPrime_InputIs1_ReturnsFalse()
            {
                var result = _primeService.IsPrime(1);
                Assert.False(result, "1 should not be prime");
            }
            [Fact]
            public void IsPrime_InputIs2_ReturnsTrue()
            {
                var result = _primeService.IsPrime(2);
                Assert.True(result, "2 should be prime");
            }
            [Fact]
            public void IsPrime_InputIs3_ReturnsTrue()
            {
                var result = _primeService.IsPrime(3);
                Assert.True(result, "3 should be prime");
            }
            [Fact]
            public void IsPrime_InputIs4_ReturnsFalse()
            {
                var result = _primeService.IsPrime(4);
                Assert.False(result, "4 should not be prime");
            }
            [Theory]
            [InlineData(5, true)]
            [InlineData(6, false)]
            [InlineData(7, true)]
            [InlineData(8, false)]
            [InlineData(9, false)]
            [InlineData(10, false)]
            public void IsPrime_Values_ReturnExpectedResult(int value, bool expected)
            {
                var result = _primeService.IsPrime(value);
                Assert.Equal(expected, result);
            }
        }
    }

    ```

    Observa que las pruebas unitarias requieren una instancia de la clase PrimeService.

    ```csharp

    private readonly PrimeService _primeService;
    public PrimeServiceTests()
    {
        _primeService = new PrimeService();
    }

    ```

1. Compile la solución.

    Debería ver las "flechas de prueba" verdes junto a cada prueba unitaria si la compilación se ha realizado correctamente.

    Debes crear más pruebas unitarias en la sección siguiente, por lo que no es necesario ejecutar las pruebas en este momento.

    Pero existen varios modos de ejecutar las pruebas. Por ejemplo:

    - Puede ejecutar las pruebas desde el terminal de Visual Studio Code mediante el comando `dotnet test`.
    - Puede ejecutar las pruebas desde la vista Explorador de pruebas de Visual Studio Code.
    - Puedes ejecutar las pruebas desde la paleta de comandos de Visual Studio Code mediante el comando **Test: Run All Tests**.
    - Puedes ejecutar las pruebas desde el editor de Visual Studio Code seleccionando la opción **Ejecutar pruebas en el archivo actual** que hay en el menú contextual.

    Las pruebas que has creado durante esta sección de la demostración deben ejecutarse correctamente. Las "flechas de prueba" verdes junto a la prueba unitaria se convierten en círculos verdes con una marca de verificación.

### Creación de pruebas unitarias mediante chat en línea

Completa los siguientes pasos para usar esta sección de la demostración:

1. En la vista Explorador de soluciones, abra el archivo PrimeService.cs.

    PrimeService.cs se encuentra en la carpeta Números.

1. Seleccione el método IsPrime.

1. Abra una sesión de chat en línea y escriba la siguiente solicitud:

    ```plaintext
    Create unit tests for the IsPrime method using the xUnit framework.
    ```

1. Dedique un minuto a revisar las sugerencias proporcionadas por el chat en línea.

    ```csharp

    using Xunit;
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
            public void IsPrime_InputIs1_ReturnsFalse()
            {
                var result = _primeService.IsPrime(1);
                Assert.False(result, "1 should not be prime");
            }
            [Fact]
            public void IsPrime_InputIs2_ReturnsTrue()
            {
                var result = _primeService.IsPrime(2);
                Assert.True(result, "2 should be prime");
            }
            [Fact]
            public void IsPrime_InputIs3_ReturnsTrue()
            {
                var result = _primeService.IsPrime(3);
                Assert.True(result, "3 should be prime");
            }
            [Fact]
            public void IsPrime_InputIs4_ReturnsFalse()
            {
                var result = _primeService.IsPrime(4);
                Assert.False(result, "4 should not be prime");
            }
            [Theory]
            [InlineData(5, true)]
            [InlineData(6, false)]
            [InlineData(7, true)]
            [InlineData(8, false)]
            [InlineData(9, false)]
            [InlineData(10, false)]
            public void IsPrime_Values_ReturnExpectedResult(int value, bool expected)
            {
                var result = _primeService.IsPrime(value);
                Assert.Equal(expected, result);
            }
        }
    }

    ```

1. Observe que la vista Chat y el chat en línea producen una cobertura de prueba similar.

1. Para descartar la sugerencia de chat en línea, seleccione **Descartar** y, a continuación, cierre la pestaña de archivo creada por el chat en línea.

    Ten en cuenta que las pruebas unitarias sugeridas por GitHub Copilot durante esta demostración pueden estar incompletas. En la siguiente demostración se examinan casos perimetrales adicionales con los que podrías plantearse realizar pruebas.

### Resumen

En esta demostración, has creado pruebas unitarias para un proyecto de código mediante GitHub Copilot Chat en Visual Studio Code. Creó un proyecto de prueba de xUnit, agregó una referencia al proyecto que quería probar y generó pruebas unitarias para el método `IsPrime` en la clase `PrimeService`. Ha usado GitHub Copilot Chat para generar pruebas unitarias en la vista Chat y el chat en línea.

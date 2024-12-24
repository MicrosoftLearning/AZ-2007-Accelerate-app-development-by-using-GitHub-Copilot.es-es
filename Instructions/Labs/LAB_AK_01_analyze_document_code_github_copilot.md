---
lab:
  title: 'Laboratorio: Aceleración del desarrollo de aplicaciones mediante GitHub Copilot'
  type: Answer Key
  module: Modules 2-5
---

# Laboratorio: Aceleración del desarrollo de aplicaciones mediante GitHub Copilot
# Clave de respuesta del laboratorio de alumnos

## Parte 1: Análisis y documentación de código mediante herramientas de GitHub Copilot

### Antes de comenzar

#### Información general del proyecto

Eres desarrollador de software y trabajas para un departamento de TI regional. La mayoría de las aplicaciones que trabaja en el soporte técnico de la comunidad local. Recientemente, los servidores de la biblioteca se dañaron en un accidente y tardarás semanas en obtener la autorización para reemplazarlos. El departamento debe desarrollar una solución temporal que permita a los bibliotecarios realizar funciones básicas.

El equipo se ha reunido con los bibliotecarios. Necesitan una solución mínima que les permita prestar a los usuarios de la biblioteca servicios esenciales como el préstamo y la devolución de libros. El equipo investiga los recursos disponibles y desarrolla un plan. Inicialmente, solo se le asignará a usted y a otro compañero al proyecto. El gobierno local ha cerrado la biblioteca hasta que la solución temporal esté disponible. Tiene tres días para desarrollar una solución v1 que permita reabrir la biblioteca.

Mientras su compañero empieza a trabajar en el software, usted utiliza los registros de la biblioteca para crear archivos JSON que representen las cuentas de los usuarios, los libros y los préstamos de libros de la biblioteca. Al final del segundo día estará listo para empezar a ayudar con el código. La solución es una aplicación de consola que se puede ejecutar en uno de los equipos portátiles de la biblioteca. Los bibliotecarios entienden que no hay tiempo para una interfaz bonita, pero insisten en que la aplicación debe ser segura y fiable. Le queda un día para demostrar la versión 1.0 de su aplicación.

Usará GitHub Copilot para ayudar a realizar el trabajo de la forma más eficiente posible. Si todo va bien, su aplicación se utilizará en el futuro para apoyar las campañas de recogida de libros de la biblioteca y otras funciones externas.

#### Escenario de laboratorio (parte 1)

GitHub Copilot puede ayudarle a comprender y documentar un código base mediante la generación de explicaciones y documentación.

En la parte 1 de este laboratorio, usarás GitHub Copilot para analizar y documentar la aplicación de biblioteca. También creará un repositorio de GitHub para la aplicación de biblioteca y generará un archivo LÉAME para el repositorio mediante GitHub Copilot.

La parte 1 incluye los siguientes ejercicios:

- Configuración de las extensiones de GitHub Copilot para Visual Studio Code.
- Use GitHub Copilot para explicar el código base de la aplicación de biblioteca.
- Use Visual Studio Code para crear un repositorio de GitHub para la aplicación de biblioteca.
- Usa extensiones de GitHub Copilot para crear un archivo README.md para el repositorio.

### Ejercicio 1: Configuración de las extensiones de GitHub Copilot para Visual Studio Code

Usarás tu cuenta de GitHub para autorizar a Visual Studio Code a comprobar la suscripción de GitHub Copilot.

Sigue los siguientes pasos para instalar las extensiones de GitHub Copilot:

1. Abra una ventana del explorador.

1. Para abrir el portal de GitHub Enterprise, ve a la siguiente dirección URL:

    ```plaintext
    https://github.com/enterprises/Microsoft-APL/sso
    ```

1. Inicia sesión en tu cuenta de GitHub con las siguientes credenciales:

    Correo electrónico/nombre de usuario: `@lab.CloudPortalCredential(1).Username`

    Contraseña: `@lab.CloudPortalCredential(1).Password`

1. Abra Visual Studio Code.

1. En el menú de la izquierda, seleccione **Extensiones**.

1. En el cuadro de texto Buscar extensiones en Marketplace, escriba **GitHub Copilot** y presione Entrar.

1. En la lista filtrada de extensiones, selecciona la extensión **GitHub Copilot** creada por GitHub.

1. En la página de extensiones de GitHub Copilot, seleccione **Instalar**.

1. Cuando veas la notificación "Iniciar sesión para usar GitHub Copilot", selecciona **Iniciar sesión en GitHub**.

    Si ves un cuadro de diálogo que dice que GitHub Copilot quiere iniciar sesión con GitHub, selecciona **Permitir**.

    Puesto que ya has iniciado sesión en tu cuenta de GitHub en una ventana del explorador, debe abrirse una nueva pestaña Comprobar sesión en la ventana del explorador.

1. En la página Comprobar sesión, selecciona **Continuar**.

1. En la página Autorizar aplicación, selecciona **Autorizar Visual Studio Code**.

1. Para volver a Visual Studio Code, selecciona **Abrir**.

1. Cierra y vuelve a abrir Visual Studio Code.

    Reiniciar Visual Studio Code ayuda a garantizar que GitHub Copilot esté integrado en la interfaz de usuario de Visual Studio Code.

1. Observa que el botón **Abrir Chat** está ahora visible en la parte derecha del Centro de comandos en la parte superior de la ventana de Visual Studio Code.

#### Resumen: Ejercicio 1

En este ejercicio, has instalado la extensión de GitHub Copilot en Visual Studio Code. También has autorizado a Visual Studio Code a acceder a tu cuenta de GitHub. Ahora estás listo para usar GitHub Copilot para analizar y documentar el código base de la aplicación de biblioteca.

### Ejercicio 2: Análisis del código base de la aplicación de biblioteca

Antes de crear un repositorio de código y un archivo LÉAME, debe tardar algún tiempo en examinar el código base. Es importante comprender la arquitectura de la aplicación y las características clave antes de documentar el proyecto. También debe ejecutar la aplicación para asegurarse de que funciona según lo previsto.

#### Tarea 1: Cargar la aplicación de biblioteca en el entorno de desarrollo

Su compañero ha desarrollado una versión inicial de la aplicación de la biblioteca y la ha puesto a su disposición como archivo .zip. Para prepararte para este laboratorio, debes realizar las siguientes acciones:

- Descarga un archivo ZIP que contenga la solución.
- Extraer los archivos de código.
- Abre la aplicación de biblioteca de Visual Studio Code y asegúrate de que se compila correctamente.

Sigue los siguientes pasos para preparar la aplicación de biblioteca:

1. Asegúrate de que tienes el explorador abierto y abre una nueva pestaña.

1. Para descargar el archivo zip que contiene el proyecto de código, ve a la siguiente dirección URL:

    ```plaintext
    https://raw.githubusercontent.com/MicrosoftLearning/APL-2007-Accelerate-app-development-by-using-GitHub-Copilot/master/LearnModuleExercises/Downloads/GuidedProjectApp.zip
    ```

    El archivo zip que contiene el código de la solución, GuidedProjectApp.zip, debe descargarse automáticamente.

1. Una vez completada la descarga, cierra la pestaña del explorador.

    Mantén abierta la página del explorador de tu cuenta de GitHub. Lo usarás más tarde en el laboratorio.

1. Abre el Explorador de archivos de Windows y ve a la carpeta Descargas.

1. Descomprimir los archivos del proyecto descargados.

    Descomprimir el proyecto de código en el entorno de desarrollo. Por ejemplo:

    1. En la máquina local, vaya a la carpeta de descargas.

    1. Haga clic con el botón derecho en **GuidedProjectApp.zip** y seleccione **Extraer todo**.

    1. Seleccione **Mostrar los archivos extraídos al completar** y, a continuación, **Extraer**.

    1. Tome nota de la ubicación de la carpeta extraída.

1. Copia la carpeta extraída, AccelerateDevGitHubCopilot, a una ubicación que sea fácil de acceder, como la carpeta Escritorio de Windows.

1. Abra la carpeta **AccelerateDevGitHubCopilot** en Visual Studio Code.

    Por ejemplo:

    1. Abra Visual Studio Code en el equipo.

    1. En Visual Studio Code, en el menú **Archivo**, seleccione **Abrir archivo**.

    1. Ve a la carpeta Escritorio de Windows y busca la carpeta **AccelerateDevGitHubCopilot**.

    1. Seleccione **AccelerateDevGitHubCopilot** y, a continuación, seleccione **Seleccionar carpeta**.

    1. Selecciona **Sí, confío en los autores**.

    > [!NOTE]
    > Visual Studio Code puede tardar entre 10 y 20 segundos en cargar los archivos del proyecto y las actualizaciones de .NET necesarias.

1. En la vista EXPLORADOR de Visual Studio Code, selecciona EXPLORADOR DE SOLUCIONES y después comprueba la siguiente estructura de proyecto:

    - AccelerateDevGitHubCopilot\
        - src\
            - Library.ApplicationCore\
            - Library.Console\
            - Library.Infrastructure\
        - tests\
            - UnitTests\

1. Asegúrese de que la solución se compila correctamente.

    Por ejemplo, en la vista EXPLORADOR DE SOLUCIONES, haga clic con el botón derecho en **AccelerateDevGitHubCopilot**y, a continuación, seleccione **Compilar**.

    Verás varias **advertencias**, pero no debería haber ningún error. Ejecutarás la aplicación más adelante en este ejercicio.

    > [!NOTE]
    > No instales actualizaciones de la carga de trabajo a menos que tu instructor te lo indique.

#### Tarea 2: Usar GitHub Copilot para explicar el código base de la aplicación de biblioteca

GitHub Copilot puede ayudarle a comprender un código base desconocido mediante la generación de explicaciones en los niveles de solución y características.

Completa los siguientes pasos para usar esta sección del ejercicio:

1. Asegúrese de que tiene abierta la solución AccelerateDevGitHubCopilot en Visual Studio Code.

1. Abra la vista Chat.

    Puedes abrir la vista Chat de las siguientes maneras:

    - Selecciona el botón **Abrir chat** (situado en la parte superior de la ventana de Visual Studio Code, justo a la derecha del Centro de comandos).
    - Usa el método abreviado de teclado: **Ctrl+Alt+I**.
    - Abra el menú estado de Copilot de GitHub y, a continuación, seleccione **Chat de GitHub Copilot**.

1. Escribe una consulta que use el participante **@workspace** de GitHub Copilot para generar una descripción del proyecto.

    Por ejemplo, escriba el siguiente símbolo del sistema en la vista Chat:

    ```plaintext
    @workspace Describe this project
    ```

    Si ves un cuadro de diálogo de Visual Studio Code que indica que "El chat de GitHub Copilot quiere iniciar sesión con GitHub", selecciona **Permitir** y luego completa el proceso de autorización usando tu cuenta de GitHub.

1. Dedica un minuto a revisar la respuesta generada por GitHub Copilot.

    Debería ver una respuesta similar a la descripción siguiente:

    ```markdown
    This project is a library management system implemented in C#. It consists of three main components:
    
    1. **Library.ApplicationCore**: This is the core application library containing the main business logic, entities, enums, and interfaces. It includes:
        - Entities such as Book, Patron, Loan, etc.
        - Enums like MembershipRenewalStatus, LoanReturnStatus, and LoanExtensionStatus.
        - Services like LoanService and PatronService.
        - Interfaces like ILoanRepository, IPatronRepository, ILoanService, and IPatronService.
    2. **Library.Console**: This is a console application that interacts with the user. It includes:
        - The main entry point in Program.cs.
        - Configuration settings in appSettings.json.
        - Console interaction logic in ConsoleApp.cs.
    3. **Library.Infrastructure**: This library handles data persistence. It includes:
        - JSON-based repositories like JsonPatronRepository and JsonLoanRepository.
        - Data loading and saving logic in JsonData.

    Additionally, there are unit tests located in the UnitTests directory, which test the functionality of the core services using the NSubstitute mocking framework and xUnit.
    
    The project uses .NET 8.0 and is configured to build and test using GitHub Actions as defined in the build-test.yml file. The solution file is AccelerateDevGitHubCopilot.sln, which includes all the projects and their configurations.
    ```

1. Usa la vista Explorador de soluciones de Visual Studio Code para expandir las carpetas del proyecto.

1. Localiza y abre el archivo **ConsoleApp.cs**.

    El archivo ConsoleApp.cs se encuentra en el proyecto src/Library.Console.

1. Escribe una consulta en la vista Chat que genere una descripción de la clase ConsoleApp.

    Por ejemplo, escriba el siguiente símbolo del sistema en la vista Chat:

    ```plaintext
    @workspace #editor Describe the ConsoleApp class
    ```

1. Tómese un par de minutos para revisar la respuesta.

    Debería ver una respuesta similar a la descripción siguiente:

    ```markdown
    The ConsoleApp class in ConsoleApp.cs is responsible for managing the console-based user interface of the library management system. It handles user interactions, processes user inputs, and coordinates actions with the underlying services and repositories.

    ### Fields
    - _currentState: Tracks the current state of the console application.
    - matchingPatrons: A list of patrons that match a search query.
    - selectedPatronDetails: Holds details of the currently selected patron.
    - selectedLoanDetails: Holds details of the currently selected loan.
    - _patronRepository: An instance of IPatronRepository for accessing patron data.
    - _loanRepository: An instance of ILoanRepository for accessing loan data.
    - _loanService: An instance of ILoanService for performing loan-related operations.
    - _patronService: An instance of IPatronService for performing patron-related operations.

    ### Constructor
    - ConsoleApp(ILoanService loanService, IPatronService patronService, IPatronRepository patronRepository, ILoanRepository loanRepository): Initializes the ConsoleApp with the provided services and repositories.

    ### Methods
    - Run(): The main entry point for running the console application.
    - PatronSearch(): Handles the logic for searching patrons.
    - ReadPatronName(): Reads the patron's name from the console input.
    - PrintPatronsList(List<Patron> matchingPatrons): Prints a list of matching patrons to the console.
    - PatronSearchResults(): Handles the logic for displaying and selecting from the search results.
    - ReadInputOptions(CommonActions options, out int optionNumber): Reads input options from the console.
    - WriteInputOptions(CommonActions options): Writes the available input options to the console.
    - PatronDetails(): Displays details of the selected patron.
    - LoanDetails(): Displays details of the selected loan and handles actions like extending or returning the loan.

    The class uses a state machine approach to manage different states of the console application, such as searching for patrons, displaying search results, showing patron details, and handling loan details.
    ```

1. Abra el archivo **Program.cs**.

1. Escribe una indicación en la vista Chat que genere una descripción del archivo Program.cs.

    Por ejemplo, escriba el siguiente símbolo del sistema en la vista Chat:

    ```plaintext
    @workspace #editor Describe the Program.cs file
    ```

1. Tómese un par de minutos para revisar la respuesta.

    Debería ver una respuesta similar a la descripción siguiente:

    ```markdown
    The Program.cs file is the entry point for the console application. It sets up the dependency injection container, configures services, and starts the ConsoleApp.
    
    1. **Dependency Injection Setup**:
        - Creates a ServiceCollection to register services.
        - Builds a configuration object from the appSettings.json file.
        - Registers various services and repositories with different lifetimes (singleton, scoped).
    
    2. **Service Registration**:
        - Registers the repositories: JsonPatronRepository and JsonLoanRepository.
        - Registers the services: LoanService and PatronService.
        - Registers the JsonData class as a singleton.
        - Registers the ConsoleApp class as a singleton.
    
    3. **Service Provider**:
        - Builds the service provider from the registered services.
        - Retrieves the ConsoleApp service and runs it asynchronously.

    This setup ensures that all dependencies are properly injected and configured before the application starts running.
    ```

1. Expande el proyecto Library.Infrastructure y después expande la carpeta Datos.

1. Agrega los archivos **JsonData.cs**, **JsonLoanRepository.cs**, y **JsonPatronRepository.cs** al contexto de chat.

    Puedes usar una operación de arrastrar y soltar para agregar los archivos desde el Explorador de soluciones a la vista Chat. También puedes usar el botón **Adjuntar contexto** (clip de papeles) en la vista Chat para agregar archivos al contexto de chat.

1. Escriba un mensaje en la vista Chat que genera una explicación de las clases de acceso a datos.

    Por ejemplo, escriba el siguiente símbolo del sistema en la vista Chat:

    ```plaintext
    @workspace /explain Explain how the data access classes work
    ```

1. Tómese un par de minutos para revisar la respuesta.

    Debería ver una respuesta similar a la descripción siguiente:

    ```markdown
    The data access classes in this project are designed to handle the loading, saving, and manipulation of data stored in JSON files. These classes include JsonData, JsonPatronRepository, and JsonLoanRepository. Here's an explanation of how each class works:
    
    ### JsonData Class
    The JsonData class is responsible for loading and saving data from and to JSON files. It also provides methods to populate related entities.
    
    #### Key Responsibilities:
    1. **Loading Data**: The LoadData method loads data from JSON files into in-memory collections (Authors, Books, BookItems, Patrons, Loans).
    2. **Saving Data**: The SaveJson method saves data to JSON files. Specific methods like SaveLoans and SavePatrons handle saving loans and patrons, respectively.
    3. **Ensuring Data is Loaded**: The EnsureDataLoaded method ensures that data is loaded into memory before any operations are performed.
    4. **Populating Related Entities**: Methods like GetPopulatedPatron, GetPopulatedLoan, GetPopulatedBookItem, and GetPopulatedBook populate related entities to provide a complete view of the data.
    
    #### Example Methods:
    - **LoadData**: Loads all data from JSON files.
    - **SaveLoans**: Saves loan data to the JSON file.
    - **GetPopulatedPatron**: Populates a patron with related loans.
    - **SearchBookByTitle**: Searches for a book by its title.
    
    ### JsonPatronRepository Class
    The JsonPatronRepository class implements the IPatronRepository interface and provides methods to interact with patron data.

    #### Key Responsibilities:
    1. **Searching Patrons**: The SearchPatrons method searches for patrons by name. 
    2. **Getting a Patron**: The GetPatron method retrieves a patron by ID and populates related data.
    3. **Updating a Patron**: The UpdatePatron method updates patron information and saves it to the JSON file.
    
    #### Example Methods:
    - **SearchPatrons**: Searches for patrons whose names contain the search input.
    - **GetPatron**: Retrieves a patron by ID and populates related loans.
    - **UpdatePatron**: Updates patron information and saves it to the JSON file.
    
    ### JsonLoanRepository Class
    The JsonLoanRepository class implements the ILoanRepository interface and provides methods to interact with loan data.
    
    #### Key Responsibilities:
    1. **Getting a Loan**: The GetLoan method retrieves a loan by ID and populates related data.
    2. **Updating a Loan**: The UpdateLoan method updates loan information and saves it to the JSON file.
    
    #### Example Methods:
    - **GetLoan**: Retrieves a loan by ID and populates related book items and patrons.
    - **UpdateLoan**: Updates loan information and saves it to the JSON file.
    
    ### How They Work Together
    1. **Loading Data**: When the application starts, the JsonData class loads data from JSON files into memory.
    2. **Searching and Retrieving Data**: The JsonPatronRepository and JsonLoanRepository classes use the JsonData class to search and retrieve data. They ensure data is loaded before performing operations.
    3. **Updating Data**: When data is updated, the repository classes call methods on the JsonData class to save the updated data back to the JSON files.
    4. **Populating Related Entities**: The JsonData class provides methods to populate related entities, ensuring that when a patron or loan is retrieved, it includes related data like loans or book items.
    
    ### Example Workflow
    1. **Search for a Patron**:
        - The SearchPatrons method in JsonPatronRepository calls EnsureDataLoaded to ensure data is loaded.
        - It then searches the Patrons collection for matching names and returns the results.

    2. **Get a Loan**:
       - The GetLoan method in JsonLoanRepository calls EnsureDataLoaded to ensure data is loaded.
       - It retrieves the loan by ID and uses GetPopulatedLoan to include related book items and patrons.

    3. **Update a Patron**:
       - The UpdatePatron method in JsonPatronRepository calls EnsureDataLoaded to ensure data is loaded.
       - It updates the patron information and calls SavePatrons to save the updated data to the JSON file.

    By using these data access classes, the application can efficiently manage data stored in JSON files, ensuring that data is loaded, manipulated, and saved correctly.
    ```

1. Tómese un par de minutos para examinar los archivos de datos JSON que se usan para simular los registros de la biblioteca.

    Los archivos de datos JSON se encuentran en la carpeta src/Library.Console/Json.

    Los archivos de datos usan propiedades de identificador para vincular entidades. Por ejemplo, un objeto Préstamo tiene una propiedad PatronId que se vincula a un objeto de usuario con el mismo Id. Los archivos JSON contienen datos para autores, libros, artículos de libros, patrones y préstamos.

    > [!NOTE]
    > Tenga en cuenta que los nombres de autor, los títulos de los libros y los nombres de los clientes se han anonimizado para los fines de este proyecto guiado.

#### Tarea 3: Compilar y ejecutar la aplicación

La ejecución de la aplicación le ayudará a comprender la interfaz de usuario, las características clave de la aplicación y cómo interactúan los componentes de la aplicación.

Completa los siguientes pasos para usar esta sección del ejercicio:

1. Asegúrese de que tiene abierta la vista del** Explorador de soluciones **.

    La vista Explorador de soluciones no es la misma que la vista explorador. La vista Explorador de soluciones usa archivos de proyecto y solución como nodos "directorio" para mostrar la estructura de la solución.

1. Para ejecutar la aplicación, haga clic con el botón derecho en **Library.Console**, seleccione **Depurar**y, a continuación, seleccione **Iniciar nueva instancia**.

    Si no se muestran las opciones **Depurar** y **Iniciar nueva instancia**, asegúrese de que usa la vista Explorador de soluciones y no la vista Explorador.

    Los pasos siguientes le guían a través de un caso de uso sencillo.

1. Cuando se le solicite un nombre de patrón, escriba **Uno** y presione Entrar.

    > [!NOTE]
    > La aplicación usa un proceso de búsqueda que distingue mayúsculas de minúsculas. Debes escribir "Uno" con "U" mayúscula.

    Debería ver una lista de clientes que coinciden con la consulta de búsqueda.

1. En el símbolo del sistema "Opciones de entrada", escriba **2** y presione Entrar.

    Al escribir **2**, se selecciona el segundo patrón de la lista.

    Debería ver el nombre del patrón y el estado de suscripción seguido de los detalles del préstamo del libro.

1. En el símbolo del sistema "Opciones de entrada", escriba **1** y presione Entrar.

    Al escribir **1**, se selecciona el primer libro de la lista.

    Debería ver los detalles del libro en la lista, incluida la fecha de vencimiento y el estado de devolución.

1. En el símbolo del sistema "Opciones de entrada", escriba **r** y presione Entrar.

    Al escribir **r**, se devuelve el libro.

1. Comprueba que se muestra el mensaje "Libro devuelto correctamente". .

    El mensaje "Libro devuelto correctamente." debe ir seguido de los detalles del libro. Los libros devueltos se marcan con **Returned: True**.

1. Para iniciar una nueva búsqueda, escriba **s** y presione Entrar.

1. Cuando se le solicite un nombre de patrón, escriba **Uno** y presione Entrar.

1. En el símbolo del sistema "Opciones de entrada", escriba **2** y presione Entrar.

1. Comprueba que el primer préstamo de libros está marcado como **Returned: True**.

1. En el símbolo del sistema "Opciones de entrada", escriba **q** y presione Entrar.

1. Detenga la sesión de depuración.

#### Resumen: Ejercicio 2

Este ejercicio te ha ayudado a comprender el código base de la aplicación de biblioteca y cómo interactúa la aplicación con el usuario. Has usado GitHub Copilot para generar explicaciones de la estructura del proyecto, los archivos seleccionados y las clases de acceso a datos. También has ejecutado la aplicación para ver cómo funciona la interfaz de consola y cómo interactúan los componentes de la aplicación.

### Ejercicio 3: Creación del repositorio de GitHub y archivo Léame vacío

La creación del repositorio de GitHub para el código le habilitará compartir su trabajo con otros usuarios y colaborar en el proyecto.

#### Tarea 1: Crear un repositorio de GitHub

Use los siguientes pasos para usar esta sección del ejercicio:

1. Asegúrate de tener tu cuenta de GitHub abierta en una ventana del explorador.

    Si es necesario, abre una ventana del explorador y usa la siguiente información para iniciar sesión:

    URL: `https://github.com/enterprises/Microsoft-APL/sso`

    Correo electrónico/nombre de usuario: `@lab.CloudPortalCredential(1).Username`

    Contraseña: `@lab.CloudPortalCredential(1).Password`

1. Abra el menú de la cuenta de GitHub y seleccione **Los repositorios**.

    Deberías ver un mensaje que indique que aún no tienes ningún repositorio.

1. Para construir comandos de configuración de Git que usen las credenciales de tu cuenta de GitHub, abre el **Bloc de notas de Windows** y luego compila los siguientes comandos de Git:

    ```bash
    git config --global user.email "lab assigned email"
    git config --global user.name "user name"
    ```

    Sustituye **"lab assigned email"** por el correo electrónico definido en el entorno del laboratorio: `@lab.CloudPortalCredential(1).Username`

    Sustituye **"user name"** por tu propio nombre.

1. Cambie a la ventana de Visual Studio Code.

1. Abre el terminal integrado de Visual Studio Code.

    En el menú Terminal, seleccione **Nuevo terminal**.

1. Para configurar Git con las credenciales asociadas a la cuenta de GitHub, escribe los dos comandos que has construido en el Bloc de notas.

1. En Visual Studio Code, abra la vista Control de código fuente.

1. Seleccione **Publicación en GitHub**.

    Si se abre un cuadro de diálogo en el que se te pide que inicies sesión con tu cuenta de GitHub, completa los pasos siguientes:

    1. Seleccione **Permitir**.
    1. Selecciona la cuenta que estás usando en este entorno de laboratorio.
    1. Si es necesario, selecciona **Publicar en GitHub** de nuevo.

1. Acepta el nombre predeterminado para el repositorio (AccelerateDevGitHubCopilot) y selecciona **Publicar en el repositorio privado de GitHub**.

    Observa que Visual Studio Code muestra un mensaje de estado durante el proceso de publicación.

    Es posible que se te pida que autorices de nuevo la cuenta de GitHub. Si es así, sigue las instrucciones en pantalla para autorizar tu cuenta en el explorador. Esto puede dar lugar a que el repositorio se publique mediante el mensaje de confirmación "Confirmar primero"

1. Si el código no se ha publicado en el repositorio y se te devuelve a la vista Control de código fuente, escribe un mensaje de confirmación y después selecciona **Publicar rama**.

    Cuando finalice el proceso de publicación, verá un mensaje que le informa de que el código se publicó correctamente en el repositorio de GitHub que especificó.

#### Tarea 2: Crear un archivo Léame vacío en GitHub

Use los siguientes pasos para usar esta sección del ejercicio:

1. Cambia a la ventana del explorador que muestra tu cuenta de GitHub.

1. Abra el nuevo repositorio AccelerateDevGitHubCopilot en la cuenta de GitHub.

    Si no ve el repositorio AccelerateDevGitHubCopilot, actualice la página. Si sigue sin ver el repositorio, pruebe los pasos siguientes:

    1. Vaya a Visual Studio Code.
    1. Abra las notificaciones (se generó una notificación cuando se publicó el nuevo repositorio).
    1. Seleccione **Abrir en GitHub** para abrir el repositorio.

1. En la pestaña Código del repositorio AccelerateDevGitHubCopilot, seleccione **Agregar un archivo LÉAME**.

1. En el editor de LÉAME.md, escriba **Próximamente** y seleccione **Confirmar cambios**.

1. En el cuadro de diálogo Confirmar cambios, selecciona **Commitir cambios**.

#### Tarea 3: Incorporar los cambios al repositorio local

Use los siguientes pasos para usar esta sección del ejercicio:

1. Cambie a Visual Studio Code y asegúrese de que la vista Control de código fuente está abierta.

1. Abre el menú **Más acciones** y después selecciona **Extraer**.

    El menú Más acciones puede abrirse mediante los puntos suspensivos de la esquina superior derecha de la vista Control de código fuente.

1. Abre la vista EXPLORADOR (contrae el EXPLORADOR DE SOLUCIONES y usa el explorador de archivos/carpetas predeterminado de Visual Studio Code), y luego expande la carpeta **AccelerateDevGitHubCopilot**.

1. Abra el archivo README.md.

    Debería ver el mensaje "Próximamente".

    > [!NOTE]
    > Podrías haber creado el contenido del archivo Léame directamente en Visual Studio Code y luego insertar las actualizaciones al repositorio de GitHub.

En el siguiente ejercicio usarás GitHub Copilot Chat para actualizar el archivo Léame de tu repositorio.

#### Resumen: Ejercicio 3

Este ejercicio te ha ayudado a crear un repositorio de GitHub para la aplicación de biblioteca y un archivo Léame vacío. También has extraído los cambios a tu repositorio local para asegurarte de que tienes las actualizaciones más recientes.

### Ejercicio 4: Creación de la documentación del proyecto para el archivo Léame

El archivo LÉAME es una parte esencial de cualquier repositorio de GitHub. El archivo LÉAME proporciona información basada en las necesidades del proyecto, los colaboradores del proyecto y las partes interesadas.

Para este ejercicio de proyecto guiado, el archivo LÉAME debe incluir las secciones siguientes:

- **Título del proyecto**: un título breve y claro del proyecto.
- **Descripción**: una explicación detallada de lo que es el proyecto y lo que hace.
- **Estructura del proyecto**: Desglose de la estructura del proyecto, incluidas las carpetas de claves y los archivos.
- **clases clave e interfaces**: Lista de clases e interfaces clave del proyecto.
- **Uso**: instrucciones sobre cómo usar el proyecto, a menudo se incluyen ejemplos de código.
- **Licencia**: la licencia en la que está el proyecto.

#### Tarea 1: Usar GitHub Copilot para generar la documentación del proyecto

En esta sección del ejercicio, vas a utilizar GitHub Copilot para crear la documentación del proyecto y agregarla a tu archivo README.md.

Completa los siguientes pasos para usar esta sección del ejercicio:

1. Abra la vista Chat.

    Cuando estés interesado en código o archivos específicos, puedes usar las operaciones de arrastrar y soltar para agregar archivos al contexto de la vista Chat. En este caso te interesa la solución general, por lo que usarás el participante `@workspace` en lugar de agregar archivos individuales.

1. Para generar documentación del proyecto para el archivo LÉAME, escriba el siguiente símbolo del sistema:

    ```plaintext
    @workspace Generate the contents of a README.md file for the code repository. Use "Library App" as the project title. The README file should include the following sections: Description, Project Structure, Key Classes and Interfaces, Usage, License. Format all sections as raw markdown. Use a bullet list with indents to represent the project structure. Do not include ".gitignore" or the ".github", "bin", and "obj" folders.
    ```

    > [!NOTE]
    > Con varias solicitudes, una para cada sección del archivo LÉAME generaría más Resultados detallados En este ejercicio se usa una simple solicitud para simplificar el proceso.

1. Revise la respuesta para asegurarse de que cada sección tiene el formato markdown.

    > [!NOTE]
    > Puedes actualizar las secciones Léame individualmente para proporcionar información más detallada o si no tienen el formato correcto. También puede copiar la respuesta de GitHub Copilot al archivo LÉAME y, a continuación, realizar correcciones directamente en el archivo markdown.

1. Con el archivo markdown abierto en el editor, abre el menú de estado de GitHub Copilot y después selecciona **Habilitar finalizaciones para Markdown**.

1. Copie las secciones de documentación sugeridas en el archivo LÉAME.md.

    GitHub Copilot puede generar sugerencias para la documentación de Markdown. Esta característica puede ayudarte a redactar y dar formato a los archivos Markdown.

    Por ejemplo, puedes seleccionar el contenido del archivo README.md, abrir el chat en línea y después pedir a GitHub Copilot que "corrija el formato de la documentación de Markdown".

1. Ajusta el formato si es necesario y guarda el archivo README.md actualizado.

    Debes tener un archivo Léame que incluya el título del proyecto, la descripción, la estructura del proyecto, las clases clave e interfaces, las instrucciones de uso y la información de licencia.

    ```markdown
    # Library App
    
    ## Description
    Library App is a console-based application for managing library operations such as patron management, book loans, and membership renewals. It uses a JSON-based data storage system and provides various services to handle library functionalities.
    
    ## Project Structure
    - AccelerateDevGitHubCopilot.sln
    - README.md
    - src
      - Library.ApplicationCore/
        - Entities/
          - `Author.cs`
          - `Book.cs`
          - `BookItem.cs`
          - `Loan.cs`
          - `Patron.cs`
        - Enums/
          - `LoanExtensionStatus.cs`
          - `LoanReturnStatus.cs`
          - `MembershipRenewalStatus.cs`
        - Interfaces/
          - `IPatronRepository.cs`
          - `IPatronService.cs`
          - `ILoanRepository.cs`
          - `ILoanService.cs`
        - `Library.ApplicationCore.csproj`
        - Services/
          - `PatronService.cs`
          - `LoanService.cs`
      - Library.Console/
        - `appSettings.json`
        - `CommonActions.cs`
        - `ConsoleApp.cs`
        - `ConsoleState.cs`
        - `Library.Console.csproj`
        - `Program.cs`
      - Library.Infrastructure/
        - Data/
          - `JsonData.cs`
          - `JsonLoanRepository.cs`
          - `JsonPatronRepository.cs`
        - `Library.Infrastructure.csproj`
    - tests
      - UnitTests/
        - ApplicationCore/
          - LoanService/
            - `ReturnLoan.cs`
            - `ExtendLoan.cs`
          - PatronService/
            - `RenewMembership.cs`
        - `UnitTests.csproj`
    
    ## Key Classes and Interfaces
    - **Entities**
      - **Author**: Represents an author with properties like Id and Name.
      - **Book**: Represents a book with properties like Id, Title, AuthorId, Genre, ImageName, and ISBN.
      - **BookItem**: Represents a specific copy of a book with properties like Id, BookId, AcquisitionDate, and Condition.
      - **Loan**: Represents a loan with properties like Id, BookItemId, PatronId, LoanDate, DueDate, and ReturnDate.
      - **Patron**: Represents a library patron with properties like Id, Name, MembershipStart, MembershipEnd, and Loans.
    
    - **Enums**
      - **LoanExtensionStatus**: Enum for loan extension statuses.
      - **LoanReturnStatus**: Enum for loan return statuses.
      - **MembershipRenewalStatus**: Enum for membership renewal statuses.
    
    - **Interfaces**
      - **IPatronRepository**: Interface for patron repository with methods like GetPatron, SearchPatrons, and UpdatePatron.
      - **IPatronService**: Interface for patron service with method RenewMembership.
      - **ILoanRepository**: Interface for loan repository with methods like GetLoan and UpdateLoan.
      - **ILoanService**: Interface for loan service with methods like ReturnLoan and ExtendLoan.
    
    - **Services**
      - **PatronService**: Implements IPatronService to handle patron-related operations.
      - **LoanService**: Implements ILoanService to handle loan-related operations.
    
    - **Console**
      - **ConsoleApp**: Main console application class that handles user interactions and application flow.
      - **ConsoleState**: Enum for different states of the console application.
      - **CommonActions**: Enum for common actions in the console application.
    
    - **Infrastructure**
      - **JsonData**: Handles loading and saving data to JSON files.
      - **JsonLoanRepository**: Implements ILoanRepository to manage loan data.
      - **JsonPatronRepository**: Implements IPatronRepository to manage patron data.
    
    ## Usage
    1. Clone the repository.
    2. Open the solution file AccelerateDevGitHubCopilot.sln in Visual Studio.
    3. Build the solution to restore dependencies.
    4. Run the Library.Console project to start the console application.
    5. Follow the on-screen instructions to search for patrons, view patron details, extend loans, return books, and renew memberships.
    
    ## License
    This project is licensed under the MIT License.
    ```

#### Tarea 2: Confirmar e insertar las actualizaciones de archivos Léame

Use los siguientes pasos para usar esta sección del ejercicio:

1. Abre la vista Control de código fuente de Visual Studio Code.

1. Para que GitHub Copilot genere un mensaje de confirmación, seleccione el icono situado en el lado derecho del cuadro de mensaje.

    Debería ver un mensaje de confirmación similar al siguiente:

    ```plaintext
    Update README.md with project description, structure, key classes, usage instructions, and license information
    ```

1. Almacenar provisionalmente y confirmar las actualizaciones de archivos.

1. Sincronice (o inserte) las actualizaciones en el repositorio de GitHub.

    Autoriza la operación de sincronización o inserción mediante las credenciales de GitHub si se te solicita.

#### Tarea 3: Comprueba tu trabajo

Para comprobar el trabajo, complete los pasos siguientes:

1. Abra el repositorio de GitHub para el proyecto AccelerateDevGitHubCopilot.

1. Use la pestaña **Código** para revisar el archivo de LÉAME.md actualizado.

    Es posible que tengas que actualizar el explorador para ver el archivo Léame actualizado.

1. Asegúrese de que la estructura del proyecto descrita en el archivo LÉAME alinea la estructura de carpetas del repositorio.

    Al obtener una vista previa del archivo Léame, puedes usar el árbol de archivos en el lado izquierdo de la interfaz de GitHub para expandir y revisar la estructura del repositorio.

1. Revise el historial de confirmaciones y busque el mensaje de confirmación generado por GitHub Copilot.

#### Resumen: Ejercicio 4

Este ejercicio te ha ayudado a crear documentación del proyecto para el archivo Léame mediante GitHub Copilot. Has usado GitHub Copilot para generar la descripción del proyecto, la estructura del proyecto, las clases clave e interfaces, las instrucciones de uso y la información de licencia. También has confirmado e insertado las actualizaciones del archivo Léame en el repositorio de GitHub.

## Parte 2: Desarrollo de características de código mediante las herramientas de GitHub Copilot

### Antes de comenzar

#### Información general del proyecto

Usted y su compañero de trabajo se reúnen para discutir sus objetivos para la aplicación de biblioteca. Quiere mejorar la experiencia del usuario para los bibliotecarios y los clientes. Se describen varias características nuevas que se pueden agregar a la aplicación.

Acepta trabajar con las siguientes características:

- Disponibilidad del libro: Habilite un bibliotecario para determinar el estado de disponibilidad de un libro. Esta característica debe mostrar un mensaje que indica si un libro está disponible para el préstamo o la fecha de vencimiento de devolución si el libro está actualmente en préstamo a otro patrón.

- Préstamos de libros: Permitir que un bibliotecario preste un libro a un patrón (si el libro está disponible). Esta característica debe mostrar la opción de que un cliente reciba un libro en préstamo, actualice Loans.json con el nuevo préstamo y muestre los detalles del préstamo para el patrón.

- Reservación de libros: Permitir que un bibliotecario reserve un libro para un patrón (a menos que el libro ya esté reservado). Esta característica debe implementar un nuevo proceso de reserva de libros. Esta característica puede requerir la creación de un nuevo archivo Reservations.json junto con las nuevas clases e interfaces necesarias para admitir el proceso de reserva.

Cada una de ellas trabajará en una de las nuevas características y, a continuación, volverá a agruparse. Trabajará en la característica para determinar el estado de disponibilidad de un libro. Su compañero de trabajo trabajará en la característica para prestar un libro a un patrón. La última característica, para reservar un libro para un patrón, se desarrollará después de que se completen las otras dos características.

#### Escenario de laboratorio (parte 2)

GitHub Copilot puede ayudarte a desarrollar nuevas características para la aplicación de biblioteca.

En la parte 2 de este laboratorio, usarás GitHub Copilot para generar sugerencias de código que te ayuden a implementar las nuevas características de forma más rápida y precisa.

La parte 2 incluye los siguientes ejercicios:

- Desarrollar una nueva característica de "disponibilidad de libros".
- Combina tus cambios en la rama principal del repositorio.

### Ejercicio 5: Desarrollo de una nueva característica de "disponibilidad de libros"

La característica de disponibilidad del libro debe incluir las siguientes actualizaciones de código:

- Implementa una nueva acción CommonActions.SearchBooks que permita a un bibliotecario seleccionar la opción para buscar un libro.
- Crea un nuevo método SearchBooks en ConsoleApp.cs. El método SearchBooks debe leer un título de libro proporcionado por el usuario. Comprueba si un libro está disponible para préstamo y muestra un mensaje que indique "book.title está disponible para el préstamo" o "book.title está en préstamo a otro usuario". La fecha de vencimiento de la devolución es loan.DueDate.

En este ejercicio, completarás las siguientes tareas:

- Crea una rama "disponibilidad de libros" en tu repositorio de código.
- Usa sugerencias de Copilot de GitHub para ayudar a implementar una nueva acción común searchBooks que puede seleccionar un bibliotecario.
- Usa sugerencias de Copilot de GitHub para ayudar a desarrollar el método SearchBooks que lee el título del libro proporcionado por un usuario, comprueba si un libro está disponible para préstamo y muestra un mensaje que indique el estado de disponibilidad del libro.

#### Tarea 1: Crear una nueva rama en el repositorio

Antes de empezar a desarrollar la nueva característica "disponibilidad de libros", debe crear una nueva rama en el repositorio. Esto le permite trabajar en la nueva característica sin afectar a la rama principal del repositorio. Puede combinar la nueva característica en la rama principal cuando esté lista.

Completa los siguientes pasos para usar esta sección del ejercicio:

1. Asegúrese de que tiene abierta la solución AccelerateDevGitHubCopilot en Visual Studio Code.

1. Seleccione la vista Control de código fuente y asegúrese de que el repositorio local está sincronizado con el repositorio remoto (Extracción o Sincronización).

1. En la esquina inferior izquierda de la ventana, seleccione **principal**.

1. Para crear una nueva rama, escribe **disponibilidad de libro** y después selecciona **+ Crear nueva rama**.

1. Para insertar la nueva rama en el repositorio remoto, seleccione **Publicar rama**.

#### Tarea 2: Implementar una nueva acción común "SearchBooks"

En esta sección del ejercicio, usarás GitHub Copilot para ayudarte a implementar una opción de menú denominada SearchBooks. Los bibliotecarios elegirán la acción SearchBooks para comprobar el estado de disponibilidad de un libro.

Estas son las actualizaciones de archivos que has completado durante esta tarea:

- Actualiza la enumeración CommonActions en CommonActions.cs: agrega una nueva acción SearchBooks a la enumeración CommonActions.
- Actualiza el método WriteInputOptions en ConsoleApp.cs: agrega compatibilidad para mostrar la nueva opción CommonActions.SearchBooks.
- Actualiza el método ReadInputOptions en ConsoleApp.cs: agrega compatibilidad para leer (seleccionar) la nueva opción CommonActions.SearchBooks.
- Actualiza el método PatronDetails en ConsoleApp.cs: agrega compatibilidad para procesar la nueva opción CommonActions.SearchBooks cuando esté seleccionada.

Completa los siguientes pasos para usar esta sección del ejercicio:

1. Abra la vista EXPLORADOR DE SOLUCIONES.

1. Abre el archivo CommonActions.cs y selecciona la enumeracion **CommonActions**.

    Debes agregar una nueva acción SearchBooks a CommonActions.

1. Abra el chat en línea y escriba el siguiente símbolo del sistema:

    ```plaintext
    Update selection to include a new `SearchBooks` action.
    ```

    GitHub Copilot debe sugerir una actualización de código que agregue la nueva acción SearchBooks a la enumeración CommonActions.

1. Revise la actualización sugerida y seleccione **Aceptar**.

    ```csharp

    public enum CommonActions
    {
        Repeat = 0,
        Select = 1,
        Quit = 2,
        SearchPatrons = 4,
        RenewPatronMembership = 8,
        ReturnLoanedBook = 16,
        ExtendLoanedBook = 32,
        SearchBooks = 64
    }

    ```

1. Abra el archivo ConsoleApp.cs.

1. Busca y selecciona el método **WriteInputOptions**.

    Debes agregar compatibilidad con la nueva opción CommonActions.SearchBooks. Muestra la opción para comprobar si hay un libro disponible para el préstamo.

1. Abra el chat en línea y escriba el siguiente símbolo del sistema:

    ```plaintext
    Update selection to include an option for the `CommonActions.SearchBooks` action. Use the letter "b" and the message "to check for book availability".
    ```

    GitHub Copilot debe sugerir una actualización de código que agregue un nuevo bloque "if" para la acción SearchBooks.

1. Revise la actualización sugerida y seleccione **Aceptar**.

    La actualización sugerida debe ser similar al siguiente fragmento de código:

    ```csharp

    static void WriteInputOptions(CommonActions options)
    {
        Console.WriteLine("Input Options:");
        if (options.HasFlag(CommonActions.ReturnLoanedBook))
        {
            Console.WriteLine(" - \"r\" to mark as returned");
        }
        if (options.HasFlag(CommonActions.ExtendLoanedBook))
        {
            Console.WriteLine(" - \"e\" to extend the book loan");
        }
        if (options.HasFlag(CommonActions.RenewPatronMembership))
        {
            Console.WriteLine(" - \"m\" to extend patron's membership");
        }
        if (options.HasFlag(CommonActions.SearchPatrons))
        {
            Console.WriteLine(" - \"s\" for new search");
        }
        if (options.HasFlag(CommonActions.SearchBooks))
        {
            Console.WriteLine(" - \"b\" to check for book availability");
        }
        if (options.HasFlag(CommonActions.Quit))
        {
            Console.WriteLine(" - \"q\" to quit");
        }
        if (options.HasFlag(CommonActions.Select))
        {
            Console.WriteLine("Or type a number to select a list item.");
        }
    }

    ```

1. Desplázate un poco hacia arriba para encontrar el método **ReadInputOptions**.

1. Selecciona el método **ReadInputOptions**.

    Debes agregar compatibilidad con la nueva opción CommonActions.SearchBooks. Incluye un caso que controle que el usuario seleccione la acción SearchBooks.

1. Abra el chat en línea y escriba el siguiente símbolo del sistema:

    ```plaintext
    Update selection to include an option for the `CommonActions.SearchBooks` action.
    ```

    GitHub Copilot debe sugerir una actualización de código que agregue un nuevo "caso" que controle que el usuario seleccione la acción SearchBooks.

1. Revise la actualización sugerida y seleccione **Aceptar**.

    La actualización sugerida debe ser similar al siguiente fragmento de código:

    ```csharp

    static CommonActions ReadInputOptions(CommonActions options, out int optionNumber)
    {
        CommonActions action;
        optionNumber = 0;
        do
        {
            Console.WriteLine();
            WriteInputOptions(options);
            string? userInput = Console.ReadLine();
            action = userInput switch
            {
                "q" when options.HasFlag(CommonActions.Quit) => CommonActions.Quit,
                "s" when options.HasFlag(CommonActions.SearchPatrons) => CommonActions.SearchPatrons,
                "m" when options.HasFlag(CommonActions.RenewPatronMembership) => CommonActions.RenewPatronMembership,
                "e" when options.HasFlag(CommonActions.ExtendLoanedBook) => CommonActions.ExtendLoanedBook,
                "r" when options.HasFlag(CommonActions.ReturnLoanedBook) => CommonActions.ReturnLoanedBook,
                "b" when options.HasFlag(CommonActions.SearchBooks) => CommonActions.SearchBooks,
                _ when int.TryParse(userInput, out optionNumber) => CommonActions.Select,
                _ => CommonActions.Repeat
            };
            if (action == CommonActions.Repeat)
            {
                Console.WriteLine("Invalid input. Please try again.");
            }
        } while (action == CommonActions.Repeat);
        return action;
    }

    ```

1. Desplázate hacia abajo para buscar y después selecciona el método **PatronDetails**.

    Hay dos cosas que debe realizar:

    - Debes agregar CommonActions.SearchBooks a las opciones antes de llamar a ReadInputOptions.
    - También debes agregar un else if para controlar la acción SearchBooks. El bloque else if debe llamar a un nuevo método denominado SearchBooks.

    Puede abordar ambos juntos.

1. Abra el chat en línea y escriba el siguiente símbolo del sistema:

    ```plaintext
    Update selection to add `CommonActions.SearchBooks` to `options` before calling `ReadInputOptions`. Add an `else if` block to handle the `SearchBooks` action. The `else if` block should call a new method named `SearchBooks`.
    ```

    GitHub Copilot debe sugerir una actualización de código que agregue CommonActions.SearchBooks a las opciones antes de llamar a ReadInputOptions.

1. Revise la actualización sugerida y seleccione **Aceptar**.

    ```csharp

    async Task<ConsoleState> PatronDetails()
    {
        Console.WriteLine($"Name: {selectedPatronDetails.Name}");
        Console.WriteLine($"Membership Expiration: {selectedPatronDetails.MembershipEnd}");
        Console.WriteLine();
        Console.WriteLine("Book Loans:");
        int loanNumber = 1;
        foreach (Loan loan in selectedPatronDetails.Loans)
        {
            Console.WriteLine($"{loanNumber}) {loan.BookItem!.Book!.Title} - Due: {loan.DueDate} - Returned: {(loan.ReturnDate != null).ToString()}");
            loanNumber++;
        }
        CommonActions options = CommonActions.SearchPatrons | CommonActions.Quit | CommonActions.Select | CommonActions.RenewPatronMembership | CommonActions.SearchBooks;
        CommonActions action = ReadInputOptions(options, out int selectedLoanNumber);
        if (action == CommonActions.Select)
        {
            if (selectedLoanNumber >= 1 && selectedLoanNumber <= selectedPatronDetails.Loans.Count())
            {
                var selectedLoan = selectedPatronDetails.Loans.ElementAt(selectedLoanNumber - 1);
                selectedLoanDetails = selectedPatronDetails.Loans.Where(l => l.Id == selectedLoan.Id).Single();
                return ConsoleState.LoanDetails;
            }
            else
            {
                Console.WriteLine("Invalid book loan number. Please try again.");
                return ConsoleState.PatronDetails;
            }
        }
        else if (action == CommonActions.Quit)
        {
            return ConsoleState.Quit;
        }
        else if (action == CommonActions.SearchPatrons)
        {
            return ConsoleState.PatronSearch;
        }
        else if (action == CommonActions.RenewPatronMembership)
        {
            var status = await _patronService.RenewMembership(selectedPatronDetails.Id);
            Console.WriteLine(EnumHelper.GetDescription(status));
            // reloading after renewing membership
            selectedPatronDetails = (await _patronRepository.GetPatron(selectedPatronDetails.Id))!;
            return ConsoleState.PatronDetails;
        }
        else if (action == CommonActions.SearchBooks)
        {
            return await SearchBooks();
        }
        throw new InvalidOperationException("An input option is not handled.");
    }

    ```

    > [!NOTE]
    > Las sugerencias de chat en línea también pueden crear código auxiliar para el método SearchBooks.

#### Tarea 3: Desarrollar el método SearchBooks

Una vez completado, el método SearchBooks debe leer el título del libro proporcionado por un usuario, comprobar si un libro está disponible para préstamo y mostrar un mensaje que indique el estado de disponibilidad del libro. El método debe usar los archivos Books.json y Loans.json para buscar el título del libro coincidente y determinar el estado de disponibilidad del libro.

Use los siguientes pasos para usar esta sección del ejercicio:

1. Dedica un minuto a tener en cuenta los requisitos de proceso del método SearchBooks.

    ¿Qué necesita hacer el método? ¿Qué debe devolver? ¿Requiere parámetros?

    El método SearchBooks debe implementar el siguiente proceso:

    1. Pida al usuario un título de libro.
    1. Lea el título del libro proporcionado por el usuario.
    1. Compruebe si hay un libro disponible para el préstamo
    1. Muestra un mensaje que indica una de las siguientes opciones:

        - "book.title está disponible para préstamo"
        - "book.title está prestado a otro usuario. La fecha de vencimiento de la devolución es loan.DueDate.

    Para compilar las opciones de mensaje, el código tendrá que acceder a los siguientes archivos JSON:

    - Books.json es necesario para encontrar el Título y el BookId coincidentes.
    - Loans.json es necesario para encontrar la ReturnDate y la DueDate del BookItemId correspondiente. BookItemId es el mismo que BookId en Books.json.

1. Asegúrate de que tienes el siguiente método **SearchBooks** creado en el archivo ConsoleApp.cs:

    ```csharp

    async Task<ConsoleState> SearchBooks()
    {
        return ConsoleState.PatronDetails;
    }

    ```

    > [!NOTE]
    > Asegúrese de quitar los comentarios de código creados por GitHub Copilot. Los comentarios innecesarios e inexactos pueden influir negativamente en las sugerencias de GitHub Copilot.

1. Selecciona el método **SearchBooks**.

1. Abra el chat en línea y escriba el siguiente símbolo del sistema:

    ```plaintext
    Update selection to obtain a book title. Prompt the user to "Enter a book title to search for". Read the user input and ensure the book title isn't null.
    ```

    GitHub Copilot debe sugerir una actualización de código que capture el título del libro proporcionado por el usuario.

1. Revise la actualización sugerida y seleccione **Aceptar**.

    ```csharp

    async Task<ConsoleState> SearchBooks()
    {
        string? bookTitle = null;
        while (String.IsNullOrWhiteSpace(bookTitle))
        {
            Console.Write("Enter a book title to search for: ");
            bookTitle = Console.ReadLine();
        }
        // Perform book search logic here
        return ConsoleState.PatronDetails;
    }

    ```

    > [!NOTE]
    > GitHub Copilot puede crear un método independiente para controlar la entrada del usuario de un título de libro. Puedes aceptar esa sugerencia y seguir desarrollando la lógica principal en el método SearchBooks.

1. Elimina cualquier comentario de marcador de posición generado por GitHub Copilot y después selecciona el método **SearchBooks**.

1. Abra la vista Chat.

1. Agrega los siguientes archivos al contexto de chat: ConsoleApp.cs, JsonData.cs, JsonLoanRepository.cs, Books.json, Loans.json, BookItems.json,.

1. Escriba lo siguiente:

    ```plaintext
    @workspace  Explain how to update the `SearchBooks` method and ConsoleApps class to determine whether a book title is available for loan. Inside the SearchBooks method, use a LINQ query and the user supplied book title to return a matching book. If a book is found, use a LINQ query and Loans.json to check if the book is available for loan. If the book has been returned, display a message stating "`book.title` is available for loan". If the book is on loan, display a message stating "`book.title` is on loan to another patron. The return due date is `loan.DueDate`".
    ```

1. Dedique un minuto a revisar las actualizaciones sugeridas.

    GitHub Copilot debe proponer actualizaciones similares a las siguientes sugerencias:

    Para actualizar el método SearchBooks y la clase ConsoleApp para determinar si el título de un libro está disponible para préstamo, sigue estos pasos:

    a. Agrega un método para buscar libros por título en la clase JsonData.
    b. Actualiza el método SearchBooks de la clase ConsoleApp para usar este nuevo método.
    c. Comprueba el estado del préstamo del libro y muestra el mensaje adecuado.

    Este es el código actualizado:

    Paso 1: Adición de un método de búsqueda de libros por título en la clase JsonData

    ```csharp

    public Book? SearchBookByTitle(string title)
    {
        return Books?.FirstOrDefault(b => b.Title.Equals(title, StringComparison.OrdinalIgnoreCase));
    }

    ```

    Paso 2: Actualización del método SearchBooks en la clase ConsoleApp

    ```csharp

    async Task<ConsoleState> SearchBooks()
    {
        string bookTitle = ReadBookTitle();
        // ensure data is loaded
        await _jsonData.LoadData();
        // find the book by title
        Book? book = _jsonData.SearchBookByTitle(bookTitle);
        if (book == null)
        {
            Console.WriteLine($"No book found with title: {bookTitle}");
            return ConsoleState.PatronDetails;
        }
        // find the loan status of the book
        Loan? loan = _jsonData.Loans?.FirstOrDefault(l => l.BookItemId == book.Id && l.ReturnDate == null);
        if (loan == null)
        {
            Console.WriteLine($"{book.Title} is available for loan.");
        }
        else
        {
            Console.WriteLine($"{book.Title} is on loan to another patron. The return due date is {loan.DueDate}.");
        }
        return ConsoleState.PatronDetails;
    }

    ```

    Paso 3: Actualización del constructor de la clase ConsoleApp para incluir JsonData

    ```csharp

    public class ConsoleApp
    {
        // Existing fields...
        JsonData _jsonData;
        public ConsoleApp(ILoanService loanService, IPatronService patronService, IPatronRepository patronRepository, ILoanRepository loanRepository, JsonData jsonData)
        {
            _patronRepository = patronRepository;
            _loanRepository = loanRepository;
            _loanService = loanService;
            _patronService = patronService;
            _jsonData = jsonData;
        }
        // Other methods...

    }

    ```

    Paso 4: Actualización del Program.cs para pasar JsonData a ConsoleApp

    ```csharp

    using Microsoft.Extensions.DependencyInjection;
    using Library.Infrastructure.Data;
    using Library.ApplicationCore;
    using Microsoft.Extensions.Configuration;
    var services = new ServiceCollection();
    var configuration = new ConfigurationBuilder()
    .SetBasePath(Directory.GetCurrentDirectory())
    .AddJsonFile("appSettings.json")
    .Build();
    services.AddSingleton<IConfiguration>(configuration);
    services.AddScoped<IPatronRepository, JsonPatronRepository>();
    services.AddScoped<ILoanRepository, JsonLoanRepository>();
    services.AddScoped<ILoanService, LoanService>();
    services.AddScoped<IPatronService, PatronService>();
    services.AddSingleton<JsonData>();
    services.AddSingleton<ConsoleApp>();
    var servicesProvider = services.BuildServiceProvider();
    var consoleApp = servicesProvider.GetRequiredService<ConsoleApp>();
    consoleApp.Run().Wait();

    ```

    Con estos cambios, el método SearchBooks de la clase ConsoleApp ahora buscará un libro por título en el archivo Books.json y comprobará su estado de préstamo en el archivo Loans.json. Si el libro está disponible para préstamo, mostrará un mensaje que indique que el libro está disponible. Si el libro está en préstamo, mostrará un mensaje que indica que el libro está en préstamo y proporcionará la fecha de vencimiento de devolución.

    > [!NOTE]
    > GitHub Copilot puede sugerir el uso de consultas LINQ en el método SearchBooks para devolver un objeto de libro en lugar de usar un método de la clase JsonData. Sin embargo, también podría sugerir la creación de métodos en la clase `JsonData` para devolver el título de un libro y comprobar el estado del préstamo (en lugar de usar consultas LINQ al método SearchBooks). Las instrucciones siguientes se basan en sugerencias de GitHub Copilot que usan una combinación de estos enfoques.

1. Agrega el método SearchBookByTitle sugerido al final de la clase **JsonData**.

    ```csharp

    public Book? SearchBookByTitle(string title)
    {
        return Books?.FirstOrDefault(b => b.Title.Equals(title, StringComparison.OrdinalIgnoreCase));
    }

    ```

1. Agrega la declaración del campo _jsonData a la clase ConsoleApp antes del constructor de clase.

    ```csharp

    JsonData _jsonData;

    ```

1. Agrega un parámetro JsonData jsonData al constructor de la clase ConsoleApp y úsalo para inicializar el campo _jsonData dentro del constructor.

    El constructor de clase actualizado debe tener un aspecto similar al siguiente fragmento de código:

    ```csharp

    public ConsoleApp(ILoanService loanService, IPatronService patronService, IPatronRepository patronRepository, ILoanRepository loanRepository, JsonData jsonData)
    {
        _patronRepository = patronRepository;
        _loanRepository = loanRepository;
        _loanService = loanService;
        _patronService = patronService;
        _jsonData = jsonData;
    }

    ```

1. Observa que JsonData no se reconoce en la clase ConsoleApp.

    Debes agregar "using Library.Infrastructure.Data;" a la parte superior del archivo ConsoleApp.cs.

1. Asegúrate de que se agrega la siguiente instrucción "using" a la parte superior del archivo ConsoleApp.cs.

    ```csharp

    using Library.Infrastructure.Data;

    ```

1. Usa las sugerencias de código para actualizar el método **SearchBooks**:

    El código sugerido debe usar el método SearchBookByTitle (o una consulta LINQ) para buscar el libro por título. Si se encuentra el libro, se usa una consulta LINQ para determinar si el libro está en préstamo. El código también incluye lógica para mostrar el estado de disponibilidad del libro en función de los resultados de la búsqueda. La lógica que se usa para mostrar mensajes de respuesta se puede implementar de varias maneras. En el siguiente fragmento de código se proporciona un ejemplo.

    El siguiente fragmento de código muestra una posible implementación del método SearchBooks:

    ```csharp

    async Task<ConsoleState> SearchBooks()
    {
        string bookTitle = ReadBookTitle();
        Book? book = _jsonData.SearchBookByTitle(bookTitle);
        if (book == null)
        {
            Console.WriteLine($"No book found with title: {bookTitle}");
            return ConsoleState.PatronDetails;
        }
        Loan? loan = _jsonData.Loans?.FirstOrDefault(l => l.BookItemId == book.Id && l.ReturnDate == null);
        if (loan == null)
        {
            Console.WriteLine($"{book.Title} is available for loan.");
        }
        else
        {
            Console.WriteLine($"{book.Title} is on loan to another patron. The return due date is {loan.DueDate}.");
        }
        return ConsoleState.PatronDetails;
    }

    ```

1. Compara el archivo **Program.cs** existente con las actualizaciones sugeridas.

    ```csharp

    using Microsoft.Extensions.DependencyInjection;
    using Library.Infrastructure.Data;
    using Library.ApplicationCore;
    using Microsoft.Extensions.Configuration;
    var services = new ServiceCollection();
    var configuration = new ConfigurationBuilder()
        .SetBasePath(Directory.GetCurrentDirectory())
        .AddJsonFile("appSettings.json")
        .Build();
    services.AddSingleton<IConfiguration>(configuration);
    services.AddScoped<IPatronRepository, JsonPatronRepository>();
    services.AddScoped<ILoanRepository, JsonLoanRepository>();
    services.AddScoped<ILoanService, LoanService>();
    services.AddScoped<IPatronService, PatronService>();
    services.AddSingleton<JsonData>();
    services.AddSingleton<ConsoleApp>();
    var servicesProvider = services.BuildServiceProvider();
    var consoleApp = servicesProvider.GetRequiredService<ConsoleApp>();
    consoleApp.Run().Wait();

    ```

    No se requiere ninguna actualización si el archivo Program.cs ya incluye el código que indica al sistema de inserción de dependencias de ASP.NET Core que cree una sola instancia de la clase JsonData y use esa misma instancia siempre que se solicite un JsonData.

1. Selecciona el método **SearchBooks**.

1. Abra la vista Chat y escriba la siguiente solicitud:

    ```plaintext
    Explain the LINQ queries and the evaluation of the book's availability status.
    ```

1. Dedique un minuto a revisar la explicación proporcionada por GitHub Copilot.

    Para la consulta que comprueba si el libro está en préstamo, deberías ver una descripción similar a la siguiente explicación:

    ```markdown
    **Search for the Loan Status of the Book**
    ```

    ```csharp

    Loan? loan = _jsonData.Loans?.FirstOrDefault(l => l.BookItemId == book.Id && l.ReturnDate == null);

    ```

    ```markdown
    - _jsonData.Loans: Accesses the list of loans from the JsonData class.

    - ?.: The null-conditional operator ensures that if _jsonData.Loans is null, the entire expression will return null without throwing a NullReferenceException.

    - FirstOrDefault: A LINQ method that returns the first element in the collection that matches the specified condition, or null if no such element is found.

    - Lambda Expression: l => l.BookItemId == book.Id && l.ReturnDate == null

        - l.BookItemId == book.Id: Checks if the BookItemId of the loan matches the Id of the book being searched.

        - l.ReturnDate == null: Checks if the loan's ReturnDate is null, indicating that the book is currently on loan and has not been returned.

    - Result: If a matching loan is found, it is assigned to the loan variable. If no matching loan is found, loan is null.

    **Evaluation of the Book's Availability Status**

    After executing the LINQ queries, the method evaluates the availability status of the book:

      - If loan is null, the book has been returned. The method prints that the book is available for loan.
      - If loan is not null, the book is currently on loan (no return date). The method prints that the book is on loan and provides the date when the book should be returned.

    ```

1. Compruebe la lógica implementada por el **Compruebe si el libro está en la consulta de préstamos**.

    Operador condicional NULL: el "?." es un operador condicional NULL. Garantiza que si _jsonData.Loans es null, toda la expresión se evaluará como nula sin iniciar una NullReferenceException.

    Expresión lambda: la expresión lambda "l => l.BookItemId == book. Id && l.ReturnDate == null" define la condición para el método FirstOrDefault. Comprueba cada objeto de préstamo "l" para ver si su BookItemId coincide con el Id. del objeto de libro y si su ReturnDate es nula.

    Este código intenta encontrar el primer préstamo de la colección _jsonData.Loans en el que el BookItemId coincide con el Id. del libro especificado y la ReturnDate es nula. Si no se encuentra dicho préstamo o si «_jsonData.Loans» es null, el préstamo se establecerá en nulo.

    > [!NOTE]
    > La mayoría de las bibliotecas modernas tienen varias copias del mismo libro. Este código supone que solo hay una copia de cada libro. Si la biblioteca tiene varias copias del mismo libro, el código deberá actualizarse para gestionar varios préstamos para el mismo libro. Para los fines de este entrenamiento, suponemos que solo hay una copia de cada libro y que la lógica proporcionada es suficiente.

1. Guarda tus archivos de actualizaciones.

1. Compile la solución para asegurarse de que no hay errores.

    Verás mensajes de **advertencia**, pero no debería haber ningún error.

    Para compilar la solución en la vista Explorador de soluciones, haga clic con el botón derecho en **AccelerateDevGitHubCopilot** y seleccione **Compilar**.

#### Resumen: Ejercicio 5

Has usado GitHub Copilot para ayudarte a implementar una nueva característica para la aplicación de biblioteca. Has creado una nueva rama en el repositorio y después has usado GitHub Copilot para generar sugerencias de código que te han ayudado a implementar la nueva característica de forma más rápida y precisa. Has agregado una nueva acción SearchBooks a CommonActions, has actualizado los métodos WriteInputOptions y ReadInputOptions en ConsoleApp.cs, y has creado un nuevo método SearchBooks para determinar el estado de disponibilidad de un libro.

### Ejercicio 6: Combinación de los cambios en la rama principal del repositorio

Has creado una nueva característica que permite a un bibliotecario determinar el estado de disponibilidad de un libro. Ahora debes comprobar que la característica funciona según lo previsto y combinar los cambios en la rama principal del repositorio.

En este ejercicio, completarás las siguientes tareas:

- Compruebe que la nueva característica funciona según lo previsto
- Sincronización de los cambios con el repositorio remoto
- Crea una solicitud de cambios para combinar tus cambios en la rama principal del repositorio

#### Tarea 1: Comprobar que la nueva característica funciona según lo previsto

Dado que no tiene pruebas automatizadas, se pueden usar pruebas manuales para comprobar que la nueva característica funciona según lo previsto. El uso de un origen de datos que se puede comprobar es importante. En este caso, se usan los archivos Books.json y Loans.json para comprobar que la nueva característica informa correctamente del estado de disponibilidad de un libro.

Completa los siguientes pasos para usar esta sección del ejercicio:

1. Abra la vista Explorador de soluciones.

1. Para ejecutar la aplicación, haga clic con el botón derecho en **Library.Console**, seleccione **Depurar** y, a continuación, seleccione **Iniciar nueva instancia**.

1. Cuando se le solicite un nombre de patrón, escriba **One** y presione Entrar.

    Debería ver una lista de clientes que coinciden con la consulta de búsqueda.

1. En el símbolo del sistema "Opciones de entrada", escriba **2** y presione Entrar.

    Al escribir **2**, se selecciona el segundo patrón de la lista.

    Debería ver el nombre del patrón y el estado de suscripción seguido de los detalles del préstamo del libro.

1. En el símbolo del sistema "Opciones de entrada", escriba **b** y presione Entrar.

    Al escribir **b** selecciona la opción para buscar el estado de disponibilidad de un libro.

    Debería ver un mensaje para escribir un título de libro.

1. Escriba **Book One** y presione Entrar.

    En los datos originales que descargó, **Book One** está actualmente en préstamo para **Patron Forty-Nine**, por lo que no debería estar disponible.

1. Compruebe que la aplicación muestra un mensaje que indica que el libro está en préstamo a otro patrón.

    Es posible que necesites desplazarte hacia arriba para ver el mensaje.

1. Compruebe que **Book Nine** ha sido devuelto por **Patron One**.

    En el ejercicio anterior, durante una prueba de la aplicación Biblioteca, había **Patrón One** devolver **Book Nine**. Si la aplicación muestra que **Book Nine** no ha sido devuelto por **Patron One**, use las opciones de entrada para seleccionar y devolver **Book Nine** antes de continuar.

    > [!NOTE]
    > El archivo Library.Console.csproj garantiza que los archivos de datos JSON se copien en el directorio de salida al compilar la aplicación. Sin embargo, la realización de operaciones de limpieza o recompilación básicamente restablecerá los datos. Las operaciones de compilación repetidas no restablecen los datos en el directorio de salida ("/bin/Debug/net8.0/").

1. En el símbolo del sistema "Opciones de entrada", escriba **b** y presione Entrar.

1. Escriba **Book Nine** y presione Entrar.

1. Compruebe que la aplicación muestra un mensaje que indica que el libro está disponible para el préstamo.

1. En el símbolo del sistema "Opciones de entrada", escriba **q** y presione Entrar.

1. Detenga la sesión de depuración.

1. Abre el archivo **Loans.json**.

    El archivo Loans.json se usa para realizar un seguimiento del estado de préstamo de cada libro. Puedes usar el archivo Loans.json para comprobar que el estado de disponibilidad de Libro Uno y Libro Nueve es correcto.

    El archivo Loans.json actualizado debe encontrarse en la carpeta "Library.Console\bin\Debug\net8.0\Json" o en la carpeta "Library.Console\Json".

    - Si usas el depurador de Visual Studio Code para ejecutar la aplicación, el archivo Loans.json actualizado debe encontrarse en la carpeta "Library.Console\bin\Debug\net8.0\Json".

    - Si usas un comando "dotnet run" de la carpeta "AccelerateDevGitHubCopilot\src\Library.Console" para ejecutar la aplicación, el archivo Loans.json actualizado debe encontrarse en la carpeta "Library.Console\Json".

1. Comprueba que el Id. de préstamo 37 y el Id. de préstamo 46 son ambos para el Libro Uno ("BookItemId": 1).

    - El Id. de préstamo 37 debe tener un valor ReturnDate (2024-01-17)
    - El Id. de préstamo 46 no debería tener un valor ReturnDate. El valor ReturnDate debe ser nulo.

    El valor ReturnDate se usa para determinar si el libro está actualmente en préstamo. Si el valor ReturnDate es nulo, se considera que el libro está en préstamo.

1. Comprueba que el Id. de préstamo 22 es para el Libro Nueve («BookItemId»: 9) y que el valor ReturnDate está establecido en la fecha actual.

    Si estás ejecutando en el depurador y has limpiado la solución después de hacer cambios en el archivo Loans.json, esos cambios se pierden. Después de limpiar la solución, el archivo Loans.json se restablece a los datos originales la próxima vez que ejecutes la aplicación. Puedes actualizar manualmente el archivo Loans.json para probar el estado de disponibilidad del Libro Uno y del Libro Nueve.

#### Tarea 2: Sincronizar los cambios con el repositorio remoto

Puedes usar la vista Control de código fuente en Visual Studio Code para confirmar los cambios en el repositorio local. Después de confirmar los cambios, puedes sincronizarlos con el repositorio remoto.

Use los siguientes pasos para usar esta sección del ejercicio:

1. Seleccione la vista Control de código fuente.

1. Asegúrate de que los archivos CommonActions.cs, ConsoleApp.cs y JsonData.cs aparecen en **Cambios**.

    Si GitHub Copilot ha usado consultas LINQ para determinar el estado de disponibilidad de un libro directamente dentro del método SearchBooks, es posible que no veas JsonData.cs en **Cambios**.

1. Use GitHub Copilot para generar un mensaje para el **Confirmar**.

1. Para almacenar provisionalmente y confirmar los cambios, seleccione **Confirmar** y, a continuación, seleccione **Sí**.

1. Sincronización (o inserción) de los cambios en el repositorio remoto.

    Si se solicita, usa la cuenta de GitHub para autenticar y autorizar la sincronización.

#### Tarea 3: Crear una solicitud de incorporación de cambios en la rama principal del repositorio

Puedes usar una solicitud de incorporación de cambios para sugerir cambios en la rama principal del repositorio. Después de crear una solicitud de incorporación de cambios, puedes revisar los cambios, comprobar que se han superado las comprobaciones y después combinar los cambios en la rama principal. GitHub Copilot puede ayudarte a generar un resumen de la solicitud de incorporación de cambios para ayudar a los revisores a comprender los cambios.

Completa los siguientes pasos para usar esta sección del ejercicio:

1. Abra el repositorio de GitHub en un explorador web.

1. Abra la pestaña **Solicitudes de incorporación de cambios**.

1. Seleccione **Nueva solicitud de incorporación de cambios**.

1. En **Comparar cambios**, asegúrese de que la **base** esté configurada para la rama **principal**.

1. Asegúrese de que **comparación** esté configurado para la rama de **disponibilidad de libros**.

    Después de configurar las ramas, se muestra una comparación de los cambios entre **principal** y **disponibilidad de libros**. Deberías ver los cambios realizados en los archivos CommonActions.cs, ConsoleApp.cs y JsonDaa.cs.

1. Seleccione **Crear solicitud de incorporación de cambios**.

1. Escribe un título para la solicitud de incorporación de cambios.

    Los miembros de una empresa con una suscripción a GitHub Copilot Enterprise pueden usar GitHub Copilot para generar un resumen de una solicitud de incorporación de cambios. El resumen detallado ayuda a los revisores a comprender los cambios.

1. Usa GitHub Copilot para generar el resumen de una solicitud de cambios.

    Para generar el resumen, selecciona el botón Acciones de Copilot y después **Resumen**.

    Puedes usar la pestaña Vista previa para revisar el resumen de la solicitud de incorporación de cambios generado por GitHub Copilot.

1. Asegúrese de que el título y la descripción reflejen las actualizaciones del código y, a continuación, seleccione **Crear solicitud de incorporación de cambios**.

1. Espere a que se completen las comprobaciones y compruebe que todas las comprobaciones pasadas y que no haya conflictos con la rama base.

    Las comprobaciones pueden tardar un minuto en completarse. Debe solucionar cualquier problema que se identifique antes de poder combinar los cambios en la rama principal.

1. Para combinar los cambios en la rama principal, seleccione **Solicitud de incorporación de cambios de mezcla** y, a continuación, seleccione **Confirmar combinación**.

    Ten en cuenta que puedes eliminar la rama de disponibilidad de libros después de combinar los cambios.

1. Abra Visual Studio Code.

1. Cambie a la rama **principal** del repositorio.

1. **Extraer** los cambios del repositorio remoto.

    Si se te solicita, usa la cuenta de GitHub para autenticar y autorizar la extracción.

1. Compruebe que los cambios realizados en la rama de **disponibilidad de libros**estén ahora en la rama **principal**.

    Los cambios realizados en los archivos CommonActions.cs y ConsoleApp.cs deberían estar presentes en la rama principal.

#### Resumen: Ejercicio 6

En este ejercicio, has probado tu código y después has combinado tus cambios en la rama principal del repositorio. Has confirmado tus cambios en el repositorio local, los has sincronizado con el repositorio remoto y después has creado una solicitud de incorporación de cambios para combinar los cambios en la rama principal del repositorio. Has usado GitHub Copilot para generar un resumen de la solicitud de incorporación de cambios para ayudar a los revisores a comprender los cambios.

## Parte 3: Desarrollo de pruebas unitarias con las herramientas de GitHub Copilot

### Antes de comenzar

#### Información general del proyecto

Tu compañero ha creado un proyecto de prueba denominado UnitTests. Las pruebas unitarias existentes cubren parcialmente las clases de servicio en el proyecto Library.ApplicationCore. El proyecto Library.ApplicationCore contiene la lógica de negocios de un sistema de administración de bibliotecas. El proyecto UnitTests usa el marco xUnit para escribir y ejecutar pruebas unitarias. El proyecto también usa la biblioteca NSubstitute para crear objetos ficticios para las pruebas.

Debes ampliar el proyecto UnitTests para cubrir las clases de acceso a datos en el proyecto Library.Infrastructure.

#### Escenario de laboratorio (parte 3)

GitHub Copilot puede ayudarle a escribir pruebas unitarias para el código. Hay varias maneras de usar GitHub Copilot para generar pruebas unitarias:

- **Generar casos de prueba**: Puede usar GitHub Copilot para generar casos de prueba para el código. Copilot puede sugerir casos de prueba basados en el código que ha escrito. A continuación, puede usar estos casos de prueba para crear pruebas unitarias para el código.
- **Generar métodos de prueba**: Copilot también puede generar métodos de prueba para el código. Puede usar estos métodos de prueba para crear pruebas unitarias para el código.
- **Generar aserciones de prueba**: Copilot puede sugerir aserciones que puede usar en las pruebas unitarias. Estas aserciones pueden ayudarle a comprobar el comportamiento del código.
- **Generar simulacros de prueba**: Copilot puede generar objetos ficticios que puede usar en las pruebas unitarias. Estos objetos ficticios pueden ayudarle a aislar el código que está probando de sus dependencias.
- **Generar datos de prueba**: Copilot puede generar datos de prueba que puede usar en las pruebas unitarias. Estos datos de prueba pueden ayudarle a probar el código con entradas diferentes.
- **Generar código de configuración de prueba**: Copilot puede generar código de instalación para las pruebas unitarias. Este código puede ayudarle a configurar el entorno de prueba antes de ejecutar las pruebas.
- **Generar código de desmontaje de pruebas**: Copilot puede generar código de desmontaje para las pruebas unitarias. Este código puede ayudarle a limpiar el entorno de prueba después de ejecutar las pruebas.

En la parte 3 de este laboratorio, se desarrollan pruebas unitarias para el proyecto Library.Infrastructure.

Parte incluye el ejercicio siguiente:

- Usa GitHub Copilot para evaluar y ampliar el proyecto UnitTests.

### Ejercicio 7: Uso de GitHub Copilot para evaluar y ampliar el proyecto UnitTests

En este ejercicio, usará GitHub Copilot para completar las siguientes tareas:

1. Usa GitHub Copilot para evaluar el proyecto UnitTests existente.

1. Amplía el proyecto UnitTests para empezar a probar las clases de acceso a datos.

#### Tarea 1: Usar GitHub Copilot para evaluar el proyecto UnitTests existente

El proyecto UnitTests implementa actualmente la siguiente estructura de carpetas:

- UnitTests\
  - ApplicationCore\
    - LoanService\
      - ExtendLoan.cs
      - ReturnLoan.cs
    - PatronService\
      - RenewMembership.cs
  - LoanFactory.cs
  - PatronFactory.cs

Esta estructura refleja y es compatible con la parte de Servicios del proyecto ApplicationCore.

- ApplicationCore\
  - Services\
    - LoanService.cs: contiene los métodos ExtendLoan y ReturnLoan.
    - PatronService.cs: contiene el método RenewMembership.

La evaluación de las pruebas unitarias existentes te ayudará a desarrollar pruebas unitarias para las clases de acceso a datos en el proyecto Library.Infrastructure.

Use los siguientes pasos para usar esta sección del ejercicio:

1. Cierra todos los archivos que hayas abierto en el editor.

1. Abra la vista Chat.

1. Agrega los siguientes archivos al contexto de chat: **LoanFactory.cs**, **PatronFactory.cs**, **ExtendLoan.cs**, **ReturnLoan.cs**, **RenewMembership.cs**, **LoanService.cs**, **PatronService.cs**.

    Los archivos se encuentran en las carpetas "tests/UnitTests", "tests/UnitTests/ApplicationCore/LoanService", "tests/UnitTests/ApplicationCore/PatronService" y "src/Library.ApplicationCore/Services".

1. Escriba lo siguiente:

    ```plaintext
    @workspace Explain the approach to unit testing that's been implemented in this workspace.
    ```

    Este mensaje pide a GitHub Copilot que explique el enfoque de las pruebas unitarias en el contexto del área de trabajo. En el mensaje se incluyen varios archivos para proporcionar contexto para la respuesta.

1. Dedique un minuto a revisar la respuesta de GitHub Copilot.

    Debería ver una explicación similar a la siguiente descripción:

    - Simulación de dependencias: las pruebas usan NSubstitute para crear implementaciones ficticias de interfaces.
    - Organización de prueba: Las pruebas se organizan en archivos independientes en función de los métodos que se están probando. Por ejemplo, los métodos ExtendLoan y ReturnLoan se prueban en archivos independientes dentro de la carpeta LoanService.
    - Aserciones: Las aserciones se usan para comprobar el resultado esperado de cada prueba.
    - Escenarios de prueba: Las pruebas abarcan varios escenarios para cada método, como devolver diferentes estados en función de la entrada.
    - Aislamiento: Cada prueba está aislada de otras personas para prevenir efectos secundarios.
    - Métodos de fábrica: Los métodos de fábrica se usan para crear datos de prueba de forma coherente.

1. Escriba lo siguiente:

    ```plaintext
    @workspace What are the benefits of this approach to unit testing?
    ```

1. Dedique un minuto a revisar la respuesta de GitHub Copilot.

    Debería ver una explicación que identifique una lista de ventajas similar a la siguiente lista:

    - Aislamiento de dependencias: El uso de simulacros aísla la unidad de trabajo de sus dependencias.
    - Repetibilidad y coherencia: Los métodos de fábrica proporcionan una manera coherente de crear datos de prueba.
    - Legibilidad y mantenimiento: Los métodos de prueba descriptivos y una disposición clara de los pasos de prueba mejoran la legibilidad de las pruebas.
    - Cobertura completa: Probar varios escenarios garantiza que el código sea sólido y controle diferentes casos perimetrales.
    - Separación de problemas: La separación de la creación de datos de prueba de la propia lógica de prueba mantiene las pruebas limpias y centradas en el comportamiento que se está probando.
    - Comentarios inmediatos: La ejecución de pruebas unitarias proporciona comentarios inmediatos sobre la exactitud del código.

1. Agrega los siguientes archivos al contexto de chat: **ExtendLoan.cs**, **ReturnLoan.cs**, **RenewMembership.cs**, **LoanFactory.cs**, **PatronFactory.cs**, **LoanService.cs**, **PatronService.cs**.

1. Escriba lo siguiente:

    ```plaintext
    @workspace How can I extend the `UnitTests` project to begin testing methods in the `Library.Infrastructure` project? Provide a process overview.
    ```

    Esta indicación pide a GitHub Copilot que proporcione una información general sobre el proceso de ampliación del proyecto UnitTests para comenzar a probar métodos en el proyecto Library.Infrastructure. En el mensaje se incluyen varios archivos para proporcionar contexto para la respuesta.

1. Dedique un minuto a revisar la respuesta de GitHub Copilot.

    Debería ver una explicación similar a la siguiente descripción:

    ```markdown
    1. Add Project Reference:

      - Open the UnitTests.csproj file located at tests/UnitTests/UnitTests.csproj.
      - Add a reference to the Library.Infrastructure project.

    2. Identify methods to test:

      - Identify the methods in the Library.Infrastructure project that need to be tested. For example, if you want to test the LoanService class, identify the methods in the LoanService class that need to be tested.

    3. Create Test Classes:

      - Create new test classes in the tests/UnitTests directory to test the methods in the Library.Infrastructure project. For example, if you want to test LoanService, create a file named LoanServiceTests.cs.

    4. Write Unit Tests:

      - In the newly created test classes, write unit tests for the methods in the Library.Infrastructure project. Use the xUnit framework for writing tests and NSubstitute for mocking dependencies.

    5. Run Tests:

      - Use Visual Studio Code's integrated terminal or the Test Explorer to run the tests.
      - Ensure that the tests are discovered and executed correctly.
    ```

#### Tarea 2: Ampliar el proyecto UnitTests para empezar a probar las clases de acceso a datos

En esta sección del ejercicio, usarás GitHub Copilot para ayudarte a crear pruebas unitarias para el proyecto Library.Infrastructure.

El proyecto Library.Infrastructure contiene clases de acceso a datos que interactúan con el sistema de archivos para cargar y guardar datos. El proyecto incluye las siguientes clases:

- JsonData: Clase que carga y guarda datos JSON.
- JsonLoanRepository: Clase que implementa la interfaz ILoanRepository y usa la clase JsonData para cargar y ahorrar datos de préstamo.
- JsonPatronRepository: Clase que implementa la interfaz IPatronRepository y usa la clase JsonData para cargar y guardar datos de patrón.

Empezarás escribiendo pruebas unitarias para la clase JsonLoanRepository.

Use los siguientes pasos para usar esta sección del ejercicio:

1. Agrega el siguiente archivo de proyecto al contexto chat: **UnitTests.csproj**.

1. Escriba el siguiente símbolo del sistema en la vista Chat:

    ```plaintext
    @workspace Explain how to add a reference to the Library.Infrastructure project inside `UnitTests.csproj`.
    ```

    Esta solicitud pide a GitHub Copilot que explique cómo agregar una referencia al proyecto Library.Infrastructure dentro del archivo UnitTests.csproj.

1. Use la respuesta de GitHub Copilot para actualizar el archivo UnitTests.csproj.

    El archivo UnitTests.csproj actualizado debe tener un aspecto similar al siguiente código XML:

    ```xml

    <Project Sdk="Microsoft.NET.Sdk">
      <PropertyGroup>
        <TargetFramework>net8.0</TargetFramework>
        <ImplicitUsings>enable</ImplicitUsings>
        <Nullable>enable</Nullable>
        <IsPackable>false</IsPackable>
        <IsTestProject>true</IsTestProject>
      </PropertyGroup>
      <ItemGroup>
        <PackageReference Include="coverlet.collector" Version="6.0.0" />
        <PackageReference Include="Microsoft.NET.Test.Sdk" Version="17.8.0" />
        <PackageReference Include="NSubstitute" Version="5.1.0" />
        <PackageReference Include="xunit" Version="2.5.3" />
        <PackageReference Include="xunit.runner.visualstudio" Version="2.5.3" />
      </ItemGroup>
      <ItemGroup>
        <Using Include="Xunit" />
      </ItemGroup>
      <ItemGroup>
        <ProjectReference Include="..\..\src\Library.ApplicationCore\Library.ApplicationCore.csproj" />
        <ProjectReference Include="..\..\src\Library.Infrastructure\Library.Infrastructure.csproj" />
      </ItemGroup>
    </Project>

    ```

1. Abre el archivo **JsonLoanRepository.cs**.

    JsonLoanRepository.cs se encuentra en la carpeta "src/Library.Infrastructure/Data/".

1. Dedica un minuto a revisar el archivo **JsonLoanRepository.cs**.

    ```csharp

    using Library.ApplicationCore;
    using Library.ApplicationCore.Entities;
    namespace Library.Infrastructure.Data;
    public class JsonLoanRepository : ILoanRepository
    {
        private readonly JsonData _jsonData;
        public JsonLoanRepository(JsonData jsonData)
        {
            _jsonData = jsonData;
        }
        public async Task<Loan?> GetLoan(int id)
        {
            await _jsonData.EnsureDataLoaded();
    
            foreach (Loan loan in _jsonData.Loans!)
            {
                if (loan.Id == id)
                {
                    Loan populated = _jsonData.GetPopulatedLoan(loan);
                    return populated;
                }
            }
            return null;
        }
        public async Task UpdateLoan(Loan loan)
        {
            Loan? existingLoan = null;
            foreach (Loan l in _jsonData.Loans!)
            {
                if (l.Id == loan.Id)
                {
                    existingLoan = l;
                    break;
                }
            }
            if (existingLoan != null)
            {
                existingLoan.BookItemId = loan.BookItemId;
                existingLoan.PatronId = loan.PatronId;
                existingLoan.LoanDate = loan.LoanDate;
                existingLoan.DueDate = loan.DueDate;
                existingLoan.ReturnDate = loan.ReturnDate;
                await _jsonData.SaveLoans(_jsonData.Loans!);
                await _jsonData.LoadData();
            }
        }
    }

    ```

1. Observa los siguientes detalles sobre la clase **JsonLoanRepository**:

    - La clase JsonLoanRepository contiene dos métodos: GetLoan y UpdateLoan.
    - La clase JsonLoanRepository usa un objeto JsonData para cargar y guardar datos de préstamos.

    Empezarás escribiendo pruebas unitarias para el método GetLoan.

1. Crea la siguiente estructura de carpetas bajo el proyecto **UnitTests**.

    - Infrastructure\
        - JsonLoanRepository\

    Esta estructura de carpetas refleja el enfoque usado para las pruebas unitarias de Library.ApplicationCore.

1. Crea un archivo de clase denominado **GetLoan** en la carpeta JsonLoanRepository.

1. Dedica un minuto a tener en cuenta los requisitos de constructor de campo y clase para las pruebas unitarias de GetLoan.

    El método JsonLoanRepository.GetLoan recibe un parámetro de Id. de préstamo cuando se llama. El método usa "_jsonData.EnsureDataLoaded" para obtener los últimos datos JSON, y "_jsonData.Loans" para buscar un préstamo coincidente. Si el método encuentra un Id. de préstamo coincidente, devuelve un objeto de préstamo rellenado (rellenado). Si el método no puede encontrar un Id. de préstamo que coincida, devuelve nulo.

    Para las pruebas unitarias GetLoan:

    - Puedes usar un objeto de repositorio de préstamo ficticio ("_mockLoanRepository") para ayudar a probar el caso en el que se encuentra un Id. coincidente. Cargue el simulacro con el identificador que desea encontrar. La clase ReturnLoanTest muestra cómo simular la interfaz ILoanRepository y crear instancias de un objeto de repositorio de préstamo ficticio.

    - Puedes usar un objeto de repositorio de préstamos no ficticios ("_jsonLoanRepository") para probar el caso en el que no se encuentra ningún Id. coincidente. Solo tiene que especificar un identificador de préstamo que sepa que no está en el archivo (nada más de 100 debería funcionar).

    - Necesitarás un objeto JsonData para crear un objeto JsonLoanRepository no ficticio. Dado que el proyecto UnitTests no tiene acceso al objeto JsonData creado por el proyecto ConsoleApp, deberás crear uno mediante la interfaz IConfiguration.

1.  Agrega los siguientes archivos al contexto chat: **JsonLoanRepository.cs**, **ReturnLoan.cs**, **LoanService.cs**, **LoanFactory.cs**, **JsonData.cs**.

1. Escriba lo siguiente:

    ```plaintext
    @workspace Create fields and a class constructor for the `GetLoan.cs` file. The class will be used to create unit tests for the GetLoan method in the `JsonLoanRepository.cs` file. Create the following private readonly fields: `_mockLoanRepository`, `_jsonLoanRepository`, `_configuration`, and `_jsonData`. Instantiate the fields in the `GetLoanTest` constructor. Use `ConfigurationBuilder` to create a `_configuration` object that can be used to instantiate the JsonData object.
    ```

    Este mensaje pide a GitHub Copilot que sugiera campos y un constructor de clase.

1. Dedique un minuto a revisar la respuesta de GitHub Copilot.

    Debería ver una sugerencia de código similar al siguiente fragmento de código:

    ```csharp

    using NSubstitute;
    using Library.ApplicationCore;
    using Library.ApplicationCore.Entities;
    using Library.ApplicationCore.Interfaces;
    using Library.Infrastructure.Data;
    using Microsoft.Extensions.Configuration;
    namespace UnitTests.Infrastructure.JsonLoanRepository;
    public class GetLoanTest
    {
        private readonly ILoanRepository _mockLoanRepository;
        private readonly JsonLoanRepository _jsonLoanRepository;
        private readonly IConfiguration _configuration;
        private readonly JsonData _jsonData;
        public GetLoanTest()
        {
            _mockLoanRepository = Substitute.For<ILoanRepository>();
            _configuration = new ConfigurationBuilder()
                .AddJsonFile("appsettings.json")
                .Build();
            _jsonData = new JsonData(_configuration);
            _jsonLoanRepository = new JsonLoanRepository(_jsonData);
        }
        // Add test methods here
    }

    ```

1. Usa la sugerencia de código proporcionada por GitHub Copilot para actualizar **GetLoan.cs**.

1. Observe los siguientes problemas:

    - Hay un conflicto entre el espacio de nombres y el uso de JsonLoanRepository en el código. Debes actualizar el espacio de nombres en GetLoans.cs para seguir el patrón usado en los archivos ReturnLoan.cs y RenewMembership.cs.

    - Si ILoanRepository no se reconoce en el código, es posible que tengas que agregar una directiva using para Library.ApplicationCore a la parte superior del archivo.

    - Si el objeto _configuration no se crea una instancia correctamente, es posible que debas actualizar la línea de código que contiene ConfigurationBuilder. Puedes simplificar el código para usar "_configuration = new ConfigurationBuilder(). Build();".

    - Si GitHub Copilot sugiere un "uso de Library.ApplicationCore.Interfaces", puedes eliminarlo de la parte superior del archivo.

1. Actualiza el archivo **GetLoan.cs** para que coincida con el siguiente fragmento de código:

    ```csharp

    using NSubstitute;
    using Library.ApplicationCore;
    using Library.ApplicationCore.Entities;
    using Library.Infrastructure.Data;
    using Microsoft.Extensions.Configuration;
    namespace UnitTests.Infrastructure.JsonLoanRepositoryTests;
    public class GetLoanTest
    {
        private readonly ILoanRepository _mockLoanRepository;
        private readonly JsonLoanRepository _jsonLoanRepository;
        private readonly IConfiguration _configuration;
        private readonly JsonData _jsonData;
        public GetLoanTest()
        {
            _mockLoanRepository = Substitute.For<ILoanRepository>();
            _configuration = new ConfigurationBuilder().Build();
            _jsonData = new JsonData(_configuration);
            _jsonLoanRepository = new JsonLoanRepository(_jsonData);
        }
    }

    ```

    Las actualizaciones de código abordan los problemas identificados en el paso anterior. Al compilar el proyecto se resolverán los problemas identificados en el editor.

1. Agrega los siguientes archivos al contexto de chat: **JsonLoanRepository.cs**, **ReturnLoan.cs**, **LoanService.cs**, **LoanFactory.cs**, **JsonData.cs**, **Loans.json**.

1. Selecciona el contenido del archivo GetLoan.cs y después introduce la siguiente indicación en la vista Chat:

    ```plaintext
    @workspace Update the selection to include a unit test for the `JsonLoanRepository.GetLoan` method. The unit test should test the case where a loan ID is found in the data. Use `_mockLoanRepository` to arrange the expected return loan. Use `_jsonLoanRepository` to return an actual loan. Asserts should verify that the return loan ID matches the expected loan ID. Use a loan ID that exists in the `Loans.json` file.
    ```

    Esta solicitud pide a GitHub Copilot que sugiera una prueba unitaria para el método JsonLoanRepository.GetLoan. La prueba unitaria debe probar el caso en el que se encuentra un identificador de préstamo en los datos. La prueba debe usar "_mockLoanRepository" para organizar el préstamo devuelto esperado, "_jsonLoanRepository" para devolver un préstamo real, y verificar que el Id. del préstamo devuelto coincide con el Id. del préstamo esperado. El Id. del préstamo debe existir en el archivo Loans.json.

1. Dedique un minuto a revisar la respuesta de GitHub Copilot.

    Debería ver una sugerencia de código similar al siguiente fragmento de código:

    ```csharp

    using NSubstitute;
    using Library.ApplicationCore;
    using Library.ApplicationCore.Entities;
    using Library.Infrastructure.Data;
    using Microsoft.Extensions.Configuration;
    using Xunit;
    namespace UnitTests.Infrastructure.JsonLoanRepositoryTests;
    public class GetLoanTest
    {
        private readonly ILoanRepository _mockLoanRepository;
        private readonly JsonLoanRepository _jsonLoanRepository;
        private readonly IConfiguration _configuration;
        private readonly JsonData _jsonData;
        public GetLoanTest()
        {
            _mockLoanRepository = Substitute.For<ILoanRepository>();
            _configuration = new ConfigurationBuilder().Build();
            _jsonData = new JsonData(_configuration);
            _jsonLoanRepository = new JsonLoanRepository(_jsonData);
        }
        [Fact(DisplayName = "JsonLoanRepository.GetLoan: Returns loan when loan ID is found")]
        public async Task GetLoan_ReturnsLoanWhenLoanIdIsFound()
        {
            // Arrange
            var loanId = 1; // Use a loan ID that exists in the Loans.json file
            var expectedLoan = new Loan { Id = loanId, BookItemId = 101, PatronId = 202, LoanDate = DateTime.Now, DueDate = DateTime.Now.AddDays(14) };
            _mockLoanRepository.GetLoan(loanId).Returns(expectedLoan);
            await _jsonData.EnsureDataLoaded(); // Ensure data is loaded
            // Act
            var actualLoan = await _jsonLoanRepository.GetLoan(loanId);
            // Assert
            Assert.NotNull(actualLoan);
            Assert.Equal(expectedLoan.Id, actualLoan?.Id);
        }
    }

    ```

1. Usa la sugerencia de código proporcionada por GitHub Copilot para actualizar **GetLoan.cs**.

    El método JsonLoanRepository.GetLoan llama a "_jsonData.EnsureDataLoaded" para asegurarse de que se cargan los datos JSON. Puedes eliminar la línea de código que llama a "_jsonData.EnsureDataLoaded" en el método de prueba si se incluye.

    Si la clase Préstamo no se reconoce en tu código, asegúrate de que tienes una instrucción "using Library.ApplicationCore.Entities" en la parte superior del archivo GetLoan.cs. La clase Préstamo se encuentra en el espacio de nombres Library.ApplicationCore.Entities.

1. Compila la solución AccelerateDevGitHubCopilot para asegurarte de que no haya errores.

1. Use la característica de autocompletar de GitHub Copilot para crear una prueba para el caso en el que no se encuentra el identificador del préstamo.

    Crea una línea en blanco después del método GetLoan_ReturnsLoanWhenLoanIdIsFound.

    Acepte las sugerencias de autocompletar para crear un nuevo método de prueba.

1. Dedique un minuto a revisar la respuesta de GitHub Copilot.

    La característica de autocompletar de GitHub Copilot probablemente simulará un préstamo esperado aunque no sea necesario. Puedes eliminar el código que simula un préstamo esperado, pero necesitas un Id. de préstamo que no exista en el archivo Loans.json.

    Debería ver una sugerencia de código similar a uno de los siguientes fragmentos de código:

    ```csharp

    [Fact(DisplayName = "JsonLoanRepository.GetLoan: Returns null when loan ID is not found")]
    public async Task GetLoan_ReturnsNullWhenLoanIdIsNotFound()
    {
        // Arrange
        var loanId = 999; // Use a loan ID that does not exist in the Loans.json file
        var expectedLoan = new Loan { Id = loanId, BookItemId = 101, PatronId = 202, LoanDate = DateTime.Now, DueDate = DateTime.Now.AddDays(14) };
        _mockLoanRepository.GetLoan(loanId).Returns(expectedLoan);
        // Act
        var actualLoan = await _jsonLoanRepository.GetLoan(loanId);
        // Assert
        Assert.Null(actualLoan);
    }

    ```

1. Acepta la sugerencia de autocompletar que asigna un valor loanId que no está en el conjunto de datos.

    Si ninguna de las sugerencias asigna números loanId que no estén en el conjunto de datos, puedes usar el método abreviado de teclado **Ctrl+Entrar** para enumerar sugerencias adicionales.

1. Observe que las pruebas unitarias requieren acceso a los archivos de datos JSON.

    El método JsonLoanRepository.GetLoan usa un objeto JsonData para cargar y guardar datos de préstamo.

    Los archivos de datos JSON se encuentran en la carpeta "Library.Console\Json". Es necesario actualizar el archivo UnitTests.csproj para incluir estos archivos en el proyecto de prueba.

1. Agrega el siguiente fragmento XML al archivo **UnitTests.csproj**:

    ```xml

    <ItemGroup>
        <None Include="..\..\src\Library.Console\Json\**\*">
            <Link>Json\%(RecursiveDir)%(FileName)%(Extension)</Link>
            <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
        </None>
    </ItemGroup>

    ```

    Esto garantiza que los archivos de datos JSON se copien en el directorio de salida cuando se ejecuten las pruebas.

#### Tarea 3: Comprueba tu trabajo

Hay varias maneras de ejecutar las pruebas unitarias para la clase JsonLoanRepository. Puedes usar el Explorador de pruebas de Visual Studio Code, el terminal integrado o el comando "dotnet test".

Completa los siguientes pasos para usar esta sección del ejercicio:

1. Asegúrese de que tiene abierto el archivo GetLoans.cs en el editor.

1. Compile la solución y asegúrese de que no haya errores.

    Haga clic con el botón derecho en **AccelerateDevGitHubCopilot** y seleccione **Compilar**.

1. Observe el "botón de reproducción verde" a la izquierda de los métodos de prueba.

1. Abra la vista Explorador de pruebas de Visual Studio Code.

    Para abrir la vista Explorador de pruebas, seleccione el icono con forma circular de la barra de actividades de la izquierda. El Explorador de pruebas se etiqueta como "Pruebas" en la interfaz de usuario.

    El Explorador de pruebas es una vista de árbol que muestra todos los casos de prueba del área de trabajo. Puede ejecutar o depurar los casos de prueba y ver los resultados de las pruebas mediante el Explorador de pruebas.

1. Expande **UnitTests** y los nodos subyacentes para buscar **GetLoanTest**.

1. Ejecute el **JsonLoanRepository.GetLoan: Devuelve el préstamo cuando se encuentra el identificador del préstamo** caso de prueba.

    > [!NOTE]
    > GitHub Copilot puede haber denominado el método de prueba de forma diferente. Ejecuta el método de prueba que usa un Id. de préstamo que existe en los datos.

1. Observe que los resultados de la prueba se muestran en la vista Explorador de pruebas y en el Editor.

    Debería ver una marca de verificación verde que indique la prueba superada.

1. Use el Editor para ejecutar el **JsonLoanRepository.GetLoan: Devuelve null cuando no se encuentra el identificador del préstamo ** en caso de prueba.

1. Observe que los resultados de la prueba se muestran en la vista Explorador de pruebas y en el Editor.

    Para ejecutar la prueba desde el Editor, seleccione el botón de reproducción verde situado a la izquierda del método de prueba.

1. Asegúrese de que el **JsonLoanRepository.GetLoan: Devuelve null cuando no se encuentra el identificador de préstamo ** superada la prueba.

    Debería ver una marca de verificación verde a la izquierda de ambas pruebas.

#### Resumen: Ejercicio 7

En este ejercicio, has usado GitHub Copilot para evaluar el proyecto UnitTests existente y ampliar el proyecto para comenzar a probar las clases de acceso a datos en el proyecto Library.Infrastructure. Has agregado una referencia al proyecto Library.Infrastructure en el archivo UnitTests.csproj y has creado pruebas unitarias para la clase JsonLoanRepository. Has usado GitHub Copilot para ayudarte a escribir las pruebas unitarias para el método GetLoan en la clase JsonLoanRepository. Has ejecutado las pruebas unitarias usando el Explorador de pruebas de Visual Studio Code y has comprobado que se han superado.

## Parte 4: Refactorización y mejora de las secciones de código mediante las herramientas de GitHub Copilot

### Antes de comenzar

#### Información general del proyecto

Tú y tu compañero de trabajo habéis completado la fase inicial de desarrollo del proyecto y ahora estáis investigando formas de refactorizar y mejorar vuestro código base.

La refactorización de código es un proceso que reestructura el código existente sin cambiar su comportamiento externo. La refactorización se suele usar para mejorar un aspecto específico del código. GitHub Copilot puede ayudarle a refactorizar el código mediante la sugerencia de cambios que mejoran la calidad, confiabilidad, rendimiento y seguridad del código.

#### Escenario de laboratorio (parte 4)

En la parte 4 de este laboratorio, usarás GitHub Copilot para refactorizar las siguientes secciones de código:

- Refactoriza la clase EnumHelper para usar diccionarios en lugar de reflexión. El uso de diccionarios mejora el rendimiento al reducir la sobrecarga de reflexión. La eliminación de la reflexión también mejora la legibilidad, el mantenimiento y la seguridad del código.

- Los métodos de acceso a datos se refactorizarán para usar LINQ (Language Integrated Query) en lugar de bucles foreach. El uso de LINQ proporciona una manera más concisa y legible de consultar colecciones, bases de datos y documentos XML. El uso de LINQ puede mejorar la legibilidad, el mantenimiento y el rendimiento del código.

Parte incluye los siguientes ejercicios:

- Usa GitHub Copilot para refactorizar la clase EnumHelper.
- Usa GitHub Copilot para mejorar las clases de acceso a datos con LINQ.

### Ejercicio 8: Uso de GitHub Copilot para refactorizar la clase EnumHelper

La reflexión es una característica eficaz que permite inspeccionar y manipular objetos en tiempo de ejecución. Sin embargo, la reflexión puede ser lenta y hay posibles riesgos de seguridad asociados a la reflexión que se deben tener en cuenta.

La clase EnumHelper existente usa la reflexión para recuperar el atributo descripción de un valor de enumeración. Puede refactorizar la clase EnumHelper para usar diccionarios en lugar de reflexión. El uso de diccionarios puede mejorar el rendimiento y eliminar cualquier problema de seguridad asociado al uso de la reflexión.

En este ejercicio, usará GitHub Copilot para ayudarle a refactorizar la clase EnumHelper.

Sigue los siguientes pasos para completar este ejercicio:

1. Use la vista Explorador de soluciones para abrir el archivo EnumHelper.cs.

    EnumHelper.cs se encuentra en la carpeta "src/Library.ApplicationCore/Enums".

    ```csharp

    using System.ComponentModel;
    using System.Reflection;
    namespace Library.ApplicationCore.Enums;
    public static class EnumHelper
    {
        public static string GetDescription(Enum value)
        {
            if (value == null)
                return string.Empty;
            FieldInfo fieldInfo = value.GetType().GetField(value.ToString())!;
            DescriptionAttribute[] attributes =
                (DescriptionAttribute[])fieldInfo.GetCustomAttributes(typeof(DescriptionAttribute), false);
            if (attributes != null && attributes.Length > 0)
            {
                return attributes[0].Description;
            }
            else
            {
                return value.ToString();
            }
        }
    }

    ```

1. Abre la vista Chat y después agrega los siguientes archivos al contexto de chat: **EnumHelper.cs**, **LoanExtensionStatus.cs**, **LoanReturnStatus.cs**, **MembershipRenewalStatus.cs**.

1. Escriba lo siguiente:

    ```plaintext
    @workspace I want to refactor the `EnumHelper` class using dictionaries rather than reflection to get enum description attributes. I want a separate dictionary for each enum. The enum values are in the `LoanExtensionStatus.cs`, `LoanReturnStatus.cs`, and `MembershipRenewalStatus.cs` files. Explain how to update the EnumHelper class to use dictionaries and provide the updated code.
    ```

    Este mensaje pide a GitHub Copilot que proporcione una explicación de cómo actualizar la clase EnumHelper para usar diccionarios en lugar de reflexión. También solicita el código actualizado que usa diccionarios para cada valor de enumeración.

1. Dedique un minuto a revisar la explicación proporcionada por GitHub Copilot.

    La explicación debe ser similar a la siguiente descripción:

    ```markdown
    To refactor the EnumHelper class to use dictionaries for each enum, you need to create a dictionary for each enum type that maps the enum values to their descriptions. This will eliminate the need for reflection at runtime.

    Here's how you can update the EnumHelper class:

    1. Create dictionaries for each enum type.
    2. Populate these dictionaries with the enum values and their corresponding descriptions.
    3. Update the GetDescription method to use these dictionaries.

    Below is the updated code for the EnumHelper class:

    ```

    ```csharp

    using System.ComponentModel;
    using System.Collections.Generic;
    namespace Library.ApplicationCore.Enums
    {
        public static class EnumHelper
        {
            private static readonly Dictionary<MembershipRenewalStatus, string> MembershipRenewalStatusDescriptions = new()
            {
                { MembershipRenewalStatus.Success, "Membership renewal was successful." },
                { MembershipRenewalStatus.PatronNotFound, "Patron not found." },
                { MembershipRenewalStatus.TooEarlyToRenew, "It is too early to renew the membership." },
                { MembershipRenewalStatus.LoanNotReturned, "Cannot renew membership due to an outstanding loan." },
                { MembershipRenewalStatus.Error, "Cannot renew membership due to an error." }
            };
            private static readonly Dictionary<LoanReturnStatus, string> LoanReturnStatusDescriptions = new()
            {
                { LoanReturnStatus.Success, "Book was successfully returned." },
                { LoanReturnStatus.LoanNotFound, "Loan not found." },
                { LoanReturnStatus.AlreadyReturned, "Cannot return book as the book is already returned." },
                { LoanReturnStatus.Error, "Cannot return book due to an error." }
            };
            private static readonly Dictionary<LoanExtensionStatus, string> LoanExtensionStatusDescriptions = new()
            {
                { LoanExtensionStatus.Success, "Book loan extension was successful." },
                { LoanExtensionStatus.LoanNotFound, "Loan not found." },
                { LoanExtensionStatus.LoanExpired, "Cannot extend book loan as it already has expired. Return the book instead." },
                { LoanExtensionStatus.MembershipExpired, "Cannot extend book loan due to expired patron's membership." },
                { LoanExtensionStatus.LoanReturned, "Cannot extend book loan as the book is already returned." },
                { LoanExtensionStatus.Error, "Cannot extend book loan due to an error." }
            };
            public static string GetDescription(Enum value)
            {
                if (value == null)
                    return string.Empty;
                return value switch
                {
                    MembershipRenewalStatus status => MembershipRenewalStatusDescriptions[status],
                    LoanReturnStatus status => LoanReturnStatusDescriptions[status],
                    LoanExtensionStatus status => LoanExtensionStatusDescriptions[status],
                    _ => value.ToString()
                };
            }
        }
    }

    ```

    ```markdown

    This refactored EnumHelper class uses dictionaries to store the descriptions for each enum type. The GetDescription method now uses pattern matching to determine the type of the enum and retrieves the description from the appropriate dictionary. This approach avoids the use of reflection and improves performance.

    ```

    > [!NOTE]
    > Si GitHub Copilot no rellena los diccionarios con las descripciones correctas, asegúrese de que la extensión de GitHub Copilot no solicite un reinicio. Si es así, reinicie la extensión e inténtelo de nuevo.

1. Usa la clase EnumHelper sugerida de GitHub Copilot para actualizar tu archivo EnumHelper.cs.

1. Asegúrate de que la clase EnumHelper actualizada usa los valores de enumeración de los archivos LoanExtensionStatus.cs, LoanReturnStatus.cs y MembershipRenewalStatus.cs.

    Abra cada uno de los archivos de enumeración y compruebe que los valores de enumeración de los diccionarios son correctos. Si hay discrepancias, haga que GitHub Copilot actualice los diccionarios de cada enumeración individualmente. Por ejemplo, puedes usar la siguiente solicitud para la enumeración LoanExtensionStatus:

    ```plaintext
    @workspace Use the description values in LoanExtensionStatus.cs to update the LoanExtensionStatus dictionary in the EnumHelper class. Provide the updated code for the LoanExtensionStatus dictionary in the EnumHelper class.
    ```

    Si es necesario, usa el mismo enfoque para las enumeraciones LoanReturnStatus y MembershipRenewalStatus.

1. Dedica un minuto a revisar el método **GetDescription**.

    ```csharp

    public static string GetDescription(Enum value)
    {
        if (value == null)
            return string.Empty;
        return value switch
        {
            MembershipRenewalStatus status => MembershipRenewalStatusDescriptions[status],
            LoanReturnStatus status => LoanReturnStatusDescriptions[status],
            LoanExtensionStatus status => LoanExtensionStatusDescriptions[status],
            _ => value.ToString()
        };
    }

    ```

    Este código usa la coincidencia de patrones para determinar el tipo de enumeración y recuperar la descripción del diccionario adecuado. La instrucción de modificador comprueba el tipo del valor de enumeración y devuelve la descripción correspondiente del diccionario. Si el valor de enumeración no se encuentra en el diccionario, el método devuelve el valor de enumeración como una cadena.

    Si pide a GitHub Copilot que refactorice este código y elimine las expresiones lambda, resulta más fácil de leer:

    ```csharp

    public static string GetDescription(Enum value)
    {
        if (value == null)
            return string.Empty;
        switch (value)
        {
            case MembershipRenewalStatus status:
                return MembershipRenewalStatusDescriptions[status];
            case LoanReturnStatus status:
                return LoanReturnStatusDescriptions[status];
            case LoanExtensionStatus status:
                return LoanExtensionStatusDescriptions[status];
            default:
                return value.ToString();
        }
    }

    ```

1. Guarda los cambios en el archivo EnumHelper.cs.

1. Compile la solución para asegurarse de que no hay errores.

    Verá advertencias. Puede ignorarlos por ahora.

#### Resumen: Ejercicio 8

En este ejercicio, has usado GitHub Copilot para refactorizar la clase EnumHelper para usar diccionarios en lugar de reflexión. El uso de diccionarios mejora el rendimiento al reducir la sobrecarga de reflexión. La eliminación de la reflexión también mejora la legibilidad, el mantenimiento y la seguridad del código.

### Ejercicio 9: Uso de GitHub Copilot para mejorar las clases de acceso a datos con LINQ

LINQ (Language Integrated Query) es una característica eficaz en C# que permite consultar colecciones, bases de datos y documentos XML de forma uniforme. LINQ proporciona una manera más concisa y legible de consultar datos en comparación con los bucles foreach tradicionales.

Este ejercicio incluye las siguientes tareas:

- Refactorice los métodos de JsonData.cs para usar LINQ.
- Refactorice los métodos de JsonLoanRepository.cs para usar LINQ.
- Refactorice los métodos de JsonPatronRepository.cs para usar LINQ.

#### Tarea 1: Refactorizar los métodos de JsonData.cs para usar LINQ

La clase JsonData incluye los siguientes métodos de acceso a datos: GetPopulatedPatron, GetPopulatedLoan, GetPopulatedBookItem, GetPopulatedBook. Estos métodos usan bucles foreach para recorrer en iteración las colecciones y rellenar objetos. Puede refactorizar estos métodos para usar LINQ para mejorar la legibilidad y el mantenimiento del código.

Completa los siguientes pasos para usar esta sección del ejercicio:

1. Abra el archivo JsonData.cs.

1. Selecciona el método **GetPopulatedPatron**.

    El método GetPopulatedPatron está diseñado para crear un objeto de usuario completamente rellenado. Copia las propiedades básicas del usuario y rellena su colección Préstamos con objetos de préstamo detallados.

    ```csharp

    public Patron GetPopulatedPatron(Patron p)
    {
        Patron populated = new Patron
        {
            Id = p.Id,
            Name = p.Name,
            ImageName = p.ImageName,
            MembershipStart = p.MembershipStart,
            MembershipEnd = p.MembershipEnd,
            Loans = new List<Loan>()
        };
        foreach (Loan loan in Loans!)
        {
            if (loan.PatronId == p.Id)
            {
                populated.Loans.Add(GetPopulatedLoan(loan));
            }
        }
        return populated;
    }

    ```

1. Abra un chat en línea y escriba un símbolo del sistema que refactorice el método mediante LINQ.

    ```plaintext
    #selection refactor selection to `return new Patron` using LINQ
    ```

1. Dedique un minuto a revisar la actualización sugerida.

    La actualización sugerida debe ser similar al código siguiente:

    ```csharp

    public Patron GetPopulatedPatron(Patron p)
    {
        return new Patron
        {
            Id = p.Id,
            Name = p.Name,
            ImageName = p.ImageName,
            MembershipStart = p.MembershipStart,
            MembershipEnd = p.MembershipEnd,
            Loans = Loans!
                .Where(loan => loan.PatronId == p.Id)
                .Select(GetPopulatedLoan)
                .ToList()
        };
    }

    ```

    En primer lugar, se usa una consulta LINQ para reemplazar el bucle "foreach (préstamo de préstamo en préstamos!)". Con el código LINQ implementado, puedes usar un inicializador de objeto para asignar propiedades de objeto al nuevo objeto de usuario. Esto alivia la necesidad de una instancia rellenada independiente del objeto de usuario. En general, el código actualizado es más corto y legible.

    El código usa el patrón de entrada "p" para asignar algunas propiedades básicas al nuevo objeto de usuario. Después rellena la colección Préstamos con los préstamos asociados al usuario de entrada y transforma cada préstamo utilizando el método GetPopulatedLoan.

    Puedes desglosar la línea de código LINQ que rellena la colección Préstamos:

    - `Loans!`: La expresión "¡Préstamos!"  accede a la colección Préstamos. El operador "!" es un operador que admite valores null, lo que indica que el desarrollador está seguro de que Préstamos no es null. Debes asegurarte de que Préstamos se inicialice correctamente antes de llamar al método GetPopulatedPatron.
    - `.Where(loan => loan.PatronId == p.Id)`: Este código filtra los préstamos para incluir solo los que pertenecen al patrón de entrada "p".
    - `.Select(GetPopulatedLoan)`: Este código transforma cada préstamo filtrado mediante el método GetPopulatedLoan.
    - `.ToList()`: convierte el resultado en una lista de objetos de préstamos.

1. Para aceptar la actualización sugerida, seleccione **Aceptar**.

    Ahora que has visto cómo refactorizar el método GetPopulatedPatron, puedes refactorizar los métodos GetPopulatedLoan, GetPopulatedBookItem y GetPopulatedBook para utilizar también LINQ.

1. Refactoriza los métodos **GetPopulatedLoan**, **GetPopulatedBookItem**, y **GetPopulatedBook** con el mismo enfoque.

    Por ejemplo, use las siguientes indicaciones para refactorizar los tres métodos:

    Para el método **GetPopulatedLoan**:

    ```plaintext
    #selection refactor selection to `return new Loan` using LINQ. Use `GetPopulatedBookItem` for the `BookItem` property. Use `Single` for BookItem and Patron properties.
    ```

    Para el método **GetPopulatedBookItem**:

    ```plaintext
    #selection refactor selection to `return new BookItem` using LINQ. Use `GetPopulatedBook` and `Single` for the `BookItem` property.
    ```

    Para el método **GetPopulatedBook**:

    ```plaintext
    #selection refactor selection to `return new Book` using LINQ. Use `Where` and `Select` for `Author` property. Use `First` author.
    ```

1. Después de aceptar las actualizaciones sugeridas, dedique un minuto a revisar los cambios del código.

    El código actualizado debe tener un aspecto similar al siguiente:

    ```csharp

    public Loan GetPopulatedLoan(Loan l)
    {
        return new Loan
        {
            Id = l.Id,
            BookItemId = l.BookItemId,
            PatronId = l.PatronId,
            LoanDate = l.LoanDate,
            DueDate = l.DueDate,
            ReturnDate = l.ReturnDate,
            BookItem = GetPopulatedBookItem(BookItems!.Single(bi => bi.Id == l.BookItemId)),
            Patron = Patrons!.Single(p => p.Id == l.PatronId)
        };
    }
    public BookItem GetPopulatedBookItem(BookItem bi)
    {
        return new BookItem
        {
            Id = bi.Id,
            BookId = bi.BookId,
            AcquisitionDate = bi.AcquisitionDate,
            Condition = bi.Condition,
            Book = GetPopulatedBook(Books!.Single(b => b.Id == bi.BookId))
        };
    }
    public Book GetPopulatedBook(Book b)
    {
        return new Book
        {
            Id = b.Id,
            Title = b.Title,
            AuthorId = b.AuthorId,
            Genre = b.Genre,
            ISBN = b.ISBN,
            ImageName = b.ImageName,
            Author = Authors!.Where(a => a.Id == b.AuthorId).Select(a => new Author {
                Id = a.Id,
                Name = a.Name
            }).First()
        };
    }

    ```

1. Use la acción inteligente **Explicar** para ver una explicación de las consultas LINQ.

    La acción inteligente **Explicar**proporciona una explicación detallada de las consultas LINQ usadas en el código.

    Por ejemplo, puedes usar la acción inteligente **Explicar** en el método GetPopulatedBook para ver una explicación de la consulta LINQ que se usa para rellenar la propiedad Autor del objeto de libro.

    ```csharp

    Author = Authors!.Where(a => a.Id == b.AuthorId).Select(a => new Author {
        Id = a.Id,
        Name = a.Name
    }).First()

    ```

    La acción inteligente **Explicar** proporciona una explicación detallada de la consulta LINQ que se usa para rellenar la propiedad Autor del objeto de libro.

    Por ejemplo, la explicación podría tener este aspecto:

    ```plaintext
    The active selection is a C# code snippet that assigns a value to the Author property. This value is derived from a collection of Author objects named Authors. The code uses LINQ (Language Integrated Query) to filter and transform the data within this collection.
    
    First, the Authors! expression uses the null-forgiving operator (!) to indicate that Authors is not null, even if the compiler might think otherwise. This is a way to suppress nullable warnings. The Where method is then called on the Authors collection to filter the elements. The lambda expression a => a.Id == b.AuthorId is used to find all Author objects where the Id matches the AuthorId property of another object b.
    
    After filtering, the Select method is used to project each filtered Author object into a new Author object. This is done by creating a new instance of the Author class and copying the Id and Name properties from the original Author object.
    
    Finally, the First method is called to retrieve the first element from the resulting sequence. This means that the Author property will be assigned the first Author object that matches the filter criteria and has been projected into a new Author instance.
    
    This approach ensures that the Author property is set to a new Author object with the same Id and Name as the first matching Author in the Authors collection.
    ```

1. Guarda los cambios en el archivo JsonData.cs.

1. Compile la solución para asegurarse de que no hay errores.

    Verá advertencias. Puede ignorarlos por ahora.

#### Tarea 2: Refactorizar los métodos de JsonLoanRepository.cs para usar LINQ

La clase JsonLoanRepository incluye los métodos de acceso a datos GetLoan y UpdateLoan. Refactorizará estos dos métodos, reemplazando los bucles foreach por LINQ para mejorar la legibilidad y el mantenimiento del código.

Completa los siguientes pasos para usar esta sección del ejercicio:

1. Abre el archivo **JsonLoanRepository.cs**.

1. Selecciona el método **GetLoan**.

    El método GetLoan está diseñado para recuperar un préstamo por su Id.

    ```csharp

    public async Task<Loan?> GetLoan(int id)
    {
        await _jsonData.EnsureDataLoaded();
        foreach (Loan loan in _jsonData.Loans!)
        {
            if (loan.Id == id)
            {
                Loan populated = _jsonData.GetPopulatedLoan(loan);
                return populated;
            }
        }
        return null;
    }

    ```

1. Abra el chat en línea y escriba un símbolo del sistema que refactorice el método mediante LINQ.

    Por ejemplo, escriba el siguiente símbolo del sistema:

    ```plaintext
    #selection refactor selection using LINQ with `_jsonData.Loans!. Use `Where`, `Select` and `GetPopulatedLoan` to return `FirstOrDefault`.
    ```

1. Dedique un minuto a revisar la actualización sugerida.

    La actualización sugerida debe ser similar al código siguiente:

    ```csharp

    public async Task<Loan?> GetLoan(int id)
    {
        await _jsonData.EnsureDataLoaded();
        Loan? loan = _jsonData.Loans!
            .Where(l => l.Id == id)
            .Select(l => _jsonData.GetPopulatedLoan(l))
            .FirstOrDefault();
        return loan;
    }

    ```

    El código actualizado usa LINQ para filtrar la colección de préstamos para incluir solo el préstamo con el identificador especificado. Ten en cuenta que el préstamo debe declararse como que admite valores null (`Loan? loan`). Después transforma el préstamo mediante el método GetPopulatedLoan y devuelve el primer resultado. Si no se encuentra ningún préstamo coincidente, FirstOrDefault devuelve null. El método devuelve este objeto de préstamo, que puede ser nulo si no existe ningún préstamo con el "id" especificado. Este enfoque garantiza que el préstamo devuelto se rellene completamente con todos los datos relacionados necesarios, lo que proporciona una visión completa del registro del préstamo.

    Este código podría simplificarse aún más:

    ```csharp

    public async Task<Loan?> GetLoan(int id)
    {
        await _jsonData.EnsureDataLoaded();
        return _jsonData.Loans!
            .Where(l => l.Id == id)
            .Select(l => _jsonData.GetPopulatedLoan(l))
            .FirstOrDefault();
    }

    ```

1. Para aceptar el método GetLoan actualizado, selecciona **Aceptar**.

1. Selecciona el método **UpdateLoan**.

    ```csharp

    public async Task UpdateLoan(Loan loan)
    {
        Loan? existingLoan = null;
        foreach (Loan l in _jsonData.Loans!)
        {
            if (l.Id == loan.Id)
            {
                existingLoan = l;
                break;
            }
        }
        if (existingLoan != null)
        {
            existingLoan.BookItemId = loan.BookItemId;
            existingLoan.PatronId = loan.PatronId;
            existingLoan.LoanDate = loan.LoanDate;
            existingLoan.DueDate = loan.DueDate;
            existingLoan.ReturnDate = loan.ReturnDate;
            await _jsonData.SaveLoans(_jsonData.Loans!);
            await _jsonData.LoadData();
        }
    }

    ```

1. Abra el chat en línea y escriba un símbolo del sistema que refactorice el método mediante LINQ.

    Por ejemplo, escriba el siguiente símbolo del sistema:

    ```plaintext
    #selection refactor selection using LINQ find an existing loan `_jsonData.Loans!. Replace existing loan.
    ```

1. Dedique un minuto a revisar la actualización sugerida.

    La actualización sugerida debe ser similar al código siguiente:

    ```csharp

    public async Task UpdateLoan(Loan loan)
    {
        Loan? existingLoan = _jsonData.Loans!.FirstOrDefault(l => l.Id == loan.Id);
        if (existingLoan != null)
        {
            existingLoan.BookItemId = loan.BookItemId;
            existingLoan.PatronId = loan.PatronId;
            existingLoan.LoanDate = loan.LoanDate;
            existingLoan.DueDate = loan.DueDate;
            existingLoan.ReturnDate = loan.ReturnDate;
            await _jsonData.SaveLoans(_jsonData.Loans!);
            await _jsonData.LoadData();
        }
    }

    ```

    El código actualizado usa LINQ para encontrar el préstamo existente en la colección de préstamos. A continuación, actualiza el préstamo existente con los nuevos datos del préstamo. A continuación, el método guarda la colección de préstamos actualizados y vuelve a cargar los datos. Este enfoque garantiza que los datos del préstamo se actualicen correctamente y que los cambios se conserven en el almacén de datos.

    También puede agregar el código para asegurarse de que los datos se cargan antes de ejecutar el método:

    ```csharp

    public async Task UpdateLoan(Loan loan)
    {
        await _jsonData.EnsureDataLoaded();
        Loan? existingLoan = _jsonData.Loans!.FirstOrDefault(l => l.Id == loan.Id);
        if (existingLoan != null)
        {
            existingLoan.BookItemId = loan.BookItemId;
            existingLoan.PatronId = loan.PatronId;
            existingLoan.LoanDate = loan.LoanDate;
            existingLoan.DueDate = loan.DueDate;
            existingLoan.ReturnDate = loan.ReturnDate;
            await _jsonData.SaveLoans(_jsonData.Loans!);
            await _jsonData.LoadData();
        }
    }

    ```

1. Para aceptar el método UpdateLoan actualizado, selecciona **Aceptar**.

1. Guarda los cambios en el archivo JsonLoanRepository.cs.

1. Compile la solución para asegurarse de que no hay errores.

    Verá advertencias. Puede ignorarlos por ahora.

#### Tarea 3: Refactorizar los métodos de JsonPatronRepository para usar LINQ

La clase JsonPatronRepository incluye los métodos SearchPatrons, GetPatron y UpdatePatron, y es una excelente candidata para la optimización. Refactorizará estos métodos y reemplazará los bucles foreach por LINQ para mejorar la legibilidad y el mantenimiento del código.

Completa los siguientes pasos para usar esta sección del ejercicio:

1. Abre el archivo **JsonPatronRepository.cs**.

1. Selecciona el método **SearchPatrons**.

    El método SearchPatrons está diseñado para buscar usuarios por nombre.

    ```csharp

    public async Task<List<Patron>> SearchPatrons(string searchInput)
    {
        await _jsonData.EnsureDataLoaded();
        List<Patron> searchResults = new List<Patron>();
        foreach (Patron patron in _jsonData.Patrons)
        {
            if (patron.Name.Contains(searchInput))
            {
                searchResults.Add(patron);
            }
        }
        searchResults.Sort((p1, p2) => String.Compare(p1.Name, p2.Name));
        searchResults = _jsonData.GetPopulatedPatrons(searchResults);
        return searchResults;
    }

    ```

1. Abra el chat en línea y escriba un símbolo del sistema que refactorice el método mediante LINQ.

    Por ejemplo, escriba el siguiente símbolo del sistema:

    ```plaintext
    #selection refactor selection using LINQ with `_jsonData.Patrons!. Replace the loop with `Where`, `OrderBy`, and `GetPopulatedPatrons`.
    ```

1. Dedique un minuto a revisar la actualización sugerida.

    La actualización sugerida debe ser similar al código siguiente:

    ```csharp

    public async Task<List<Patron>> SearchPatrons(string searchInput)
    {
        await _jsonData.EnsureDataLoaded();
        List<Patron> searchResults = _jsonData.Patrons!
            .Where(patron => patron.Name.Contains(searchInput))
            .OrderBy(patron => patron.Name)
            .ToList();
        searchResults = _jsonData.GetPopulatedPatrons(searchResults);
        return searchResults;
    }

    ```

1. Para aceptar el método SearchPatrons actualizado, selecciona **Aceptar**.

1. Selecciona el método **GetPatron**.

    El método GetPatron está diseñado para devolver el patrón que coincide con el "id" especificado.

    ```csharp

    public async Task<Patron?> GetPatron(int id)
    {
        await _jsonData.EnsureDataLoaded();
        foreach (Patron patron in _jsonData.Patrons!)
        {
            if (patron.Id == id)
            {
                Patron populated = _jsonData.GetPopulatedPatron(patron);
                return populated;
            }
        }
        return null;
    }

    ```

1. Abra el chat en línea y escriba un símbolo del sistema que refactorice el método mediante LINQ.

    Por ejemplo, escriba el siguiente símbolo del sistema:

    ```plaintext
    #selection refactor selection using LINQ with `_jsonData.Patrons!. Use `Where`, `Select` and `GetPopulatedPatron` to return `FirstOrDefault`
    ```

1. Dedique un minuto a revisar la actualización sugerida.

    La actualización sugerida debe ser similar al código siguiente:

    ```csharp

    public async Task<Patron?> GetPatron(int id)
    {
        await _jsonData.EnsureDataLoaded();
        var patron = _jsonData.Patrons!
            .Where(p => p.Id == id)
            .Select(p => _jsonData.GetPopulatedPatron(p))
            .FirstOrDefault();
        return patron;
    }

    ```

    Este código podría simplificarse aún más:

    ```C#

    public async Task<Patron?> GetPatron(int id)
    {
        await _jsonData.EnsureDataLoaded();
        return _jsonData.Patrons!
            .Where(p => p.Id == id)
            .Select(p => _jsonData.GetPopulatedPatron(p))
            .FirstOrDefault();
    }

    ```

1. Para aceptar el método GetPatron actualizado, selecciona **Aceptar**.

1. Selecciona el método **UpdatePatron**.

    El método UpdatePatron está diseñado para actualizar el patrón con el "id" especificado.

    ```csharp

    public async Task UpdatePatron(Patron patron)
    {
        await _jsonData.EnsureDataLoaded();
        var patrons = _jsonData.Patrons!;
        Patron existingPatron = null;
        foreach (var p in patrons)
        {
            if (p.Id == patron.Id)
            {
                existingPatron = p;
                break;
            }
        }
        if (existingPatron != null)
        {
            existingPatron.Name = patron.Name;
            existingPatron.ImageName = patron.ImageName;
            existingPatron.MembershipStart = patron.MembershipStart;
            existingPatron.MembershipEnd = patron.MembershipEnd;
            existingPatron.Loans = patron.Loans;
            await _jsonData.SavePatrons(patrons);
            await _jsonData.LoadData();
        }
    }

    ```

1. Abra el chat en línea y escriba un símbolo del sistema que refactorice el método mediante LINQ.

    Por ejemplo, escriba el siguiente símbolo del sistema:

    ```plaintext
    #selection refactor selection using LINQ to find `patron` in `_jsonData.Patrons!. Replace existing patron with `patron`.
    ```

1. Dedique un minuto a revisar la actualización sugerida.

    La actualización sugerida debe ser similar al código siguiente:

    ```csharp

    public async Task UpdatePatron(Patron patron)
    {
        await _jsonData.EnsureDataLoaded();
        var patrons = _jsonData.Patrons!;
        var existingPatron = patrons.FirstOrDefault(p => p.Id == patron.Id);
        if (existingPatron != null)
        {
            existingPatron.Name = patron.Name;
            existingPatron.ImageName = patron.ImageName;
            existingPatron.MembershipStart = patron.MembershipStart;
            existingPatron.MembershipEnd = patron.MembershipEnd;
            existingPatron.Loans = patron.Loans;
            await _jsonData.SavePatrons(patrons);
            await _jsonData.LoadData();
        }
    }

    ```

1. Para aceptar el método UpdatePatron actualizado, selecciona **Aceptar**.

#### Tarea 4: Compruebe su trabajo

Siga estos pasos para comprobar el trabajo:

1. Para limpiar la solución, haz clic con el botón derecho en **AccelerateAppDevGitHubCopilot** y después selecciona **Limpiar**.

    Esta acción quita los artefactos de compilación de la compilación anterior. La limpieza de la solución restablecerá eficazmente los archivos de datos JSON a sus valores originales durante (en el directorio de salida).

1. Compile la aplicación y asegúrese de que no hay errores.

1. Ejecute la aplicación.

    Para ejecutar la aplicación desde la vista Explorador de soluciones, haz clic con el botón derecho en el proyecto **Library.Console**, selecciona **Depurar** y después **Iniciar nueva instancia**.

1. Cuando se le solicite un nombre de patrón, escriba **One** y presione Entrar.

1. En el símbolo del sistema "Patrones coincidentes", escriba **2** y presione Entrar.

1. En el símbolo del sistema "Reservar préstamos", escriba **1** y presione Entrar.

1. En el símbolo del sistema "Opciones de entrada", escriba **r** y presione Entrar.

1. Comprueba el mensaje **"El libro se ha devuelto correctamente"**. .

1. Para iniciar una nueva búsqueda, escriba **s** y presione Entrar.

1. Cuando se le solicite un nombre de patrón, escriba **One** y presione Entrar.

1. En el símbolo del sistema "Patrones coincidentes", escriba **2** y presione Entrar.

1. Comprueba que el primer préstamo de libros está marcado como **Returned: True**.

1. En el símbolo del sistema "Opciones de entrada", escriba **q** y presione Entrar.

1. Detenga la aplicación.

#### Resumen: Ejercicio 9

En este ejercicio, refactorizarás los métodos de acceso a datos de las clases JsonData, JsonLoanRepository y JsonPatronRepository para usar LINQ. Estos cambios mejoran la legibilidad, el mantenimiento y el rendimiento del código.

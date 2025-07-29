---
demo:
  title: 'Demostración: Generación de documentación del proyecto mediante GitHub Copilot Chat'
  module: 'Module 2: Generate documentation using GitHub Copilot tools'
---

# Demostración: Generación de documentación del proyecto mediante GitHub Copilot Chat

## Instrucciones

Las actividades de demostración están diseñadas para un entorno que incluye los siguientes recursos:

- Visual Studio Code.
- Extensión del kit de desarrollo de C# para Visual Studio Code.
- Las extensiones de GitHub Copilot y GitHub Copilot Chat para Visual Studio Code. Se requiere una cuenta de GitHub con una suscripción activa para GitHub Copilot.
- Proyectos de código de ejemplo creados con C#.

**NOTA**: Se recomienda que los instructores consideren usar su propia cuenta de GitHub y la suscripción a GitHub Copilot para las demostraciones. Esto te permitirá controlar y personalizar el entorno de desarrollo. También harás que sea más fácil ajustar las demostraciones para adaptarlas a las necesidades de tus aulas.

**IMPORTANTE**: Si decides ejecutar las demostraciones en el entorno de laboratorio hospedado en lugar de en el equipo instructor, puedes descomprimir las aplicaciones de ejemplo en el entorno hospedado. Tendrás que configurar las extensiones de GitHub Copilot en el entorno hospedado para poder ejecutar las demostraciones. Es posible que el entorno hospedado sea más lento que el entorno local, por lo que es posible que tengas que ajustar el ritmo de las demostraciones según proceda.

### Presentación de la demostración

La creación de documentación es una parte importante del desarrollo de software. La documentación insertada ayuda a los desarrolladores a comprender el código base, su propósito y cómo usarlo. La documentación del proyecto proporciona a las partes interesadas información esencial para comprender el ámbito y el propósito del proyecto.

La documentación del proyecto suele incluir las secciones siguientes:

- **Información general del proyecto**: un resumen general del proyecto, su propósito y sus objetivos.
- **Requisitos de proyecto**: una lista de los requisitos del proyecto, incluidos los requisitos funcionales y no funcionales.
- **Restricciones del proyecto**: Cualquier restricción que afecte al proyecto, como el tiempo, el presupuesto o las restricciones técnicas.
- **Dependencias del proyecto**: una lista de las dependencias del proyecto, incluidas bibliotecas, marcos y otros componentes en los que se basa el proyecto.
- **Resumen del proyecto**: un breve resumen del proyecto, su propósito y sus objetivos.

En esta demostración, utilizarás GitHub Copilot Chat para generar la documentación del proyecto `APL2007M2Sample1`.

> [!IMPORTANT]
> Los instructores deben resaltar la importancia de revisar la documentación sugerida por GitHub Copilot. Los desarrolladores deben comprobar la precisión y la integridad. La documentación generada por GitHub Copilot es un punto de partida. Es posible que tenga que agregar, eliminar o modificar el contenido para satisfacer las necesidades específicas de su proyecto.

### Generación de la documentación del proyecto para el proyecto APL2007M2Sample1

La documentación del proyecto se puede generar en Visual Studio Code mediante la vista Chat y el participante `@workspace`. Puede incluir descripciones de lenguaje natural para generar secciones específicas de la documentación del proyecto, como la información general del proyecto, los requisitos, las restricciones, las dependencias y el resumen. También puede usar el Chat de GitHub Copilot para generar tipos específicos de archivos de documentación, como un archivo `readme.md`.

1. Asegúrese de que tiene abierto el proyecto `APL2007M2Sample1` en Visual Studio Code.

1. Para abrir la vista de chat, selecciona **Abrir chat**.

1. En la vista Chat, para generar documentación para el área de trabajo, escriba el símbolo del sistema siguiente:

    ```output
    @workspace document this project
    ```

1. Dedique un minuto a revisar la documentación del proyecto generada para el proyecto `APL2007M2Sample1`.

    Observe que la documentación del proyecto sugerido es similar a la explicación del proyecto generada en la unidad anterior.

    Al anexar avisos como "documentar las restricciones del proyecto" o "documentar las dependencias del proyecto", puede obtener información detallada sobre el proyecto.

1. En la vista Chat, para generar documentación que describa las dependencias del proyecto, escriba el símbolo del sistema siguiente:

    ```output
    @workspace document the project dependencies
    ```

1. Dedique un minuto a revisar la documentación de dependencias del proyecto.

    La respuesta generada por el chat de Copilot debe ser similar a la siguiente información:

    El chat de GitHub Copilot puede ayudarle a documentar cualquier aspecto de los proyectos. Puede usar la vista Chat para generar documentación para archivos, clases o funciones específicos dentro del proyecto. El tamaño y la complejidad del proyecto ayudan a determinar el nivel de detalle necesario.

    Si el tiempo lo permite, use la vista Chat para generar documentación para las siguientes secciones del proyecto:

    - Requisitos de proyecto
    - Restricciones del proyecto
    - Arquitectura de proyecto
    - Diseño del proyecto
    - Pruebas del proyecto
    - Implementación del proyecto
    - Resumen del proyecto

    Puede adaptar la documentación del proyecto generada por el Chat de Copilot a las necesidades específicas del proyecto y sus partes interesadas.

1. En la vista Chat, para generar un archivo LÉAME para el proyecto `APL2007M2Sample1`, escriba el símbolo del sistema siguiente:

    ```output
    @workspace generate a readme document that can be used as a repo description
    ```

1. Dedique un minuto a revisar el archivo LÉAME generado para el `APL2007M2Sample1` proyecto.

    El contenido del archivo LÉAME generado por el Chat de Copilot proporciona información general de alto nivel del proyecto con varias secciones que a menudo se incluyen en este tipo de archivo.

    Puedes adaptar la indicación para especificar secciones LÉAME específicas. También puede escribir mensajes individuales para generar secciones específicas de un documento LÉAME.

    > [!NOTE]
    > Si desea que el documento LÉAME tenga formato de archivo Markdown, puede escribir un símbolo del sistema similar al siguiente: `generate readme project documentation formatted using a raw markdown format`. Si GitHub Copilot está configurado para trabajar con archivos Markdown, puedes usar la característica de chat insertado para dar formato al documento LÉAME como un archivo Markdown.

### Resumen

En esta demostración, has usado GitHub Copilot Chat para generar la documentación del proyecto `APL2007M2Sample1`. Con la vista Chat y el participante `@workspace`, ha podido generar documentación para la información general del proyecto, los requisitos, las restricciones, las dependencias y el resumen. También ha generado un archivo LÉAME para el proyecto `APL2007M2Sample1`. Al usar Copilot Chat para generar documentación del proyecto, puede crear una introducción general de alto nivel que ayude a otros desarrolladores a comprender el proyecto y sus objetivos. Recuerde revisar la documentación generada por Copilot Chat para asegurarse de que es precisa y está completa.

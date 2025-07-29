---
demo:
  title: 'Demostración: Conversión de código de un lenguaje de programación a otro'
  module: 'Module 3: Develop code features using GitHub Copilot tools'
---

# Demostración: Conversión de código de un lenguaje de programación a otro

## Instrucciones

Las actividades de demostración están diseñadas para un entorno que incluye los siguientes recursos:

- Visual Studio Code.
- Extensión del kit de desarrollo de C# para Visual Studio Code.
- Las extensiones de GitHub Copilot y GitHub Copilot Chat para Visual Studio Code. Se requiere una cuenta de GitHub con una suscripción activa para GitHub Copilot.
- Proyectos de código de ejemplo creados con C#.

**NOTA**: Se recomienda que los instructores consideren usar su propia cuenta de GitHub y la suscripción a GitHub Copilot para las demostraciones. Esto te permitirá controlar y personalizar el entorno de desarrollo. También harás que sea más fácil ajustar las demostraciones para adaptarlas a las necesidades de tus aulas.

**IMPORTANTE**: Si decides ejecutar las demostraciones en el entorno de laboratorio hospedado en lugar de en el equipo instructor, puedes descomprimir las aplicaciones de ejemplo en el entorno hospedado. Tendrás que configurar las extensiones de GitHub Copilot en el entorno hospedado para poder ejecutar las demostraciones. Es posible que el entorno hospedado sea más lento que el entorno local, por lo que es posible que tengas que ajustar el ritmo de las demostraciones según proceda.

### Presentación de la demostración

GitHub Copilot puede ayudarte a convertir código de un lenguaje de programación a otro. Por ejemplo, puedes pedir a GitHub Copilot que convierta una función o un fragmento de código en otro lenguaje de programación.

Puede completar los siguientes tipos de conversiones de código mediante GitHub Copilot:

- Convierta un archivo de código completo en otro lenguaje de programación.
- Convierta una función en otro lenguaje de programación.
- Convierta un fragmento de código en otro lenguaje de programación.

Cada una de las interfaces de chat (vista chat, ventana chat rápido y chat en línea) se puede usar para convertir código entre lenguajes de programación. La elección de la interfaz de chat depende de tus preferencias y de la complejidad del código que deseas convertir.

Supongamos que acaba de empezar a trabajar en el proyecto de `QuarterlyIncomeReport`. Analizará los objetivos del proyecto con un compañero. Mencionan que tienen un archivo de Python que podría proporcionar algunas de las características que está buscando. Apuntan al repositorio para el código de Python. Decide abrir el proyecto de código de Python en Visual Studio Code y usar la vista Chat para convertir el código de Python en C#.

## Conversión de código entre lenguajes de programación mediante la vista Chat

1. Abre la carpeta del proyecto **APL2007M3Python** en Visual Studio Code.

    Este proyecto contiene una versión de Python del proyecto `QuarterlyIncomeReport` en el que ha trabajado durante este módulo. Puede hacer que GitHub Copilot le explique el código mediante la vista Chat o Explicar esta acción inteligente.

1. Ejecute la aplicación de Python.

    Tenga en cuenta que la salida de la aplicación de Python es básicamente la misma que la salida de la aplicación de C# que creó anteriormente.

1. Abra el archivo `main.py` Python.

    El archivo de Python contiene una función que genera datos de ventas. Quiere convertir este código de Python en C#.

1. Seleccione todo el contenido del archivo.

1. Abra la vista Chat y escriba el siguiente símbolo del sistema:

    ```plaintext
    Convert #selection to C#
    ```

1. Dedique un momento a revisar la respuesta de GitHub Copilot.

    La respuesta debe contener la versión de C# del código de Python seleccionado.

1. Abra una segunda instancia de Visual Studio Code.

1. Abra la vista Chat y escriba el siguiente símbolo del sistema:

    ```plaintext
    @workspace /new console application in C# NET8 named APL2007M3B. Only .cs and .csproj files. Enable ImplicitUsings and Nullable
    ```

    Si Copilot responde con un mensaje de error sobre el "argumento path", vuelva a intentar la misma solicitud.

1. Seleccione **Crear área de trabajo**

1. En el cuadro de diálogo Abrir carpeta, seleccione la carpeta **Escritorio** y, a continuación, seleccione **Seleccionar como carpeta principal**.

    espere a que se cree el área de trabajo.

1. Cuando se cree el área de trabajo, seleccione **Program.cs**, y elimine el contenido del archivo.

1. Cambie a la instancia de Visual Studio Code que contiene el código de Python.

1. Desplácese hasta la parte superior de la vista Chat y haga clic en el botón **Copiar ** para copiar el código de C# generado en el Portapapeles.

1. Cambie a la instancia de Visual Studio Code que contiene el código de C#.

1. Pegue el código de C# en el archivo Program.cs.

1. Guarde el archivo Program.cs.

1. Ejecute la aplicación de C#.

    Observe que la salida de la aplicación de C# es básicamente la misma que la salida de la aplicación Python.

    Si tiene tiempo, dedique unos minutos a revisar las diferencias entre el código de C# convertido y el código de C# de la unidad anterior.

## Conversión de código entre lenguajes de programación mediante el chat en línea

1. Vuelva a la instancia de Visual Studio Code que contiene el proyecto de Python que abrió anteriormente.

1. Seleccione el código en el archivo main.py.

1. Abra el chat en línea y escriba el siguiente símbolo del sistema:

    ```plaintext
    Convert #selection to C#
    ```

1. Revise la respuesta de GitHub Copilot y seleccione **Aceptar**.

    El archivo de Python ahora debe contener código de C#.

1. Copie el código de C# generado en el Portapapeles.

1. Cierre el archivo main.py sin guardar los cambios.

1. Cambie a la instancia de Visual Studio Code que contiene el proyecto de C# y abra el archivo Program.cs.

1. Para sobrescribir el código de C# existente, pegue el código de C# del Portapapeles (convertido desde Python mediante chat en línea) sobre el contenido del archivo Program.cs.

1. Guarde el archivo Program.cs.

1. Ejecute la aplicación de C#.

    Observe que la salida de la aplicación de C# es básicamente la misma que la salida de la aplicación Python.

Cuando use GitHub Copilot para convertir código entre lenguajes de programación, intente usar la vista Chat y el chat en línea. Aunque ambas herramientas comparten el mismo modelo de IA, sus resultados pueden diferir. Probar ambas herramientas puede ayudarle a determinar qué herramienta es mejor para su caso de uso específico.

> [!NOTE]
> Los lenguajes de programación suelen tener un "estilo de programación" asociado y algunos lenguajes pueden tener características únicas o bibliotecas de código. Al convertir grandes secciones de código de un lenguaje de programación a otro, es importante comprender completamente el lenguaje de programación de destino y la intensión del código. Las sugerencias de GitHub Copilot siempre deben revisarse antes de aceptarlas.

### Resumen

En esta demostración, has usado GitHub Copilot para convertir código de Python a C#. Has utilizado la vista Chat y el chat insertado para convertir el código de Python a C#. A continuación, has ejecutado la aplicación de C# para comprobar que la salida era la misma que la de la aplicación de Python. Mediante el uso de GitHub Copilot para convertir código entre lenguajes de programación, puedes adaptar rápidamente el código de un lenguaje a otro. Recuerda revisar el código convertido para asegurarte de que cumple tus requisitos y que sigue el estilo de programación del lenguaje de destino.

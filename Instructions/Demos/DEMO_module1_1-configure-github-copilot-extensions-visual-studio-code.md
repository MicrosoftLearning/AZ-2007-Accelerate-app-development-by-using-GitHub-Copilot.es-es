---
demo:
  title: "Demostración: Configuración de las extensiones de GitHub Copilot para Visual\_Studio Code"
  module: 'Module 1: Get started with GitHub Copilot'
---

# Demostración: Configuración de las extensiones de GitHub Copilot para Visual Studio Code

## Instrucciones

Las actividades de demostración están diseñadas para un entorno que incluye los siguientes recursos:

- Visual Studio Code.
- Extensión del kit de desarrollo de C# para Visual Studio Code.
- Las extensiones de GitHub Copilot y GitHub Copilot Chat para Visual Studio Code. Se requiere una cuenta de GitHub con una suscripción activa para GitHub Copilot.
- Proyectos de código de ejemplo creados con C#.

**NOTA**: Se recomienda que los instructores consideren usar su propia cuenta de GitHub y la suscripción a GitHub Copilot para las demostraciones. Esto te permitirá controlar y personalizar el entorno de desarrollo. También harás que sea más fácil ajustar las demostraciones para adaptarlas a las necesidades de tus aulas.

**IMPORTANTE**: Si decides ejecutar las demostraciones en el entorno de laboratorio hospedado en lugar de en el equipo instructor, puedes descomprimir las aplicaciones de ejemplo en el entorno hospedado. Tendrás que configurar las extensiones de GitHub Copilot en el entorno hospedado para poder ejecutar las demostraciones. Es posible que el entorno hospedado sea más lento que el entorno local, por lo que es posible que tengas que ajustar el ritmo de las demostraciones según proceda.

### Presentación de la demostración

La configuración de GitHub Copilot se configura en la cuenta de GitHub.com y en el entorno de Visual Studio Code. En Visual Studio Code, puede acceder a la configuración de GitHub Copilot y GitHub Copilot Chat usando el menú de estado de GitHub Copilot.

La configuración de Visual Studio Code te permite habilitar o deshabilitar GitHub Copilot para idiomas específicos, configurar el comportamiento del chat de GitHub Copilot y personalizar la experiencia de GitHub Copilot para adaptarla a tus preferencias. También puede configurar la configuración de GitHub Copilot en GitHub.com para administrar su suscripción a GitHub Copilot, configurar la retención de avisos y sugerencias, y permitir o bloquear sugerencias que coincidan con código público.

## Habilitar o deshabilitar GitHub Copilot

GitHub Copilot está habilitado de forma predeterminada al instalar la extensión en Visual Studio Code. Puede deshabilitar GitHub Copilot durante un período de tiempo si es necesario.

Para mostrar las opciones de habilitar y deshabilitar la extensión GitHub Copilot, sigue estos pasos:

1. En Visual Studio Code, abra la vista **Extensiones**.

1. En la lista de extensiones instaladas, desplácese hacia abajo hasta que encuentre **GitHub Copilot**.

1. Para mostrar un menú desplegable para la extensión GitHub Copilot que enumere las opciones Habilitar y Deshabilitar, seleccione el icono de engranaje situado junto a GitHub Copilot.

Si deseas demostrar las opciones de habilitación o deshabilitación, puedes seleccionar la opción de deshabilitar. Sin embargo, asegúrate de volver a habilitar GitHub Copilot antes de continuar con esta demostración.

## Configurar GitHub Copilot y el chat de Copilot en Visual Studio Code

Las extensiones de GitHub Copilot se configuran con los ajustes predeterminados al instalar las extensiones en Visual Studio Code. Puede personalizar esta configuración para adaptarse a sus preferencias.

Visual Studio Code proporciona dos maneras de acceder a la configuración de las extensiones de GitHub Copilot:

- Puedes usar el icono `Manage` para abrir la pestaña Configuración de Visual Studio Code. En la pestaña Configuración, puedes seleccionar **Extensiones** y, a continuación, seleccionar **Copilot**.
- Puede usar el icono de estado de GitHub Copilot para acceder al menú estado de GitHub Copilot y luego seleccionar **Editar configuración**.

Muestra cómo usar el menú de estado de GitHub Copilot para acceder a la configuración. Se abrirá la pestaña Configuración de Visual Studio Code con la configuración filtrada para GitHub Copilot. El menú de estado es la forma más rápida de acceder a la configuración de las extensiones de GitHub Copilot.

### Configurar los ajustes de GitHub Copilot

Para mostrar los valores de configuración de GitHub Copilot, sigue estos pasos:

1. En el panel inferior de la ventana Visual Studio Code, para abrir el menú de estado de GitHub Copilot, selecciona el icono de estado de GitHub Copilot.

    El icono de estado de GitHub Copilot indica si GitHub Copilot está habilitado o deshabilitado. Cuando está habilitado, el color de fondo del icono coincide con el color de la barra de estado. Cuando está deshabilitado, el color de fondo del icono contrasta con el color de la barra de estado.

1. En el menú estado de GitHub Copilot, seleccione **Editar configuración**.

1. Dedique un minuto a revisar la lista de opciones de configuración disponibles.

    Observe que se muestran los valores de GitHub Copilot y el chat de GitHub Copilot. Además, en la etiqueta Extensiones de la izquierda, ambas extensiones están etiquetadas como Copilot. La primera extensión de Copilot es para GitHub Copilot y la segunda es para el chat de GitHub Copilot.

1. En la etiqueta Extensiones, seleccione la primera extensión de Copilot.

    Tenga en cuenta que la lista de configuración ahora está filtrada solo para GitHub Copilot.

    La configuración de GitHub Copilot incluye las siguientes opciones:

    - Habilitar finalizaciones automáticas
    - Habilitar o deshabilitar finalizaciones de Copilot para idiomas especificados

1. Tómese un minuto para revisar la configuración de **Habilitar o deshabilitar las terminaciones de Copilot para los idiomas especificados**.

    Observe que los ajustes para esta opción se configuran usando una lista de idiomas y un valor de **verdadero** o **falso** para habilitar o deshabilitar GitHub Copilot para cada idioma. De forma predeterminada, GitHub Copilot está habilitado para todos los idiomas. Esta configuración se especifica con el carácter comodín `*` en la primera fila y el valor **verdadero**. Las filas posteriores especifican los idiomas para los que GitHub Copilot está habilitado o deshabilitado. Por ejemplo, GitHub Copilot está habilitado para **C#**, **JavaScript** y **Python** y deshabilitado para **Plaintext** y **Markdown**.

1. En **Habilitar o deshabilitar finalizaciones de Copilot para idiomas especificados**, seleccione **Markdown**.

    Observe que el valor de Markdown está establecido en **falso**. Esto significa que GitHub Copilot está deshabilitado para los archivos Markdown.

1. Para habilitar Copilot para archivos Markdown, seleccione **Editar elemento** (icono de lápiz), seleccione **falso**, cambie el valor a **verdadero** y luego seleccione **Aceptar**.

    Ahora puede usar proyectos de documentos de GitHub Copilot mediante archivos Markdown.

1. En la etiqueta Extensiones, seleccione la segunda extensión de Copilot.

    Tenga en cuenta que la lista de configuración ahora está filtrada solo para Chat de GitHub Copilot.

    La configuración del chat de GitHub Copilot incluye las opciones **Vista previa** y **Experimental**. Entre las opciones de configuración se incluyen las siguientes:

    - **Corrección de errores de prueba**: Esta opción está habilitada de manera predeterminada de modo que GitHub Copilot pueda proporcionar sugerencias para corregir errores de prueba.
    - **Seguimientos**: De manera predeterminada, esta configuración se establece en **firstOnly**, lo que significa que GitHub Copilot proporcionará sugerencias de seguimiento solo después de la primera sugerencia. Las otras opciones son **siempre** y **nunca**.
    - **Reemplazo local**: De manera predeterminada, esta opción se establece en **automático**, lo que significa que GitHub Copilot usa la configuración regional de idioma para mostrar de Visual Studio Code.
    - **Selección del ámbito**: Esta opción está deshabilitada de manera predeterminada. Cuando está habilitado, se solicita al usuario un símbolo de ámbito cuando el usuario usa `/explain` en Chat sin nada seleccionado en el Editor.
    - **Ubicación de chat del terminal**: La configuración predeterminada es chatView, que especifica la vista de chat. Las otras opciones son para el área Chat rápido y el terminal.
    - **Usar plantillas de proyecto**: Esta opción está habilitada de forma predeterminada para que GitHub Copilot use las plantillas de proyecto de GitHub pertinentes cuando el usuario usa `/new` en Chat.
    - **Habilitar acciones de código**: Esta opción está habilitada de forma predeterminada para que GitHub Copilot pueda proporcionar acciones de código en el Editor.
    - **Desencadenar automáticamente**: Esta opción está habilitada de manera predeterminada para que las sugerencias de GitHub Copilot se muestren automáticamente a medida que escribe.

    Se recomienda mantener la configuración predeterminada durante este entrenamiento. Esto ayuda a garantizar que tenga la experiencia esperada cuando trabaje en los módulos de esta ruta de aprendizaje. Cuando haya completado el entrenamiento, puede experimentar con esta configuración para personalizar su experiencia con GitHub Copilot y Copilot Chat.

## Configuración de las opciones de GitHub Copilot en GitHub.com

La configuración de la cuenta de GitHub en GitHub.com incluir opciones para configurar GitHub Copilot. Esta configuración se usa para administrar su suscripción a GitHub Copilot, configurar la retención de avisos y sugerencias, y permitir o bloquear sugerencias que coincidan con código público.

GitHub Copilot se puede administrar a través de cuentas personales con GitHub Copilot Individual o a través de cuentas de organización con GitHub Copilot Business/Enterprise.

## Métodos abreviados de teclado para GitHub Copilot

Puede usar los métodos abreviados de teclado predeterminados en Visual Studio Code al usar GitHub Copilot. Como alternativa, puedes volver a enlazar los accesos directos en el editor Métodos abreviados de teclado y usar tus preferidos para cada comando específico.

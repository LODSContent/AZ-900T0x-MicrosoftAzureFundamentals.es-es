---
wts:
  title: "8: Implementar Azure\_Functions (5\_minutos)"
  module: 'Module 03: Describe core solutions and management tools'
---
# <a name="08---implement-azure-functions-5-min"></a>8: Implementar Azure Functions (5 minutos)

En este tutorial, crearemos una aplicación de funciones para mostrar un mensaje de saludo cuando haya una solicitud HTTP. 

# <a name="task-1-create-a-function-app"></a>Tarea 1: Crear una aplicación de funciones 

En esta tarea, crearemos un aplicación de funciones.

1. Inicie sesión en [Azure Portal](https://portal.azure.com).

2. En la barra de **Búsqueda** de la parte superior del portal, busque y seleccione **Aplicación de funciones** y luego, en la hoja **Aplicación de funciones**, haga clic en **+ Agregar, + Crear, o + Nuevo**.

3. En la pestaña **Datos básicos** de la hoja **Aplicación de funciones**, especifique la siguiente configuración (reemplace **xxxx** en el nombre de la función por letras y dígitos, de modo que el nombre sea único a nivel global, y deje todas las demás configuraciones con sus valores predeterminados): 

    | Configuración | Value |
    | -- | --|
    | Subscription | **Mantener los valores predeterminados** |
    | Grupo de recursos | **Crear un grupo de recursos** |
    | Nombre de la aplicación de funciones | **función-xxxx** |
    | Publicar | **Código** |
    | Pila en tiempo de ejecución | **.NET** |
    | Versión | **3.1** |
    | Region | **Este de EE. UU.** |

    **Nota**: Recuerde cambiar **xxxx** de modo que sea un **nombre de la aplicación de funciones** único.

4. Haga clic en **Revisar y crear** y, después de una correcta validación, haga clic en **Crear** para empezar a aprovisionar e implementar su nueva aplicación de funciones de Azure.

5. Espere la notificación de que el recurso ha sido creado.

6. Cuando la implementación se haya completado, haga clic en Ir al recurso desde la hoja de implementación. Como alternativa, vuelva a la hoja **Aplicación de funciones**, haga clic en **Actualizar** y compruebe que la aplicación de funciones recién creada muestra el estado **En ejecución**. 

    ![Captura de pantalla de la página Aplicación de funciones con la nueva aplicación de funciones.](../images/0701.png)

# <a name="task-2-create-a-http-triggered-function-and-test"></a>Tarea 2: Crear una función activada por HTTP y probar

En esta tarea, usaremos la función API de Webhook para mostrar un mensaje cuando haya una solicitud HTTP. 

1. Sobre la hoja **Aplicación de funciones**, haga clic en la aplicación de funciones recién creada. 

2. En la hoja Aplicación de funciones, en la sección **Funciones**, haga clic en **Funciones** y luego en **+ Agregar, + Crear, o +Nuevo**.

    ![Captura de pantalla del paso elegir un entorno de desarrollo en Azure Functions para el panel Introducción .NET dentro de Azure Portal. Se resaltan los elementos de visualización para crear una nueva función en el portal. Los elementos resaltados son expandir la aplicación de funciones, agregar nuevas funciones, en el portal y el botón continuar.](../images/0702.png)

3. A la derecha aparecerá la ventana emergente **Agregar función**. En la sección **Seleccionar una plantilla**, haga clic en **Desencadenador de HTTP**. Haga clic en **Agregar**. 

    ![Captura de pantalla del paso Crear una función en Azure Functions para el panel Introducción .NET dentro de Azure Portal. La tarjeta de desencadenador HTTP se resalta para ilustrar los elementos de visualización utilizados para agregar un nuevo webhook a una función de Azure.](../images/0702a.png)

4. En la hoja **DesencadenadorHttp1**, en la sección **Desarrollador**, haga clic en **Código y prueba**. 

5. En la hoja **Código y prueba**, revise el código generado automáticamente y tenga en cuenta que está diseñado para ejecutar una solicitud HTTP y registrar información. Además, observe que la función devuelve un mensaje de saludo con un nombre. 

    ![Captura de pantalla del código de función. El mensaje de saludo está resaltado.](../images/0704.png)

6. Haga clic en **Obtener URL de función** desde la sección superior del editor de funciones. 

7. Asegúrese de que el valor en la lista desplegable **Clave** se establece en **predeterminado** y haga clic en **Copiar** para copiar la función URL. 

    ![Captura de pantalla del panel URL de obtención de funciones dentro del editor de funciones en Azure Portal. Los elementos de visualización obtienen el botón URL de la función, establecen el menú desplegable de teclas y el botón Copiar URL se resaltan para indicar cómo obtener y copiar la URL de la función desde el editor de funciones.](../images/0705.png)

8. Abra una nueva pestaña del explorador y pegue la URL de la función copiada en la barra de direcciones del explorador web. Cuando se solicite la página, la función se ejecutará. Observe el mensaje devuelto que indica que la función requiere un nombre en el cuerpo de la solicitud.

    ![Captura de pantalla del mensaje para proporcionar un nombre.](../images/0706.png)

9. Agregue **&name=*sunombre*** al final de la URL.

    **Nota**: Por ejemplo, si su nombre es Cindy, la URL final tendrá este aspecto: `https://azfuncxxx.azurewebsites.net/api/HttpTrigger1?code=X9xx9999xXXXXX9x9xxxXX==&name=cindy`

    ![Captura de pantalla de una URL de función resaltada y un nombre de usuario de ejemplo anexado en la barra de direcciones de un explorador web. El mensaje de saludo y el nombre de usuario también se resaltan para ilustrar el resultado de la función en la ventana principal del explorador.](../images/0707.png)

10. Cuando pulse Intro, la función se ejecutará y se realizará un seguimiento de todas las invocaciones. Para ver los seguimientos, vuelva al panel **HttpTrigger1 \| Código y prueba**  del portal y haga clic en **Supervisar**. Para **configurar** Application Insights, seleccione la marca de tiempo y haga clic en **Ejecutar consulta en Application Insights**.

    ![Captura de pantalla de un registro de información de seguimiento resultante de ejecutar la función dentro del editor de funciones en Azure Portal.](../images/0709.png) 

¡Enhorabuena! Ha creado una aplicación de funciones para mostrar un mensaje de saludo cuando hay una solicitud HTTP.  

**Nota**: Para evitar costes adicionales, opcionalmente, puede quitar este grupo de recursos. Busque grupos de recursos, haga clic en su grupo de recursos y, luego, haga clic en **Eliminar grupo de recursos**. Compruebe el nombre del grupo de recursos y luego haga clic en **Eliminar**. Supervise las **Notificaciones** para ver cómo se realiza la eliminación.

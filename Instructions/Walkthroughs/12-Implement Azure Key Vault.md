---
wts:
  title: "12: Implementar Azure\_Key\_Vault (5\_minutos)"
  module: 'Module 04: Describe general security and network security features'
---
# <a name="12---implement-azure-key-vault-5-min"></a>12: Implementar Azure Key Vault (5 minutos)

En este tutorial, crearemos una instancia de Azure Key Vault y luego crearemos un secreto de contraseña en el almacén de claves, lo que le dará una contraseña almacenada de forma segura y administrada de manera centralizada para su uso con aplicaciones.

# <a name="task-1-create-an-azure-key-vault"></a>Tarea 1: Crear una instancia de Azure Key Vault 

1. Inicie sesión en [Azure Portal](https://portal.azure.com).

2. Desde la hoja **Todos los servicios**, busque y seleccione **Almacenes de claves** y, luego, seleccione **+Agregar, +Nuevo o +Crear **.

3. Configure the key vault (replace <bpt id="p1">**</bpt>xxxx<ept id="p1">**</ept> in the name of the key vault with letters and digits such that the name is globally unique). Leave the defaults for everything else.

    | Configuración | Valor | 
    | --- | --- |
    | Subscription | **Usar los valores predeterminados** |
    | Grupo de recursos | **Crear un grupo de recursos** |
    | Nombre del almacén de claves | **keyvaulttestxxx** |
    | Location | **Este de EE. UU.** |
    | Plan de tarifa | **Estándar** |
    
    **Nota**: Reemplace **xxxx** para idear un nombre único.
4. Haga clic en **Revisar y crear** y después en **Crear**. 

5. Once the new key vault is provisioned, click <bpt id="p1">**</bpt>Go to resource<ept id="p1">**</ept>. Or you can locate your new key vault by searching for it. 

6. Click on the key vault <bpt id="p1">**</bpt>Overview<ept id="p1">**</ept> tab and take note of the <bpt id="p2">**</bpt>Vault URI<ept id="p2">**</ept>. Applications that use your vault through the REST APIs will need this URI.

7. Take a moment to browse through some of the other key vault options. Under <bpt id="p1">**</bpt>Settings<ept id="p1">**</ept> review <bpt id="p2">**</bpt>Keys<ept id="p2">**</ept>, <bpt id="p3">**</bpt>Secrets<ept id="p3">**</ept>, <bpt id="p4">**</bpt>Certificates<ept id="p4">**</ept>, <bpt id="p5">**</bpt>Access Policies<ept id="p5">**</ept>, <bpt id="p6">**</bpt>Firewalls and virtual networks<ept id="p6">**</ept>.

    <bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: Your Azure account is the only one authorized to perform operations on this new vault. You can modify this if you wish in the <bpt id="p1">**</bpt>Settings<ept id="p1">**</ept> and then the <bpt id="p2">**</bpt>Access policies<ept id="p2">**</ept> section.

# <a name="task-2-add-a-secret-to-the-key-vault"></a>Tarea 2: Agregar un secreto al almacén de claves
        
En esta tarea agregaremos una contraseña al almacén de claves. 

1. En **Configuración**, haga clic en **Secretos**, luego haga clic **+ Generar/Importar**.

2. Configure the secret. Leave the other values at their defaults. Notice you can set an activation and expiration date. Notice you can also disable the secret.

    | Configuración | Value | 
    | --- | --- |
    | Opciones de carga | **Manual** |
    | Nombre | **Contraseña de ejemplo** |
    | Value | **hVFkk96** |

3. Haga clic en **Crear**.

4. Una vez que el secreto se haya creado con éxito, haga clic en el **Contraseña de ejemplo** y tenga en cuenta que tiene el estado de **Habilitado**

5. Select the secret you just created, note the the <bpt id="p1">**</bpt>Secret Identifier<ept id="p1">**</ept>. This is the url value that you can now use with applications. It provides a centrally managed and securely stored password. 

6. Haga clic en el botón **Mostrar valor secreto**, para mostrar la contraseña que especificó anteriormente.


Configure el almacén de claves (reemplace **xxxx** en el nombre del almacén de claves con letras y dígitos de manera que el nombre sea único a nivel global).

Deje los valores predeterminados para todo lo demás.

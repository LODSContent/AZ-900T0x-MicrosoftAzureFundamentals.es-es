---
wts:
  title: "4: Crear una red virtual (20\_minutos)"
  module: Module 02 - Core Azure Services (Workloads)
---
# <a name="04---create-a-virtual-network-20-min"></a>4: Crear una red virtual (20 minutos)

En este tutorial crearemos una red virtual, implementaremos dos máquinas virtuales en esa red virtual y luego las configuraremos para permitir que una máquina virtual haga ping a la otra dentro de la red.

# <a name="task-1-create-a-virtual-network"></a>Tarea 1: Creación de una red virtual 

En esta tarea, crearemos una red virtual. 

Nota: Antes de comenzar el laboratorio, deshabilite el firewall público y privado en la máquina virtual; para ello, abra menú Inicio > Configuración > Network and Internet > Locate Windows Firewall (Menú Inicio > Configuración > Network e Internet > Locate Windows Firewall).

1. Inicie sesión en Azure Portal en <a href="https://portal.azure.com" target="_blank"><span style="color: #0066cc;" color="#0066cc">https://portal.azure.com</span></a>

2. Desde la hoja **Todos los servicios**, busque y seleccione **Redes virtuales** y haga clic en **+ Agregar, + Crear, o + Nuevo**. 

3. En la pestaña **Datos básicos**, complete la siguiente información (deje los valores predeterminados para todo lo demás):

    | Configuración | Value | 
    | --- | --- |
    | Subscription | **Deje los valores predeterminados** |
    | Grupo de recursos | **Crear un grupo de recursos** |
    | Nombre | **vnet1** |
    | Region | **(EE. UU.) Este de EE. UU.** |
    
   
4. Click the <bpt id="p1">**</bpt>Review + create<ept id="p1">**</ept> button. Ensure the validation passes. Then hit create to deploy the resource.


# <a name="task-2-create-two-virtual-machines"></a>Tarea 2: Creación de dos máquinas virtuales

En esta tarea crearemos dos máquinas virtuales en la red virtual. 

1. Desde la hoja **Todos los servicios** busque **Máquinas virtuales** y luego haga clic en **+ Agregar, +Crear, o +Nuevo** y seleccione **Máquina virtual** en el menú desplegable. 

2. En la pestaña **Datos básicos**, complete la siguiente información (deje los valores predeterminados para todo lo demás):

   | Configuración | Valor | 
   | --- | --- |
   | Subscription | **Usar los valores predeterminados** |
   | Grupo de recursos |  **Seleccionar el predeterminado en el menú desplegable** |
   | Nombre de la máquina virtual | **vm1**|
   | Region | **(EE. UU.) Este de EE. UU.** |
   | Imagen | **Windows Server 2019 Datacenter - Gen2** |
   | Nombre de usuario| **azureuser** |
   | Contraseña| **Pa$$w0rd1234** |
   | Puertos de entrada públicos| Seleccione **Allow selected ports** (Permitir puertos seleccionados).  |
   | Puertos de entrada seleccionados| **RDP (3389)** |
   

3. Select the <bpt id="p1">**</bpt>Networking<ept id="p1">**</ept> tab. Make sure the virtual machine is placed in the <bpt id="p2">**</bpt>vnet1<ept id="p2">**</ept> virtual network. Review the default settings, but do not make any other changes. 

4. Click <bpt id="p1">**</bpt>Review + create<ept id="p1">**</ept>. After the Validation passes, click <bpt id="p1">**</bpt>Create<ept id="p1">**</ept>. Deployment times can vary but it can generally take between three to six minutes to deploy.

5. Supervise su implementación, pero continúe con el siguiente paso. 

6. Create a second virtual machine by repeating steps <bpt id="p1">**</bpt>2 to 4<ept id="p1">**</ept> above. Make sure you use a different virtual machine name, that the virtual machine is in the same virtual network, and is using a new public IP address:

    | Configuración | Value |
    | --- | --- |
    | Grupo de recursos | **seleccione valor predeterminado en el menú desplegable (igual que la tarea 1-3 y la tarea 2-2)** |
    | Nombre de la máquina virtual |  **vm2** |
    | Virtual network | **vnet1** |
    | Dirección IP pública | **vm2-ip** |

7. Espere a que las dos máquinas virtuales se implementen y muestren el estado *En ejecución*.

# <a name="task-3-test-the-connection"></a>Tarea 3: Probar la conexión 

In this task, we will try to test whether the virtual machines can communicate (ping) each other. If not we will install a rule to allow an ICMP connection. Usually ICMP connections are automatically blocked.

1. From the <bpt id="p1">**</bpt>All resources<ept id="p1">**</ept> blade, search for <bpt id="p2">**</bpt>vm1<ept id="p2">**</ept>, open its <bpt id="p3">**</bpt>Overview<ept id="p3">**</ept> blade, and make sure its <bpt id="p4">**</bpt>Status<ept id="p4">**</ept> is <bpt id="p5">**</bpt>Running<ept id="p5">**</ept>. You may need to <bpt id="p1">**</bpt>Refresh<ept id="p1">**</ept> the page.

2. En la hoja **Información general**, seleccione **Conectar** y después seleccione **RDP** en el menú desplegable.

    **Nota**: Las siguientes instrucciones le indican cómo conectarse a su VM desde un equipo con Windows. 

3. En la hoja **Conectar mediante RDP**, mantenga las opciones predeterminadas para conectarse por dirección IP a través del puerto 3389 y haga clic en **Descargar archivo RDP**.

4. Abra el archivo RDP descargado (ubicado en la parte inferior izquierda de la máquina virtual) y haga clic en **Conectar** cuando se le pida. 

5. En la ventana **Seguridad de Windows**, escriba el nombre de usuario **azureuser** y la contraseña **Pa$$w0rd1234** y luego haga clic en **Aceptar**.

6. You may receive a certificate warning during the sign-in process. Click <bpt id="p1">**</bpt>Yes<ept id="p1">**</ept> to create the connection and connect to your deployed VM. You should connect successfully. Close the Windows Server and Dashboard windows that pop up. You should see a Blue Windows background. You are now in your virtual machine.

7. En **ambas** máquinas virtuales recién creadas, conéctese a través de RDP y deshabilite el firewall público y privado. Para ello, abra menú Inicio > Configuración > Network and Internet > Locate Windows Firewall (Menú Inicio > Configuración > Network e Internet > Locate Windows Firewall).

8. Abra PowerShell en la máquina virtual. Para ello, haga clic en el botón **Inicio** y, en Búsqueda, escriba **PowerShell**, haga clic con el botón derecho en **Windows PowerShell** y luego seleccione **Ejecutar como administrador**.

9. En PowerShell, intente hacer ping a vm2. Para ello escriba:

   ```PowerShell
   ping vm2
   ```

 10. You should be successful. You have pinged VM2 from VM1.


<bpt id="p1">**</bpt>Congratulations!<ept id="p1">**</ept> You have configured and deployed two virtual machines in a virtual network, and then you were able to connect them.

<bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: To avoid additional costs, you can optionally remove this resource group. Search for resource groups, click your resource group, and then click <bpt id="p1">**</bpt>Delete resource group<ept id="p1">**</ept>. Verify the name of the resource group and then click <bpt id="p1">**</bpt>Delete<ept id="p1">**</ept>. Monitor the <bpt id="p1">**</bpt>Notifications<ept id="p1">**</ept> to see how the delete is proceeding.

---
wts:
  title: '19: Usar la calculadora de precios de Azure (10 min)'
  module: 'Module 06: Describe Azure cost management and service level agreements'
---
# <a name="19---use-the-pricing-calculator-10-min"></a>19: Usar la calculadora de precios (10 min)

En este tutorial, utilizaremos la calculadora de precios de Azure para generar una estimación de costes para una máquina virtual de Azure y los recursos de red relacionados.

# <a name="task-1-configure-the-pricing-calculator"></a>Tarea 1: Configurar la calculadora de precios

En esta tarea, calcularemos el coste de una infraestructura de muestra con la Calculadora de precios de Azure. 

<bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: To create an Azure Pricing Calculator estimate, this walkthrough provides example configurations for the VM and related resources. Use this example configurations or provide the Azure Pricing Calculator with details of your <bpt id="p1">*</bpt>actual<ept id="p1">*</ept> resource requirements instead.

1. En el explorador, navegue hasta la página web [Calculadora de precios de Azure](https://azure.microsoft.com/en-us/pricing/calculator/).

2. Para agregar detalles de la configuración de su VM, haga clic en **Maquinas virtuales** en la pestaña **Productos**. Desplácese hacia abajo para ver los detalles de la máquina virtual. 

3. Replace <bpt id="p1">**</bpt>Your Estimate<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Virtual Machines<ept id="p2">**</ept> text with more descriptive names for your Azure Pricing Calculator estimate and your VM configuration. This walkthrough example uses <bpt id="p1">**</bpt>My Pricing Calculator Estimate<ept id="p1">**</ept> for the estimate, and <bpt id="p2">**</bpt>Windows VM<ept id="p2">**</ept> for the VM configuration.

   ![Screenshot of the vm configuration area within the Azure pricing calculator estimate webpage. The highlighted estimate name and vm configuration name indicate how to add an estimate name and a vm configuration name to an Azure pricing calculator estimate.](../images/1901.png)

4. Modifique la configuración de VM predeterminada.

    | Configuración | Value |
    | -- | -- |
    | Region | **Norte de Europa** |
    | Sistema operativo | **Windows** |
    | Tipo | **(Solo para sistema operativo)** |
    | Nivel | **Estándar** |  
    | Instancia | **A2: 2 núcleos, 3,5 GB de RAM, 135 GB de almacenamiento temporal** |

   ![Screenshot of the vm configuration area within the Azure pricing calculator estimate webpage. The highlighted examples of user inputted vm configuration property values indicate how to specify a vm configuration within an Azure pricing calculator estimate.](../images/1902.png)

    <bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: The VM instance specifications and pricing may differ from those in this example. Follow this walkthrough by choosing an instance that matches the example as closely as possible. To view details about the different VM product options, choose <bpt id="p1">**</bpt>Product details<ept id="p1">**</ept> from the <bpt id="p2">**</bpt>More info<ept id="p2">**</ept> menu on the right.

5. Ajuste la **Opción de facturación** en **Pago por uso**.

   ![Screenshot of the vm billing options area within the Azure pricing calculator estimate webpage. The highlighted pay as you go billing option indicates how to specify a billing option for a vm within an Azure pricing calculator estimate.](../images/1903.png)

6. **Nota**: Para crear una estimación de la Calculadora de precios de Azure, este tutorial ofrece configuraciones de ejemplo para la VM y recursos relacionados.

    Deje el número de máquinas virtuales establecido en `1` y cambie el valor de las horas por mes a `365`.

   ![Use estas configuraciones de ejemplo, o bien proporcione a la Calculadora de precios de Azure detalles de sus requisitos de recursos *reales*.](../images/1904.png)

7. En el panel **Discos de sistema operativo administrados**, modifique la configuración del almacenamiento de VM predeterminada.

    | Nivel | Tamaño del disco | Número de discos | Depurador de | Transacciones de almacenamiento |
    | ---- | --------- | --------------- | -------- | -------------------- |
    | HDD estándar | S30: 1 024 GiB | 1 | Desactivado | 10 000 |

   ![Screenshot of the managed OS Disks options area within the Azure pricing calculator estimate webpage. The highlighted tier type, disk size, number of disks, and number of storage transactions, options indicate how to specify a storage configuration for a vm within an Azure pricing calculator estimate.](../images/1905.png)

8. To add networking bandwidth to your estimate, go to the top of the Azure Pricing Calculator webpage. Click <bpt id="p1">**</bpt>Networking<ept id="p1">**</ept> in the product menu on the left, then click the <bpt id="p2">**</bpt>Bandwidth<ept id="p2">**</ept> tile. In the <bpt id="p1">**</bpt>Bandwidth added<ept id="p1">**</ept> message dialog, click <bpt id="p2">**</bpt>View<ept id="p2">**</ept>.

   ![Screenshot of the networking products area within the Azure pricing calculator webpage. The highlighted networking, add bandwidth, and view bandwidth, tiles indicate how to add and view details of a networking bandwidth configuration in an Azure pricing calculator estimate.](../images/1906.png)

9. Reemplace el texto **Su estimación** y **Virtual Machines** por nombres más descriptivos de su estimación de la Calculadora de precios de Azure y de la configuración de su máquina virtual.

    | Region | Cantidad de transferencia de datos salientes de la Zona 1 |
    | ------ | -------------------------------------- |
    | Norte de Europa | 50 GB |

   ![El ejemplo de este tutorial usa **Estimación de mi calculadora de precios** para la estimación y **Windows VM** para la configuración de la máquina virtual.](../images/1907.png)

10. To add an Application Gateway, return to the top of the Azure Pricing Calculator webpage. In the <bpt id="p1">**</bpt>Networking<ept id="p1">**</ept> product menu, click the <bpt id="p2">**</bpt>Application Gateway<ept id="p2">**</ept> tile. In the <bpt id="p1">**</bpt>Application Gateway<ept id="p1">**</ept> message dialog, click <bpt id="p2">**</bpt>View<ept id="p2">**</ept>.

    ![Captura de pantalla del área de configuración de la máquina virtual en la página web de estimación de la calculadora de precios de Azure.](../images/1908.png)

11. El nombre de la estimación y el nombre de la configuración de VM resaltados indican cómo agregar un nombre de estimación y un nombre de configuración de VM a una estimación de la calculadora de precios de Azure.

    | Configuración | Value |
    | -- | -- |
    | Region | **Norte de Europa** |
    | Nivel | **Basic** |
    | Size | **Pequeño** |
    | Instancias | **1** |  
    | Horas | **365** |
    | Datos procesados | **50 GB** |
    | Zona 1: Norteamérica, Europa | **50 GB**|

    ![Captura de pantalla del área de configuración de la puerta de enlace de aplicaciones dentro de la página web de estimación de la calculadora de precios de Azure.](../images/1909.png)


# <a name="task-2-review-the-pricing-estimate"></a>Tarea 2: Revisar el presupuesto de precios

En esta tarea, revisaremos los resultados de la Calculadora de precios de Azure. 

1. Desplácese hasta la parte inferior de la página web de la Calculadora de precios de Azure para ver el **Coste mensual estimado** total.

    <bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: Explore the various options available within the Azure Pricing Calculator. For example, this walkthrough requires you to update the currency to Euro.

2. Cambie la divisa a euro y luego seleccione **Exportar** para descargar una copia de la estimación y así poder verla sin conexión en formato Microsoft Excel (`.xlsx`).

    ![Screenshot of the total estimated monthly costs within the Azure pricing calculator estimate webpage. The highlighted euro currency option indicates how to modify the currency used in an Azure pricing calculator estimate. The highlighted export option illustrates how to download a copy of an estimate for offline viewing.](../images/1910.png)

    ![Captura de pantalla de un ejemplo de estimación de la calculadora de precios de Azure en Microsoft Excel.](../images/1911.png)

Congratulations! You downloaded an estimate from the Azure Pricing Calculator.

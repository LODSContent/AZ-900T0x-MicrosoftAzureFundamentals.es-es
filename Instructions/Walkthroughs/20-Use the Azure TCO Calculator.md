---
wts:
  title: "20: Usar la calculadora de TCO de Azure (10\_min)"
  module: 'Module 06: Describe Azure cost management and service level agreements'
---
# <a name="20---use-the-azure-tco-calculator-10-min"></a>20: Usar la calculadora de TCO de Azure (10 min)


En este tutorial usará la calculadora del coste total de propiedad (TCO) para generar un informe de comparación de costes para un ambiente local.

<bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: This walkthrough provides example definitions of on-premises infrastructure and workloads for a typical datacenter. To create a TCO Calculator report, use the example definitions or provide details of your <bpt id="p1">*</bpt>actual<ept id="p1">*</ept> on-premises infrastructure and workloads.

# <a name="task-1-configure-the-tco-calculator"></a>Tarea 1: Configurar la calculadora de TCO

En esta tarea agregaremos información de infraestructura a la calculadora. 

1. En el explorador navegue hasta la página [Calculadora del coste total de propiedad (TCO)](https://azure.microsoft.com/en-us/pricing/tco/calculator/).

2. Para agregar detalles de su infraestructura de servidor local, haga clic en **+ Agregar carga de trabajo del servidor** en el panel **Definir cargas de trabajo**.

    | Configuración | Value |
    | -- | -- |
    | Nombre | **Servidores: VM Windows** |
    | Carga de trabajo | **Servidor de Windows/Linux** |
    | Entorno | **Máquinas virtuales** |
    | Sistema operativo | **Windows** |  
    | Máquinas virtuales | **50** |
    | Virtualización | **Hyper-V** |
    | Núcleos | **8**|
    | RAM (GB) | **16** |
    | Optimizar por | **CPU** |
    | Windows Server 2008/2008 R2 | **Desactivado** |

3. Seleccione **+ Agregar carga de trabajo del servidor** para hacer una fila para una definición de cargas de trabajo del servidor nueva. 

    | Configuración | Value |
    | -- | -- |
    | Nombre | **Servidores: VM Linux** |
    | Carga de trabajo | **Servidor de Windows/Linux** |
    | Entorno | **Máquinas virtuales** |
    | Sistema operativo | **Linux** |  
    | Máquinas virtuales | **50** |
    | Virtualización | **VMware** |
    | Núcleos | **8**|
    | RAM (GB) | **16** |
    | Optimizar por | **CPU** |
    | Windows Server 2008/2008 R2 | **Desactivado** |

4. En el panel **Almacenamiento**, haga clic en **Agregar almacenamiento**.

    | Configuración | Value |
    | -- | -- |
    | Nombre | **Almacenamiento en servidor** |
    | Tipo de almacenamiento | **Disco local/SAN** |
    | Tipo de disco | **HDD** |
    | Capacity | **60 TB** |  
    | Backup | **120 TB** |
    | Archivar | **0 TB** |

5. En el panel **Redes**, agregue el ancho de banda. 

    | Configuración | Value |
    | -- | -- |
    | Ancho de banda saliente | 15 TB|

6. Haga clic en **Next**.

7. Explore las opciones y realice los ajustes que necesite. 

    | Configuración | Value |
    | -- | -- |
    | Moneda | **Euro** |

8. Haga clic en **Next**.

# <a name="task-2-review-the-results-and-save-a-copy"></a>Tarea 2: Revisar los resultados y guardar una copia

En esta tarea revisaremos las recomendaciones de ahorro de costes y descargaremos un informe. 

1. Revise las recomendaciones y visualizaciones de ahorro de Azure.

    | Configuración | Value |
    | -- | -- |
    | Período de tiempo| **3 años** |
    | Region | **Norte de Europa** |

2. Para modificar la información que proporcionó, vaya al final de la página y haga clic en **Atrás**. 

3. Para guardar o imprimir una copia en PDF del informe, haga clic en **Descargar**.

    ![Screenshot of the report pane of the tco calculator in Azure. The highlighted and completed input fields indicates how set the tco calculator timeframe to three years and the region to north europe. A graph shows the cost of on-premises infrastructure and workloads off-set against the reduced cost of using Azure.](../images/2001.png)

Congratulations! You have used the TCO Calculator to generate a cost comparison report for an on-premises environment.

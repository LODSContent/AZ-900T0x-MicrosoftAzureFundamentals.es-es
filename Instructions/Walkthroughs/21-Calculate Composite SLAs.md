---
wts:
  title: "21: Calcular acuerdos de nivel de servicio compuestos (5\_min)"
  module: 'Module 06: Describe Azure cost management and service level agreements'
---
# <a name="21---calculate-composite-slas-5-min"></a>21: Calcular acuerdos de nivel de servicio compuestos (5 min)

En este tutorial determinaremos el acuerdo de nivel de servicio de los servicios de Azure disponible y luego calcularemos la disponibilidad basada en el acuerdo de nivel de servicio compuesto de la aplicación esperada.

Our example application consists of these Azure services. We will not go in to deep architectural configuration and considerations, the intention here is to give an high level example.

+ **App Service**: Para hospedar la aplicación.
+ **Azure AD B2C**: Para autenticar inicios de sesión de usuarios y administrar perfiles.
+ **Application Gateway**: Para administrar el acceso a la aplicación y la escala. 
+ **Azure SQL Database**: Para almacenar datos de la aplicación. 

# <a name="task-1-determine-the-sla-uptime-percentage-values-for-our-application"></a>Tarea 1: Determinar los valores de porcentaje de tiempo de actividad del Acuerdo de nivel de servicio para nuestra aplicación

1. En un explorador, vaya a la página [Resumen de SLA para los servicios de Azure](https://azure.microsoft.com/en-us/support/legal/sla/summary/).

2. Locate the <bpt id="p1">**</bpt>App Service<ept id="p1">**</ept> SLA uptime value, <bpt id="p2">**</bpt>99.95%<ept id="p2">**</ept>. Click <bpt id="p1">**</bpt>View full details<ept id="p1">**</ept>, and then expand <bpt id="p2">**</bpt>SLA details<ept id="p2">**</ept>. Notice the <bpt id="p1">**</bpt>Monthly uptime percentages<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Service Credits<ept id="p2">**</ept>.

3. Regrese a la página web del contrato de nivel de servicio, localice el servicio **Azure Active Directory B2C** y determine el valor de tiempo de actividad del acuerdo (SLA), **99,9 %** . 

4. Localice el valor de tiempo de actividad del contrato de nivel de servicio de **Application Gateway**, **99,95 %** . 

5. The Azure SQL database uses Premium tiers but is not configured for Zone Redundant Deployments. Locate the <bpt id="p1">**</bpt>Azure SQL Database<ept id="p1">**</ept> SLA uptime value, <bpt id="p2">**</bpt>99.99%<ept id="p2">**</ept>. 

    <bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: There are different uptime values for different configurations and deployments of Azure SQL Database. It is important you are clear on your required uptime values, when planning and costing your deployment and configuration. Small changes in uptime can have impact on service costs as well as potentially increase complexity in configuration. Some other services that may be of interest on the Azure SLA summary web page would include <bpt id="p1">**</bpt>Virtual Machines<ept id="p1">**</ept>, <bpt id="p2">**</bpt>Storage Accounts<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Cosmos DB<ept id="p3">**</ept>.

# <a name="task-2-calculate-the-application-composite-sla-percentage-uptime"></a>Tarea 2: Calcular el tiempo de actividad del porcentaje del contrato de nivel de servicio compuesto de la aplicación

1. Nuestra aplicación de ejemplo consta de estos servicios de Azure.

    **% de tiempo de actividad de App Service** X **% de tiempo de actividad de Azure AD B2C** X **% de tiempo de actividad de Azure Application Gateway** X **% de tiempo de actividad de Azure SQL Database** =  **% de tiempo de actividad total**.

    que en términos de porcentaje es:

    **99,95 %** X **99,9 %** X **99,95 %** X **99,99 %**  = **99,79 %**

    Esta es la disponibilidad esperada basada en el contrato de nivel de servicio (SLA) de nuestra aplicación con los servicios y la arquitectura actuales.

No entraremos en configuraciones ni consideraciones arquitectónicas en detalle. La intención aquí es dar un ejemplo de alto nivel.

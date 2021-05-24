# Conceptos sobre computacion en la nube


## Containers y Kubernetes
Container Instances y Azure Kubernetes Service son recursos de Azure Compute que puede usar para implementar contenedores y administrarlos. Los contenedores son entornos de aplicación ligeros y virtualizados. Están diseñados para crearse, escalarse horizontalmente y detenerse dinámicamente de forma rápida. Puede ejecutar varias instancias de una aplicación en contenedores en un único equipo host.

## App Service
Con Azure App Service puede compilar, implementar y escalar de forma rápida aplicaciones de API, móviles y web de nivel empresarial que se pueden ejecutar en cualquier plataforma. Puede satisfacer los exigentes requisitos de rendimiento, escalabilidad, seguridad y cumplimiento mientras usa una plataforma totalmente administrada para realizar el mantenimiento de la infraestructura. App Service es una oferta de plataforma como servicio (PaaS).

## Functions
Functions es una opción ideal si le preocupa solo el código que ejecuta el servicio y no la infraestructura o la plataforma subyacente. Se usan normalmente cuando se debe realizar un trabajo en respuesta a un evento (a menudo a través de una solicitud REST), un temporizador o un mensaje de otro servicio de Azure, y cuando ese trabajo puede completarse rápidamente, en segundos o en menos tiempo.

Azure kubernetes. https://azure.microsoft.com/mediahandler/files/resourcefiles/kubernetes-learning-path/Kubernetes%20Learning%20Path%20version%201.0.pdf


## Clasificación de los datos.

### 1. Estructurados.
   Los datos estructurados, a veces denominados datos relacionales, son datos que se ajustan a un esquema estricto, por lo que todos los datos tienen los mismos campos o propiedades. El 
   esquema compartido hace que sea muy fácil realizar búsquedas en este tipo de datos con lenguajes de consulta como SQL (Lenguaje de consulta estructurado). Esta capacidad hace que este 
   estilo de los datos sea idóneo en usos como los sistemas CRM, las reservas y la administración de inventarios.

### 2. Datos semiestructurados.
   Los datos semiestructurados están menos organizados que los estructurados y no se almacenan en formato relacional, dado que los campos no encajan fácilmente en tablas, filas y 
   columnas. Los datos semiestructurados contienen etiquetas que hacen evidentes la organización y la jerarquía de los datos (por ejemplo, pares clave-valor). Los datos 
   semiestructurados también se conocen como datos no relacionales o datos NoSQL. La expresión y la estructura de los datos de este estilo se definen mediante un lenguaje de 
   serialización.
### 3. Datos no estructurados.

  La organización de los datos no estructurados es ambigua. A menudo, los datos no estructurados se entregan en archivos, como fotos o vídeos. El propio archivo de vídeo puede tener una 
  estructura general e incluir metadatos semiestructurados, pero los datos que forman el vídeo en sí mismo no están estructurados. Por tanto, las fotos, los vídeos y otros archivos 
  similares se clasifican como datos no estructurados.

Ejemplos de datos no estructurados son:

* Archivos multimedia, como fotos, vídeos y archivos de audio
* Archivos de Office, como documentos de Word
* Archivos de texto
* Archivos de registro

## Diferencias entre OLTP y OLAP
Las bases de datos transaccionales se conocen con frecuencia como sistemas OLTP (Procesamiento de transacciones en línea). Los sistemas OLTP normalmente admiten muchos usuarios, tienen tiempos de respuesta rápidos y controlan grandes volúmenes de datos. También son altamente disponibles (lo que significa que tienen un tiempo de inactividad mínimo) y normalmente controlan transacciones relativamente sencillas o pequeñas.

Por el contrario, los sistemas OLAP (Procesamiento analítico en línea) normalmente admiten menos usuarios, tienen tiempos de respuesta más largos, su disponibilidad puede ser menor y, por lo general, controlan transacciones grandes y complejas.

## Roles de disco
Cada disco puede tomar uno de estos tres roles en una máquina virtual:

+ Disco de SO. Un disco de cada máquina virtual contiene los archivos del sistema operativo. Cuando se crea una máquina virtual, se selecciona una imagen de máquina virtual y se fija el sistema operativo y el disco del sistema operativo que está conectado al nuevo equipo. El disco de SO tiene una capacidad máxima de 2 048 GB.
+ Disco de datos. Puede agregar uno o más discos virtuales de datos a cada máquina virtual para almacenar los datos. Por ejemplo, los archivos de base de datos, el contenido estático de sitios web o el código de aplicación personalizado deben almacenarse en discos de datos. El número de discos de datos que puede agregar depende del tamaño de la máquina virtual. Cada disco de datos tiene una capacidad máxima de 32 767 GB.
+ Disco temporal. Cada máquina virtual contiene un solo disco temporal, que se usa para las aplicaciones de almacenamiento a corto plazo, como los archivos de paginación y los de intercambio. El contenido de los discos temporales se pierde durante los eventos de mantenimiento, por lo que no se deben usar para datos críticos. Estos discos son locales para el servidor y no se almacenan en una cuenta de almacenamiento.

## Discos de sistema operativo efímeros.

Un disco de sistema operativo efímero es un disco virtual que guarda los datos en el almacenamiento de la máquina virtual local. Un disco efímero tiene una latencia de lectura y escritura más rápida que un disco administrado. Si usa un disco efímero, también resulta más rápido para restablecer la imagen al estado de arranque original. Pero un error en una máquina virtual individual podría destruir todos los datos de un disco efímero e impedir que la máquina virtual se pueda arrancar. Como los discos efímeros residen localmente en el host, no incurren en costos de almacenamiento y son gratuitos.

## Discos administrados.

La mayoría de los discos que se usan con máquinas virtuales en Azure son discos administrados. Un disco administrado es un disco duro virtual para el que Azure administra toda la infraestructura física necesaria. Como Azure se ocupa de la complejidad subyacente, los discos administrados son fáciles de usar. Basta con aprovisionarlos y asociarlos a las máquinas virtuales.
+ Escalabilidad sencilla. Puede crear hasta 50 000 discos administrados de cada tipo en cada región de la suscripción.
+ Alta disponibilidad. Los discos administrados admiten una disponibilidad del 99,999 %, ya que almacenan los datos tres veces. Si se produce un error en una réplica, las otras dos pueden mantener una funcionalidad de lectura y escritura completa.
+ Integración con conjuntos de disponibilidad y zonas. Si coloca las máquinas virtuales en un conjunto de disponibilidad, Azure distribuye de forma automática los discos administrados para esas máquinas en diferentes dominios de error, para que sean resistentes a los errores localizados. También puede usar zonas de disponibilidad, que distribuyen los datos en varios centros de datos, para ofrecer una disponibilidad aún mayor.
+ Compatibilidad con Azure Backup. Azure Backup admite de forma nativa los discos administrados, lo que incluye los discos cifrados.
+ Control de acceso pormenorizado. Puede usar el control de acceso basado en rol (RBAC) de Azure con el fin de conceder acceso a cuentas de usuario específicas para operaciones concretas en un disco administrado. Por ejemplo, podría asegurarse de que solo un administrador pueda eliminar un disco.
+ Compatibilidad con cifrado. Para proteger la información confidencial en un disco administrado frente al acceso no autorizado, puede cifrarlo mediante Storage Service Encryption (SSE) de Azure, que se proporciona con las cuentas de Azure Storage. Como alternativa, puede usar Azure Disk Encryption (ADE), que usa BitLocker para las máquinas virtuales Windows y DM-Crypt para las máquinas virtuales Linux.


## Discos no administrados
Un disco no administrado, como un disco administrado, se almacena como un blob en páginas en una cuenta de Azure Storage. La diferencia es que, con los discos no administrados, esta cuenta de almacenamiento se crea y se mantiene de forma manual. Este requisito significa que tendrá que realizar el seguimiento de los límites de IOPS en una cuenta de almacenamiento y asegurarse de no sobreaprovisionar el rendimiento de la cuenta de almacenamiento. También debe administrar la seguridad y el acceso RBAC en el nivel de la cuenta de almacenamiento, en lugar de hacerlo en cada disco individual con discos administrados.

Si ejecuta una máquina virtual antigua, es posible que tenga discos no administrados. Puede convertir esos discos no administrados en discos administrados mediante el cmdlet de PowerShell ConvertTo-AzureRmVmManagedDisk.

### Recordatorios.
+ Coloque todos los datos de la aplicación, incluidas las bases de datos y los archivos de contenido estático en discos de datos.
+ Los discos administrados garantizan un 99,999 % de disponibilidad porque los datos se replican de forma automática.
+ El SSD Ultra ofrece el mejor rendimiento de los tipos de disco en Azure
+ Los discos de nivel estándar no garantizan un rendimiento mínimo. Para ello, use discos SSD Premium.

## Azure DevOps Services
Azure DevOps Services es un conjunto de servicios que aborda cada fase del ciclo de vida de desarrollo de software.

* Azure Repos es un repositorio de código fuente centralizado en el que los profesionales de desarrollo de software, ingeniería DevOps y documentación pueden publicar su código para su revisión y colaboración.
* Azure Boards es un conjunto de administración de proyectos ágil que incluye paneles Kanban, informes, ideas de seguimiento y trabajo desde epopeyas de alto nivel hasta incidencias y elementos de trabajo.
* Azure Pipelines es una herramienta de automatización de canalizaciones de CI/CD.
* Azure Artifacts es un repositorio para hospedar artefactos, como código fuente compilado, que se puede incluir en los pasos de canalización de pruebas o de implementación.
* Azure Test Plans es una herramienta de pruebas automatizadas que se puede usar en una canalización de CI/CD para garantizar la calidad antes de publicar una versión de software.

Si su objetivo es automatizar la creación y la administración de un entorno de laboratorio de pruebas, considere la posibilidad de elegir Azure DevTest Labs. De las tres herramientas y servicios que hemos descrito, es el único que ofrece esta funcionalidad.

### Azure DevTest Labs
Azure DevTest Labs proporciona un medio automatizado para administrar el proceso de compilación, configuración y anulación de máquinas virtuales que contienen las compilaciones de los proyectos de software. De esta manera, los desarrolladores y los evaluadores pueden realizar pruebas en diferentes entornos y compilaciones. Esta funcionalidad no se limita a las máquinas virtuales. Cualquier cosa que se pueda implementar en Azure a través de una plantilla de Resource Manager se puede aprovisionar a través de DevTest Labs. El aprovisionamiento de entornos de laboratorio creados previamente con las herramientas y configuraciones necesarias ya instaladas supone un gran ahorro de tiempo para los desarrolladores y los profesionales de control de calidad.

Supongamos que necesita probar una nueva característica en una versión anterior de un sistema operativo. Azure DevTest Labs puede configurar todo automáticamente a petición. Una vez completadas las pruebas, DevTest Labs puede apagar y desaprovisionar la máquina virtual, lo que ahorra dinero cuando no está en uso. Para controlar los costos, el equipo de administración puede restringir el número de laboratorios que se pueden crear, el tiempo de ejecución, etc.

## Azure Advisor
Azure Advisor evalúa los recursos de Azure y hace recomendaciones que contribuyen a mejorar la confiabilidad, la seguridad y el rendimiento, lograr la excelencia operativa y reducir los costos. Advisor está diseñado para ayudarle a ahorrar tiempo en la optimización en la nube. El servicio de recomendaciones sugiere medidas que puede adoptar de inmediato, posponer o descartar.

Las recomendaciones están disponibles con Azure Portal y la API. Además, es posible configurar notificaciones para estar al tanto de las nuevas recomendaciones.

## Azure Monitor
Azure Monitor es una plataforma que permite recopilar, analizar y mostrar datos, así como llevar a cabo acciones en función de las métricas y los datos registrados en todo el entorno local y de Azure.

## Azure Service Health
Azure Service Health proporciona una vista personalizada del estado de los servicios, regiones y recursos de Azure en los que se basa su infraestructura. El sitio web status.azure.com, que muestra solo los principales problemas que afectan de manera generalizada a los clientes de Azure, no refleja el panorama completo. Sin embargo, Azure Service Health muestra los problemas detectados de mayor y menor importancia que le afectan. Los problemas del servicio son poco frecuentes, pero es importante estar preparado para lo inesperado. Por ello, puede configurar alertas que le ayuden a evaluar las interrupciones y el mantenimiento planeado. Después de una interrupción, Service Health proporciona informes de incidentes oficiales, llamados análisis de la causa principal (RCA), que puede compartir con las partes interesadas.

Elija Azure Advisor si quiere realizar un análisis de los recursos implementados. Azure Advisor analiza la configuración y el uso de los recursos, y ofrece sugerencias sobre cómo optimizar la confiabilidad, la seguridad, el rendimiento, los costos y las operaciones según los procedimientos recomendados por los expertos.

Si quiere mantener un control de Azure, especialmente de los servicios y regiones de los que dependa, debe elegir Azure Service Health. Puede ver el estado actual de los servicios de Azure de los que depende, las próximas interrupciones planeadas y los próximos servicios que se lanzarán. Puede configurar alertas que le permitan estar al día de incidentes y tiempos de inactividad futuros sin tener que visitar el panel con regularidad.

Elija Azure Monitor si quiere medir eventos personalizados y otros datos de telemetría recopilados. Los eventos personalizados, como los agregados al código fuente de las aplicaciones de software, pueden ayudar a identificar y diagnosticar la razón por la que la aplicación se comporta de una manera determinada.

## Azure Functions
Con el servicio Azure Functions, puede hospedar un único método o función mediante un lenguaje de programación popular en la nube que se ejecuta en respuesta a un evento. Un ejemplo de un evento podría ser una solicitud HTTP, un mensaje nuevo en una cola o un mensaje en un temporizador.

La solución Azure Functions es ideal si le preocupa solo el código que ejecuta el servicio y no la infraestructura o la plataforma subyacente. Azure Functions se usa con más frecuencia cuando es necesario realizar un trabajo en respuesta a un evento. Esto suele realizarse mediante una solicitud REST, un temporizador o un mensaje de otro servicio de Azure, y cuando ese trabajo puede completarse rápidamente, en segundos o en menos tiempo.

## Azure Logic Apps
Logic Apps es una plataforma de desarrollo de poco código o sin código hospedada como un servicio en la nube. El servicio le ayuda a automatizar y organizar tareas, procesos empresariales y flujos de trabajo cuando tiene que integrar aplicaciones, datos, sistemas y servicios en empresas u organizaciones. Logic Apps simplifica el diseño y la creación de soluciones escalables en la nube, en el entorno local o en ambos. Esta solución abarca la integración de aplicaciones, la integración de datos, la integración de sistemas, la integración de aplicaciones empresariales (EAI) y la integración de negocio a negocio (B2B).

Azure Logic Apps está diseñado en un entorno web y puede ejecutar una lógica que los servicios de Azure desencadenan sin escribir ningún código. Las aplicaciones se pueden compilar vinculando desencadenadores con acciones mediante conectores. Un desencadenador es un evento (como un temporizador) que hace que una aplicación se ejecute, que un mensaje nuevo se envíe a una cola o que se emita una solicitud HTTP. Una acción es una tarea o paso que se puede ejecutar. Hay acciones lógicas, como las que encontraría en la mayoría de los lenguajes de programación. Entre los ejemplos de acciones se incluyen trabajar con variables, instrucciones de decisión y bucles, y tareas que analizan y modifican datos.

Para crear soluciones de integración empresarial con Azure Logic Apps, se puede elegir entre una galería creciente de más de 200 conectores. La galería incluye servicios como Salesforce, SAP, Oracle DB y recursos compartidos de archivos.

### ¿Cuál es la diferencia entre estos servicios?
Puede llamar a Azure Functions desde Azure Logic Apps y viceversa. La principal diferencia entre los dos servicios es su intención. Azure Functions es un servicio informático sin servidor, y Azure Logic Apps está diseñado para ser un servicio de orquestación sin servidor. Aunque puede usar Azure Functions para orquestar un proceso empresarial de larga duración que implique varias conexiones, su caso de uso principal no era ese cuando se diseñó.

Además, los dos servicios tienen un precio diferente. Los precios de Azure Functions se basan en el número de ejecuciones y en el tiempo ejecución de cada una. Los precios de Logic Apps se basan en el número de ejecuciones y el tipo de conectores que se usan

Ayudamos a la empresa a elegir Azure Functions cuando necesitó compilar una solución que extrajese la lógica de código de un servicio de Windows en C# existente.

También le ayudamos a elegir Azure Logic Apps cuando necesitó orquestar un flujo de trabajo para evitar la pérdida de clientes tras una experiencia de compra negativa.


## Azure IoT Hub
Azure IoT Hub es un servicio administrado hospedado en la nube que actúa como centro de mensajes centralizado para la comunicación bidireccional entre la aplicación de IoT y los dispositivos que administra. Puede usar Azure IoT Hub para compilar soluciones de IoT con comunicaciones confiables y seguras entre millones de dispositivos de IoT y un back-end de soluciones hospedadas en la nube. Puede conectar prácticamente cualquier dispositivo al centro de IoT.

## Azure IoT Central

Azure IoT Central se basa en IoT Hub y agrega un panel que le permite conectar, supervisar y administrar sus dispositivos de IoT. La interfaz de usuario (UI) visual facilita la conexión rápida de nuevos dispositivos y la inspección a medida que comienzan a enviar mensajes de telemetría o de error. Puede ver el rendimiento general de todos los dispositivos en conjunto y configurar alertas que envían notificaciones cuando un dispositivo concreto necesita mantenimiento. Por último, puede enviar actualizaciones de firmware al dispositivo.

## Azure Sphere
Azure Sphere crea una solución de IoT de un extremo a otro de alta seguridad para los clientes que lo abarca todo, desde el hardware y el sistema operativo del dispositivo hasta el método seguro para enviar mensajes desde el dispositivo al centro de mensajes. Azure Sphere tiene características de comunicación y seguridad integradas para dispositivos conectados a Internet.

Azure Sphere consta de tres partes:

* La primera parte es la unidad de microcontrolador (MCU) de Azure Sphere, que se encarga de procesar el sistema operativo y las señales de los sensores conectados
* La segunda parte es un sistema operativo (SO) Linux personalizado, que controla la comunicación con el servicio de seguridad y puede ejecutar el software del proveedor.
* La tercera parte es el servicio de seguridad de Azure Sphere, también conocido como AS3. Su trabajo es asegurarse de que el dispositivo no se ha puesto en peligro de forma malintencionada. 


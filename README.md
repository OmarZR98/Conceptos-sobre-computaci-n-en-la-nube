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

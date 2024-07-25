# WEB Y REDES (En construccion)

# Red (Network)
Una red es un conjunto de computadoras y otros dispositivos interconectados que pueden comunicarse entre sí y compartir recursos (como archivos, impresoras, y conexiones a Internet).

Tipos de Redes:

- LAN (Local Area Network): Red local, como la de una oficina o una casa.
- WAN (Wide Area Network): Red de área amplia, que conecta redes locales a través de grandes distancias, como Internet.
- MAN (Metropolitan Area Network): Red de área metropolitana, que abarca una ciudad o campus universitario.
- PAN (Personal Area Network): Red personal, que conecta dispositivos a corta distancia, como un teléfono móvil con auriculares Bluetooth.

Protocolos Comunes:

- Ethernet, Wi-Fi, TCP/IP.

# Internet

La Internet es una red global que conecta millones de redes locales y dispositivos en todo el mundo.

Permite el acceso a servicios y aplicaciones como la web, el correo electrónico, la mensajería instantánea, y más

Protocolos comunes:

- TCP/IP

Componentes:

- Proveedores de Servicios de Internet (ISP): Empresas que proporcionan acceso a Internet.
- Backbones de Internet: Grandes redes de alta velocidad que transportan datos a través de largas distancias.
- Puntos de Presencia (PoP): Lugares donde los usuarios se conectan a la red de su ISP.

# Web (World Wide Web)

La web es un sistema de información que utiliza Internet para acceder a documentos y otros recursos interconectados mediante hipervínculos.

Los recursos de la web se identifican mediante URLs (Uniform Resource Locators).

Componentes:

- Páginas Web: Documentos de información que pueden contener texto, imágenes, videos y otros elementos multimedia.
- Navegadores Web: Aplicaciones que permiten a los usuarios acceder y visualizar páginas web (por ejemplo, Chrome, Firefox).

Protocolos Comunes:

- HTTP/HTTPS: Protocolos utilizados para transferir páginas web entre servidores y navegadores.
- HTML (Hypertext Markup Language): Lenguaje utilizado para crear y estructurar páginas web.

# Relación entre Red e Internet y la Web

## Internet:

- Es la red global que conecta múltiples redes locales, permitiendo la comunicación y el intercambio de datos a nivel mundial.
- Usa el conjunto de protocolos TCP/IP para asegurar que los datos se transmitan correctamente entre diferentes dispositivos y redes.
- La web (World Wide Web) es solo una de las muchas aplicaciones que funcionan sobre Internet. Otras aplicaciones incluyen correo electrónico, FTP, y mensajería instantánea.

## La Web:

- Es un servicio específico que se ejecuta sobre Internet.
- Utiliza la infraestructura de Internet para permitir el acceso y la navegación a través de documentos y recursos enlazados mediante hipervínculos.

# Red:

- Puede referirse a cualquier sistema interconectado de computadoras y dispositivos, ya sea local o global.
- ejemplos: La red de una empresa (LAN), la red de un campus universitario (MAN).

# HTTP (HyperText Transfer Protocol)

Es un protocolo de comunicacion que permite la trasferencia de datos a traves de la web (World Wide Web).

HTTP define cómo los mensajes transmiten y cómo los navegadores web y servidores web deben responder a diversas solicitudes.

Define cómo se formulan (estructuran) las solicitudes y respuestas.

## Características Principales

Es un Protocolo de Capa de Aplicación:

HTTP opera en la capa de aplicación del modelo OSI (Open Systems Interconnection) y del modelo TCP/IP. 

## Métodos HTTP:

GET: Solicita la representación de un recurso específico.

POST: Envía datos al servidor para crear o actualizar un recurso.

PUT: Actualiza un recurso existente o crea uno nuevo si no existe.

DELETE: Elimina un recurso especificado.

HEAD: Similar a GET, pero solo recupera los encabezados de la respuesta.

OPTIONS: Describe las opciones de comunicación disponibles para el recurso de destino.

PATCH: Aplica modificaciones parciales a un recurso

## Encabezados HTTP:

Proporcionan metadatos sobre la solicitud o respuesta. Ejemplos: Content-Type, Content-Length, User-Agent, Accept, etc.

## Flujo: 
- Un cliente (navegador web, Postman, etc.) envía una solicitud HTTP a un servidor web.
- El servidor procesa la solicitud: El servidor recibe la solicitud, la procesa y busca el recurso solicitado.
- El servidor responde con un mensaje HTTP que incluye un código de estado (por ejemplo, 200 OK), encabezados HTTP y el cuerpo del mensaje (como el HTML de una página web).
- Cliente recibe la respuesta y procesa los datos según corresponda (por ejemplo, renderizando una página web).

# Modelo TCP/IP  (Transmission Control Protocol/Internet Protocol)

Actualmente la mayoría de ordenadores están conectados a alguna red (internet, intranet, etc.) y casi todos lo hacen utilizando el modelo TCP/IP. Este modelo es un protocolo para comunicación en redes que permite que un equipo pueda comunicarse dentro de una red.

La definición de TCP/IP es la identificación del grupo de protocolos (TCP e IP) de red que hacen posible la transferencia de datos en redes, entre equipos informáticos e internet. Las siglas TCP/IP hacen referencia a este grupo de protocolos:

- TCP es el Protocolo de Control de Transmisión: permite la conexión entre dos dispositivos (emisor y receptor) a través de internet u otras redes y el intercambio de datos (redirecciona o dirigir los datos a un dispositivo receptor a traves de los puertos). TCP se asegura de que los datos lleguen completos  y sin pérdidas y en el orden correcto, se pueden retransmitir si es necesario.
- TCP tambien utiliza números de puerto para redireccionar o dirigir los datos a la aplicación o servicio correcto en el dispositivo receptor. Hay numerosos números de puerto, y son una parte esencial de cómo funciona Internet.
- TCP se encarga de dividir los datos en segmentos (paquetes), enviarlos de manera confiable al destino.
- Puertos: Son servicios que estan corriendo en un servidor o ordenador. Por ejemplo los servidores tienen puertos específicos abiertos para escuchar conexiones entrantes
- IP o protocolo de internet, utiliza direcciones series de cuatro octetos con formato de punto decimal (como por ejemplo 75.4.160.25). Este protocolo lleva los datos a otras máquinas de la red.

## Ejemplo: 

Tipos de Datos Enviados a Través de TCP.

1. Solicitud HTTP/HTTPS:

- Cuando un cliente (por ejemplo, un navegador web) se conecta a un servidor web, normalmente envía una solicitud HTTP o HTTPS.
- Esta solicitud puede incluir diferentes tipos de datos, como:
  - Método HTTP: Como GET, POST, PUT, DELETE.
  - URL: La dirección del recurso que el cliente está solicitando.
  - Encabezados HTTP: Información adicional sobre la solicitud, como el tipo de contenido que el cliente acepta (Accept), la información del agente de usuario (User-Agent), cookies, etc.
  - Cuerpo de la Solicitud: En solicitudes POST o PUT, puede incluir datos que el cliente está enviando al servidor, como formularios de datos o cargas de archivos.

2. Respuesta HTTP/HTTPS:

- El servidor web responde con una respuesta HTTP o HTTPS que también utiliza TCP para la transmisión.
- La respuesta puede incluir:
  - Código de Estado HTTP: Como 200 OK, 404 Not Found, 500 Internal Server Error.
  - Encabezados HTTP: Información adicional sobre la respuesta, como el tipo de contenido (Content-Type), longitud del contenido (Content-Length), etc.
  - Cuerpo de la Respuesta: El contenido solicitado por el cliente, que puede ser una página HTML, un archivo de imagen, datos JSON, etc.
 
***Define cómo se envían y reciben los datos a través de la red de Internet*** 

El modelo TCP/IP está compuesto por cuatro niveles o capas:  

1. Capa de Acceso a la Red (o Capa de Enlace):

Es la primera capa del modelo. 
 
Función: Maneja la transmisión de datos en la red física. Incluye tecnologías como Ethernet y Wi-Fi.
Ejemplo: La tarjeta de red de tu computadora enviando bits a través de un cable Ethernet.

2. Capa de Red o Internet:

Función: Proporciona el paquete de datos y maneja el direccionamiento y el enrutamiento de los datos a través de la red global (Internet).
El protocolo principal en esta capa es el IP (Internet Protocol).
Ejemplo: Un paquete IP que contiene la dirección IP de origen y destino

3. Capa de Transporte: 

Función: Asegura que los datos se transmitan de manera confiable entre sistemas finales.
Protocolos principales: TCP (Transmission Control Protocol) y UDP (User Datagram Protocol).
Ejemplo: TCP divide los datos en segmentos, los envía, y asegura que lleguen en orden y sin errores.

4. Capa de Aplicación:

La capa de aplicación es la que directamente interactúa con los programas que el usuario utiliza, como navegadores web, clientes de correo, y aplicaciones de transferencia de archivos.

Es la capa más alta y donde se ejecutan los protocolos que interactúan con el software de la aplicación.
Ejemplo: HTTP para navegar por la web, SMTP para enviar correos electrónicos, FTP para transferir archivos.

## Ejemplo Práctico

1. Navegador Web (Aplicación):
Tú, como usuario, escribes una URL en tu navegador web.

2. HTTP (Protocolo de Capa de Aplicación):
   
- El navegador utiliza el protocolo HTTP para solicitar la página web al servidor.
- Esta solicitud HTTP se crea y procesa en la capa de aplicación.

3. Capas Inferiores:

- Capa de Transporte (TCP): HTTP utiliza TCP para asegurar que la solicitud llegue correctamente al servidor.
- Capa de Internet (IP): TCP/IP maneja el direccionamiento y el enrutamiento para llevar la solicitud a través de Internet.
- Capa de Acceso a la Red: Los datos se transmiten físicamente a través de la red local (por ejemplo, a través de Ethernet o Wi-Fi).

# SSH (Secure Shell protocol)
Es un protocolo de red popular que nos permite acceder a una computadora remota a traves de una red 
como internet.

Tambien encrypta la comunicacion de datos entre dos computadores. Se utiliza ampliamente para
comunicarse con una computadora remota a traves de internet.

Normalmente, un administrador del servidor instala un programa de servidor que acepta o rechaza las conexiones entrantes.

Es un protocolo de red que permite el acceso remoto a traves de una conexion cifrada. Proporciona
una autenticacion robusta y es compatible con el inicio de sesion remoto seguro, la ejecucion
de comandos, la transferencia de archivos, el control de acceso y el reenvio de TCP/IP.

Puedes gestionar tus archivos y carpetas a traves de una conexion SSH, modificar sus permisos,
editar archivos directamente en el servidor, etc.

## Para que se utiliza?

Este protocolo crea un canal seguro entre una computadora local y un servidor remoto, permitiendo la ejecucion de comandos, 
acceso a recursos, transferencia de archivos, actualizaciones de rendimiento, etc.

- Comunicacion entre maquinas locales y remotas.

- Acceso remoto a los recursos del servidor.

- Ejecutar comandos en la maquina host remota. (proporciona varios comandos ejecutables)

- Realizar tareas de administracion de tareas.


# SSL/TLS (Secure Sockets Layer, Transport Layer Security)

Son protocolos criptograficos (conjunto de reglas que se utilizan para asegurar la comunicacion segura entre dos partes en una red
, se basan en tecnicas de cifrado) que se utilzan para brindar seguridad en las comunicaciones de internet.

Estos protocolos cifran los datos que se transmiten a traves de la web, por lo que cualquiera que intente interceptar paquetes
no podra  interceptar los datos. 

Actualmente SSL esta en desuso debido a fallas de seguridad y la mayoria de de los navegadores web modernos ya no lo admite. Pero
TLS sigue siendo seguro y ampliamente compatible.

### Encriptacion: SSL/TLS encripta los datos transmitidos entre un cliente (por ejemplo, un navegador web) y un servidor, evitando
### que partes no autorizadas puedan leer informacion sensible.

### Integridad de los datos: SSL/TLS verifica que los datos transmitidos entre cliente y el servidor permanezcan sin cambios durante el 
### transito, detectando cualquier intento de manipulacion.

### Autenticacion: SSL/TLS permite que tanto el cliente como el servidor autentiquen las identidades del otro, asegurando que esten 
### comunicandose con las partes previstas.

### Ejemplo: Cuando rellenas un formulario en un sitio web y envías los datos, la encriptación SSL/TLS se utiliza para proteger
### la transmisión de esos datos desde tu navegador hasta el servidor web del sitio. Esto significa que los datos que ingresaste en el 
### formulario, como tu nombre, dirección, contraseña u otra información personal, son encriptados antes de ser enviados a través de Internet.

# FTP (File Transfer Protocol) y SFTP (SSH File Transfer Protocol)

Son dos protocolos utilizados para transferir archivos entre un cliente y un servidor a través de una red.

## Diferencias: 

### FTP (File Transfer Protocol)

- FTP es uno de los protocolos de transferencia de archivos más antiguos y ampliamente utilizados en Internet.

- Permite la transferencia de archivos entre un cliente y un servidor de manera sencilla.

- Funciona sobre el puerto estándar 21.

- FTP transfiere datos en texto claro, lo que significa que la información, incluyendo las credenciales de inicio de sesión, se envía sin cifrar, 
lo que puede ser un riesgo de seguridad.

- FTP no proporciona encriptación de extremo a extremo, por lo que es vulnerable a ataques de escucha de red y captura de datos.

### SFTP (SSH File Transfer Protocol)

- SFTP es una extensión segura de FTP que utiliza SSH (Secure Shell) para cifrar los datos durante la transferencia.

- Funciona sobre el puerto estándar 22.

- SFTP proporciona una capa adicional de seguridad al cifrar tanto la autenticación como la transferencia de datos, lo que la hace más segura que FTP.

- Utiliza claves de autenticación y cifrado para proteger la conexión entre el cliente y el servidor.

- SFTP es compatible con la mayoría de las funciones de FTP estándar, lo que facilita la migración desde FTP a SFTP para mejorar la seguridad de las transferencias de archivos.

# DNS

DNS (Domain Name System) es un sistema de nomenclatura jerárquica utilizado para traducir nombres de dominio legibles por humanos, como "example.com", 
en direcciones IP numéricas que las computadoras utilizan para identificar y comunicarse entre sí en una red. Básicamente, DNS actúa 
como una "libreta de direcciones" de Internet, facilitando la resolución de nombres de dominio a direcciones IP.

Aquí hay una descripción de cómo funciona el DNS:

- Solicitud de resolución: Cuando escribes una dirección web en tu navegador (por ejemplo, "www.ejemplo.com") y presionas Enter, tu computadora necesita traducir ese nombre de dominio en una dirección IP para localizar el servidor web correspondiente.
- 
- Consulta DNS: Tu computadora envía una consulta al servidor DNS configurado en tu red (generalmente proporcionado por tu ISP o configurado manualmente). Si no se encuentra la información en ese servidor, se pasa a otros servidores DNS en cascada.
- 
- Recorrido de resolución: La consulta se realiza en múltiples servidores DNS, comenzando por los servidores de nombres de nivel superior (TLD) como ".com", ".org" o el dominio de nivel superior específico del país (como ".es" para España). Luego, se pasa a los servidores de nombres autoritativos del dominio, que contienen la información más actualizada sobre el dominio específico.
- 
- Respuesta DNS: Una vez que se encuentra la dirección IP correspondiente al nombre de dominio solicitado, se envía una respuesta al cliente DNS original (tu computadora). Esta respuesta incluye la dirección IP del servidor web asociado con el nombre de dominio.
- 
- Acceso al sitio web: Con la dirección IP obtenida, tu computadora puede establecer una conexión con el servidor web del sitio solicitado y solicitar la página web correspondiente.
- 
- Es importante destacar que el DNS es fundamental para el funcionamiento de Internet, ya que permite a los usuarios acceder a los recursos en línea utilizando nombres de dominio fácilmente memorizables en lugar de tener que recordar direcciones IP numéricas complicadas. Además, el DNS también se utiliza para otros servicios, como la entrega de correo electrónico y la resolución de nombres de host en redes locales.

















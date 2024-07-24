
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

















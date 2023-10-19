# Recursos de una DB
El agotamiento de recursos debido a una falta de cierre de conexiones de una bd en un problema real que puede afectar
negativamente el rendimiento de una aplicacion, y en ultima instancia, llevar a la indisponibilidad del sistema.

## Agotamiento de conexiones a la BD:
Cada vez que un usuario realiza una solicitud a la aplicacion, se abre una conexion a la bd para obtener o modificar datos.
Si estas conexiones no se cierran adecuadamente, se acumularan a largo del tiempo, y en algun momento, la bd alcanzara su limite de conexiones
permitidas.

Numero de conexiones permitidas se refiere al numero de sesiones de usuario o aplicaciones que pueden conectarse y trabajar con 
la base de datos al mismo tiempo. Cada vez que un usuario o aplicaciones se conecta a una base de datos, se crea una conexion activa.

Estas conexiones activas son importantes para controlar la utilizacion de recursos del `servidor` de base de datos y garantizar
un rendimiento estable. Si se permiten demasiadas conexiones simultaneas, el servidor podria agotar sus recursos como memoria, CPU,
y capacidad de red, lo que podria llevar a un mal rendimiento o incluso una caida del servidor. 

## Bloqueo de usuarios
Cuando se alcanza el limite de conexiones a la bd, los usarios adicionales no podran conectarse, lo que puede resultar en bloqueos y 
tiempos de espera  para los usuarios, lo que afecta la experiencia de usuario y reduce la disponibilidad del servicio.

## Agotamiento de recursos del servidor.
Las conexiones no cerradas tambien consumen recursos del servidor, como memoria  y capacidad de CPU. 

MEMORIA: Cada conexion activa requiere una cierta cantidad de memoria para  almacenar informacion sobre la sesion como variables de estado, 
buferes y resultados parciales.

CPU: El servidor de base de datos debe dedicar tiempo de CPU para procesar las solicitudes y consultas que llegan a traves de cada conexion,
cuantas mas conexiones existan, mayor sera la caga en la CPU del servidor.

Como concecuencia puede resultar en un mal rendimiento de la aplicacion, y en ultima instancia, hacer 
que el servidor se vuelva mas lento o incluso bloquee debido al
agotamiento de los recursos.

## Reinicio del servidor 
En situaciones extremas, el agotamiento de recursos puede llevar al reinicio del servidor para liberar recursos. Esto interrumpira el 
servicio y afectara la disponibilidad de la aplicacion.


# Servidores 

Son maquinas computudadores (fisicas o virtuales) que son capaces de realizar(proveer) algun tipo de servicio como por ejemplo:
  Servidor web.
  Servidor de correo electronico
  Servidor de base de datos.
  Servidor de archivos
  Servidor de aplicaciones
  Servidor proxy
  Servidor DNS
  Servidor de impresion
  Servidor de juegos 
  Servidor de almacenamiento de red 
  Servidor de chat

# Base de datos y despliegue

Las bases de datos pueden estar en local, en un servidor de produccion/test.
Para desplegar una base de datos local a la nube(o servidor destino) se deben generar
scrips para generar la misma structura (la misma estructura que se encuentra en local)
y los datos que se quieran migran desde la db local a la base de datos que se usara en produccion o test.
(en palabras simples se realizar una migración).
Luego, asegurarce de actualizar la cadena de conexion que apunte al servidor destino o la
base de datos desplegada.

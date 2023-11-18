# HTTPS 

## HTTP = "Hypertext transfer protocol"

Es un protocolo que permite realizar una
peticion  de datos y recursos como pueden ser documentos HTML.
Es la base de cualquier intercambio de datos de la web

Es un protocolo de estructura cliente-servidor, esto quiere decir que 
una petición de datos es iniciada por el elemento que recibira los datos.
(cliente), normalmente el navegaro web.

Asi que una pagina web compelta resulta de la unión de distintos
sub-documentos recibidos, como, por ejemplo: un documento que especifique el 
estilo de maquetación de la página web(web), el texto, las imágines, videos,
scripts, etc

Se transmite sobre el protocolo TCP, o el protocolo encriptado TLS.

## Arquitectura de los sistemas basados en HTTP

HTTP es un protocolo basado en el principio cliente-servidor: las peticiones
son enviadas por una entidad: el agende del usuario (o un proxy a petición).
La mayoría de las veces el agende del usuario (cliente) es un navegador Web, 
pero podria ser cualquier otro programa, como por ejemplo un programa-robot,
que explore la Web, para adquirir datos de sus estructura y contenido para uso 
de un buscador de internet.

Cada petición individual se envía a un servidor, el cuál la gestiona y responde.
Entre cada petición y repúesta, hay varios intermediarios, normalmente denominados
proxies, los cuales realizan distintias funciones, como: gateways o caches


## Cliente: el agende del usuario

El agente usuario, es cualquier herramienta que actué en representación del usuario. 
Esta función es realiza en la parte de los casos por un navegador Web.
El nagegador es siempre el que inicia una comunicación (petición), y el servidor 
nunca la comienza 

Para mostrar una pagina web, el navegador envía una petición de documento HTML
al servidor. Entonces procesa este documento y envia mas peticiones para solicitar
scripts, css y otros datos que necesite (normalmente videos y/o imágenes)

El navegador une estos documentos y datos y realiza la pagina web. Los scripts 
los ejecuta tambien el nagegador.

Una pagina web es un documento de hipertexto. El navegador, traduce estas
direcciones en peticiones de HTTP, e interpreta y procesara las respuestas 
HTTP  para presentar al usuario la página Web que desea.

## El servidor Web

El servidor "sirve" los datos que ha pedido el cliente. Un servidor es una unica
entidad, aunque puede estar formado por varios elementos, que se reparten la carga de+
peticiones, (load balancing), u otros programas que gestionas otros computadores
(como cache, base de datos, servidor de correo electronico) que generan 
parte o todo el documento que ha sido pedido.

El servidor no tiene que ser necesariamente un servidor fisico, aunque varios 
servidores pueden estan funcionando en un único computador.

## Proxies

Aquello dispositivos, que sí operan procesando la capa de aplicación son 
conocidos como proxies. Estos pueden transparentes, o no (modificando)
las peticiones que pasan por ellos, realizando estas funciones:

- caching (la caché puede ser pública o privada, como la caché de un navegador)
- filtrado (como un anti-virus, control parental, ...)
- balanceo de carga de peticiones (para permitir a varios servidores responder
a la carga total de peticiones que reciben)
- autentificación (para el control al acceso de recursos y datos)
- registro de eventos (para tener un historico de los eventos que se producen)


## Cookies

Como HTTP es un protocolo sin estado, el uso de HTTP cookies, si permite
guardar datos con respecto a la sesión de comunicación. Usando la capacidad
de ampliación del protocolo HTTP,las cookiies permiten crear un contexto
común para cada sesión de comunicación. 

- El uso de "carros de compras" en páginas que utilizan en comercio electronico.   
- mantener la sesion de un usuario abierta.
- Permiten recordar la información de estado en vista a que el protocolo HTTP
es un protocolo sin estado.
- Gestion de sesiones: Inicios de sesión, carritos de compras, puntajes de juegos
o cualquier otra cosa que el servidor deba recordar.
- Personalización: Preferencias de usuario, temas y otras configuraciones.
- Rastreo: Guardar y analizar el comportamiento del usuario.

## ¿Que se puede controlar con HTTP?

- Cache: El como se alamacenan los documentos en la caché, puede ser espeficicado
por HTTP. El servidor puede indicar a a los proxies y clientes que quiere 
almacenar y durante cuanto tiempo. 

- Flexibilidad del requisito de origen: Para prevenir invasiones de la privacidad
de los usuarios, los navegadores Web, solamente permiten a páginas del mismo origen,
compartir la información o datos. Esto es una complicación para el servidor, asi 
que mediante cabeceras HTTP se puede flexibilizar o relajar esta división entre cliente
y servidor.

- Autentificación: Hay páginas web que pueden estan protegidas, de manera que solo
los usuarios autorizados puedan acceder. HTTP provee de servicios básicos de autentificación
, por ejemplo mediante el uso de cabeceras como: WWW-Authenticate, o establecendiendo 
una sesión especifica mediante el uso de HTTTP cookies. 

- Proxies: Servidores y/o clientes pueden estar en intranets y esconder asi 
su verdadera direccion IP a otros.



## Peticiones

![peticion http imagen](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview/http_request.png)

Una peticion HTTP, esta formada por los siguientes campos:

- Method = post, get, put, delete (etc)
- Path = Url del recurso
- Version del protocolo HTTP
- Cabeceras HTTP opcionales, que aportar informacion de la peticion
- Cuerpo del mensaje, en algun método, como puede ser POST, en el cuál
envía la información para el servidor.


## Respuestas

![peticion http imagen](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview/http_response.png)

Una respuesta HTTP, esta formada por los siguientes campos:

- La versión del protocolo HTTP que están usando.
- Un código de estado, indicando si la petición ha sido exitosa, o no.
- Un mensaje de estado, una breve descriptción del código de estado.
- Cabeceras HTTP, como de las peticiones.
- Opcionalmente, el recurso qeu se ha pedido.



# Request and Responses 

![mensajes http imagen](https://developer.mozilla.org/en-US/docs/Web/HTTP/Messages/httpmsgstructure2.png)


# Request

## Headers
    
Cabeceras generales, ('General headers' en inglés), como Via (en-US), afectan al mensaje como una unidad completa.

Cabeceras de petición, ('Request headers' en inglés), como User-Agent, Accept-Type, modifican la petición especificándola en mayor detalle ( como: Accept-Language (en-US), o dándole un contexto, como: Referer, o restringiéndola condicionalmente, como: If-None.

Cabeceras de entidad, ('Entity headers' en ingles), como Content-Length las cuales se aplican al cuerpo de la petición. Por supuesto, esta cabecera no necesita ser transmitida si el mensaje no tiene cuerpo ('body' en inglés).
 )

![mensajes http imagen](https://developer.mozilla.org/en-US/docs/Web/HTTP/Messages/http_request_headers3.png)


## Cuerpo

La parte final de la petición el el cuerpo. No todas las peticiones llevan uno: las peticiones que reclaman datos, como GET, HEAD, DELETE, o OPTIONS, normalmente, no necesitan ningún cuerpo. Algunas peticiones pueden mandar peticiones al servidor con el fin de actualizarlo: como es el caso con la petición POST (que contiene datos de un formulario HTML).

Los cuerpos pueden ser dividos en dos categorias:

Cuerpos con un único dato, que consisten en un único archivo defindo por las dos cabeceras: Content-Type y Content-Length.

Cuerpos con múltiples datos, que están formados por distintos contenidos, normalmente estan asociados con los formularios HTML (en-US).


# Response

Las cabeceras HTTP para respuestas siguen también la misma estructura como cualquier otra cabecera: una cadena de texto, que no diferencia entre mayusculas y minúsculas, seguida por dos puntos (':') y un valor cuya estructura depende del tipo de cabecera. Toda la cabecera incluido su valor, se ha de expresar en una única línea.

Existen varias cabeceras posibles. Estas se puede dividir en distintos grupos:

Cabeceras generales, ('General headers' en inglés), como Via (en-US), afectan al mensaje completo.

Cabeceras de petición, ('Request headers' en inglés), como Vary , Accept-Ranges, dan información adicional sobre el servidor, que no tiene espacio en la línea de estado.

Cabeceras de entidad, ('Entity headers' en ingles), como Content-Length las cuales se aplican al cuerpo de la petición. Por supuesto, esta cabecera no necesita ser transmitida si el mensaje no tiene cuerpo ('body' en inglés).

![mensajes http imagen](https://developer.mozilla.org/en-US/docs/Web/HTTP/Messages/http_response_headers3.png)

## Cuerpo

La última parte del mensaje de respuesta el es 'cuerpo'. No todas las respuestas tienen uno, respuestas con un código de estado como 201 o 204 (en-US) normalmente prescinden de él.

De forma general, los cuerpos se pueden diferenciar en tres categorias:

Cuerpos con un único dato, consisten en un simple archivo, de longitud conocida y definido en las cabeceras: Content-Type y Content-Length.

Cuerpos con un único dato, consisten en un simple archivo, de longitud desconocida, y codificado en partes, indicadas con Transfer-Encoding valor chunked (que significa: 'partido' en inglés).

Cuerpos con múltiples datos, consisten de varios datos, cada uno con una sección distinta de información. Este caso es relativamente raro y poco común.



## JSON

*ES UN FORMATO QUE SE UTILIZA PARA ALMACENAR E INTERCAMBIAR DE DATOS

Explicacion: Si estas trabando con un lenguaje de programacion no tengas inconvenientes en enviar esta informacion a otro lenguaje de
programacion o otra tecnologia. Se utiliza bastante un solicitudes HTTP para hacer la transferencia de datos.

- Un documento json consiste en una serie de pares clave-valor.
- Los archivos json contienen solo texto.
- Representa informacion estrucuturada en forma de texto.
- Un documento json esta compuestto principalmente por cadenas de texto que representan nombres de propiedades
y valores.

Es un formato de archivo y un formato de intercambio de datos que utiliza texto legible por los
humanos para almacenar y transmitir objetos de datos que consisten en pares y matrices de atributo valor. 
Un uso comun es el intercambio de datos HTTP entre aplicaciones web y servidores.

## Serialization
Significa convertir objetos en un formato que pueda ser transportado, este formato es un STRING.
Este string por dentro tiene un formato de JSON (o xml)

## Deserialization
Es la operacion inversa convierte string a objetos

## Resumen 
Al transmitir datos (https) o almacenarlos en un archivo, se requiere que los datos sean cadenas de bytes
pero los objetos complejos rara vez tienen ese formato

La serializacion puede convertir estos objetos complejos en cadenas de bytes para dicho uso.
Una vez transmitidas las cadenas de bytes, el receptor tendra que recuperar el objeto original
de la cadena de bytes. Esto se conoce como deserializacion.

Ejemplo:

Tienes un objeto.
```
{foo: [1, 4, 7, 10], bar: "baz"}
```

Serializar lo convertirá en una cadena:
```
'{foo: [1, 4, 7, 10], bar: "baz"}'
```
que se puede almacenar y enviar a cualquier lugar (cuando se encuentra en string ya se puede enviar por la web).
Luego el receptor puede deserializar esta cadena para recuperar el objeto.


*Explicacion larga en C#

*La serialización es el proceso de convertir un objeto en un formato que puede ser fácilmente 
almacenado o transmitido y posteriormente reconstruido. En el contexto de tu aplicación web 
ASP.NET Core, cuando devuelves un objeto desde un controlador, este objeto se serializa a un 
formato específico antes de ser enviado como respuesta HTTP.

*En tu código, estás utilizando el método Ok() para devolver un objeto de tipo RepuestaApi. 
Este objeto se serializa automáticamente a formato JSON antes de ser enviado como respuesta HTTP 
al cliente. La serialización a JSON implica convertir las propiedades y valores del objeto en una 
cadena de texto JSON que pueda ser interpretada por el cliente.

*ASP.NET Core utiliza un mecanismo de serialización JSON incorporado para realizar esta tarea. 
En la configuración predeterminada, se utiliza el serializador JSON proporcionado por el 
paquete System.Text.Json, que es parte del .NET Core Framework. Sin embargo, 
en algunos casos, puedes optar por utilizar bibliotecas de terceros como Newtonsoft.Json (Json.NET) 
para personalizar la serialización.

















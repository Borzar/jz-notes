# Web Services

Un Servicio Web es una forma especifica de implementar una API.

Un servicio web es un conjunto de protocolos y estándares que permite que diferentes aplicaciones se comuniquen a 
través de la red. Los servicios web utilizan tecnologías como HTTP (Hypertext Transfer Protocol) para la 
comunicación y XML (eXtensible Markup Language) o JSON (JavaScript Object Notation) para el intercambio de datos.

Algunos de los estándares comunes asociados con servicios web incluyen WSDL (Web Services Description Language) para 
describir la interfaz de servicio, UDDI (Universal Description, Discovery, 
and Integration) para el registro y descubrimiento de servicios, y SOAP o REST para la comunicación real.

Existen diferentes tipos de servicios web, pero los dos más comunes son:

## SOAP (Simple Object Access Protocol)
SOAP es un protocolo de comunicación estándar basado en XML. Define una estructura de mensajes y reglas para su 
procesamiento. Los servicios web SOAP suelen utilizar el protocolo HTTP o SMTP (Simple Mail Transfer Protocol)
como transporte. Aunque SOAP es más pesado en términos de overhead debido a su formato XML, ofrece un enfoque 
más estructurado y riguroso.

## REST (Representational (XML o JSON) State Transfer)
REST es un estilo arquitectónico que utiliza los principios y restricciones HTTP. En lugar de utilizar un 
formato como XML para los mensajes, REST generalmente utiliza JSON (JavaScript Object Notation) debido a su 
ligereza y facilidad de lectura.

REST se basan en la idea de recursos identificables (URIs Uniform Resource Identifiers) y utilizan los métodos HTTP 
estándar (GET, POST, PUT, DELETE) para realizar operaciones sobre estos recursos y la transferencias de representaciones
de recursos en formatos como JSON o XML.

## WSDL
WSDL (Web Services Description Language) es un lenguaje de descripción de servicios web que se utiliza para describir 
la interfaz de un servicio web (principalmente utilizado por el protocolo SOAP). Proporciona una manera estándar de describir 
los servicios, incluyendo detalles sobre los métodos disponibles, los tipos de datos utilizados y la ubicación del servicio en la red.

Un archivo WSDL define la forma en que un servicio web debe ser llamado y qué tipo de datos puede esperar en respuesta. 
Al describir la interfaz del servicio de esta manera, se facilita que aplicaciones y servicios cliente se comuniquen 
con el servicio web de manera efectiva, ya que tienen una descripción precisa de cómo deben interactuar con él.

# API (Application Programming Interface)

Una API, por otro lado, es un termino mas amlpio que abarca cualquier interfaz que permita la interaccion entro dos o mas
programas. Puede referirse a interfaces  basadas en web (como los web services) o interfaces que se utilizan localmente
en un sistema.

Una API es un puente de comunicacion entre una o mas aplicaciones o piezas de software mediante un conjunto de definiciones
y protocolos. (como un intermediario que facilita la comunicación entre ellos)

Una API define cómo interactuar con un software específico, proporcionando una interfaz estandarizada para el 
acceso y la manipulación de sus funcionalidades o datos. Se utiliza comúnmente en el desarrollo de software para 
permitir que diferentes componentes o servicios se conecten y se comuniquen de manera eficiente.

Existen varios tipos de API, pero dos categorías principales son:

## API basada en web (Web API) 
Estas API utilizan protocolos web estándar, como HTTP, y son accesibles a través de la red, 
generalmente utilizando solicitudes HTTP. Las Web APIs a menudo entregan datos en formatos como JSON o XML. Un ejemplo 
común de una Web API es la API REST.

## API de biblioteca o de sistema
Estas API son conjuntos de funciones y procedimientos que permiten la interacción con componentes específicos de un sistema 
o biblioteca de software. Estas funciones pueden ser invocadas directamente en el código de un programa para lograr ciertos 
objetivos.

## Diferencias entre API y Web Services
Un servicio web es una forma especifica de implementar una API que utiliza tecnologias web para permitir la comunicacion
entre sistemas a traves de la red.

Entonces, mientras todos los Servicios Web son APIs, no todas las APIs son necesariamente Servicios Web.

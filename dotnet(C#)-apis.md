# Seguridad (Protocolos de autenticacion y autorizacion)

## OAuth (proporciona autorizacion)

OAuth es un protocolo de autorizacion potente y popular que se puede utilizar para conceder acceso a sitios web y aplicaciones sin dar contraseñas

OAuth proporciona flujos de autorización seguros para aplicaciones web y de escritorio, así como para dispositivos móviles

Un token de acceso OAuth le da acceso seguro a los recursos en un sitio web o aplicación habilitada para este protocolo.
Se utilizan para autenticar de forma segura al usuario y concederle acceso al recurso solicitado

## OAuth2 (Open Authorization)

Sustituyó a OAuth 1.0 en 2012 y ahora es el estándar de facto de la industria para la autorización en línea.
Se utiliza como una forma para que un usuario otorgue 
a los sitios web acceso a su información en otros sitios web o aplicaciones, pero sin darles las credenciales

OAuth 2.0 es más seguro que OAuth 1.0 y ofrece a los usuarios más control sobre cómo se comparten sus datos entre servicios.

OAuth 2.0 es un protocolo de autorización que permite a las aplicaciones obtener acceso limitado a cuentas de 
usuario en un servicio HTTP, como Facebook, Google y Twitter. Permite a los usuarios conceder acceso a su información
en otros sitios web sin proporcionar contraseñas u otra información sensible. Es la última versión de OAuth y proporciona
medidas de seguridad mejoradas, como tokens de acceso y flujos de autorización seguros.

Se utiliza ampliamente en la web y las aplicaciones móviles y proporciona a los usuarios una forma segura de 
acceder a la información de servicios de terceros sin tener que dar sus contraseñas

## OpenID

OpenID Connect está pensado para la autenticación y OAuth para la autorización. Este añade las siguientes funcionalidades que complementan a OAuth

    Un ID token que nos permite saber quién es el usuario.
    Un nuevo endpoint, UserInfo, que nos permite recuperar más información del usuario.
    Un conjunto de scopes estándar.
    Un conjunto de claims que nos permite obtener datos del sujeto.

OpenID Connect 1.0 es una «capa de identificación» desarrollada sobre el protocolo OAuth 2.0 que proporciona toda la 
información necesaria sobre usuarios o clientes.

Para entenderlo fácilmente, permite a los usuarios reutilizar sus cuentas, para así poder identificarse con 
su proveedor (Google, Facebook, etc …), evitando tener que crearse una cuenta nueva.

## Diferencias entre OpenID y OAuth

Sabemos que OpenID permite autenticarnos y demostrar quien realmente decimos ser (esto nos permite obtener diferentes datos del usuario).

En cambio OAuth ha sido creado para autorizar a sitios Web para que estos pueda acceder a diferentes funcionalidades o aplicaciones 
del usuario (como pueden ser datos privados de usuario, correo, cloud, etc …), evitando tener que autenticarnos de la manera tradicional.

## Auth0

Es una empresa que comercializa una plataforma de gestión de identidad con servicios de autenticación 
y autorización que implementa el protocolo OAuth2 (entre otros).

## RFC 6902 (Request for Comments)

Los RFC son documentos publicados por la IETF (Internet Engineering Task Force) y otras organizaciones
relacionadas que describen varios aspectos de protocolos, tecnologías, estándares y prácticas relacionadas con Internet.

Es el medio principal para documentar estándares y protocolos técnicos.

## Seguridad - Core Identity

Autenticacion(login) y Autorizacion (roles)
 
Es un sistema de identitad que nos permite llevar el control de usuarios, roles, manejo de contraseñas.
Gestiona usuarios, contraseñas, datos de perfil, roles, claims, tokens, confirmacion de email y mas.

Nos permite almacenar la informacion de nuestros usuarios y al mismo tiempo nos dara mecanismos para 
poder trabajar el acceso o la autorizacion a estos usuarios a nuestra app.
Cuando se imnplementa Identity se realiza una migracion de tablas para implementar la seguridad con Core Identity
Cuando se implementa Identity nos dara unas tablas en nuestra base de datos para guardar todo lo relacionado a nuestro 
sistema de usuarios y nos permitira acceder a un conjunto de funciones para el mantenimiento del sistema de usuarios

Identity nos provee nos da un conjunto de clases para realizar toda la funcionalidad de un sistema de usuarios tipico:
incluye :
    -Registro de un usuario: 
    servicio que permite ingresar un usuario es UserManager. Se le pasa una clase que identifica a un usuario de nuestro aplicacion.
    Esta es IdentityUser. Ejemplo UserManger<IdentityUser>

## Authentication

Registered authentication handlers: son usados para completar actiones realacionadas a la autenticacion
    Ejemplos de aciones relacionadas a la autenticacion son :
    - autenticar a un usuario y responder a un usuario no registrado 
    
Los "manipuladores de autenteicacion registrados" y sus confuguraciones son llamamos "Scheamas".

## Claims
Es un fragmento de informacion sobre el usuario, como puede ser nombre de usario, email, rol, localidad.
La forma mas sencilla de crear un claim es proporcionando un tipo y un valor. El valor del claim se representa 
con un valor string.

## Cors (intercambio de recursos de origen cruzado)  
El CORS se debe habilitar para permitir el intercambio de recurusos de origin cruzado.
Esto es debido a que hay una medida de seguridad por defecto que impide hacer peticiones http desde un navegador X a un endpoint de origen Y (dominio).
Se llama "Politica de seguridad del mismo origen"
Es una politica de seguridad de navegadores

# Patrones de diseño 

## CQRS (Command query responsibility segregation):

Separacion de responsabilidad de las lecturas y los comandos La idea de utilizar CQRS en ASP.NET Core (específicamente, una Web API) es delegar
la responsabilidad de procesar cada Request a un Handler y no al Controller (y aparte todo lo que vimos anteriormente arriba).
Promueve la segregacion de operaciones de lectura y escritura, mejorando el rendimiento y la escabilidad.
Es un patron de diseño que nos muestra como separar logica de nuestrasEl patrón CQRS es un patrón que no habíamos visto 
antes de la llegada de los microservicios ya que lo más normal era tener un monolito que lo hacía todo, 
incluido el conectarse a una única base de datos, pero en el mundo actual, las arquitecturas distribuidas 
estan empezando a coger popularidad.  aplicaciones 

## Patron Repository

Es un patron de diseño que aisla la capa de datos del resto de la app.
La capa de datos hace referencia a la parte de la APP que controla 
los datos y la logica de negocio de la APP.

## Inyeccion de dependencias

### Que es una dependencia?

Una dependencia es cuando se utiliza una clase adentro de otra. 
Cuando una clase A utiliza una clase B, se dice que la clase B es una dependencia de la clase A.

Nos permite realizar el desacoplamiento de nuestros componentes. 

Se implementa en el constructor de la clase (y se configura segun el patron en services).

## Ciclos de vida (inyeccion de dependencias)

`Transient:` Cuando un servicio es registrado como Transient quiere decir que se va a crear una instancia cada vez que se resuelve la dependencia.
Cada vez que utilizemos un servicio Transient este sera una nueva instancia. (cada vez que utilizemos este servicio se generara su propia instancia)    
Mayor gasto de memoria.

`Scoped:` Si registramos un servicio como Scoped este vivira por el tiempo de vida que exista en el scope. 
En ASP se crea un scope para cada request que recibe, normalmente del navegador.
Lo que quiere decir, que todos los servicios recibirán la misma instancia mientras dure el scope (la request):

```
Request 1:
[
    "Middleware: 9660-62-75-a1ae-976d9516",
    "Controller: 9660-62-75-a1ae-976d9516"
]

Request 2:
[
    "Middleware: 3c3f-5e-72-99a3-00e22744",
    "Controller: 3c3f-5e-72-99a3-00e22744"
]
```

`Singleton`: Cuando se registra un servicio como Singleton quiere decir que sera creado una unica vez mientras la app este funcionando.
La misma instancia será reutilizada e inyectada en todas las clases que la utilicen.

## UnitOfWork

Porporciona una capa de abtraccion por encima de las transacciones de bd.
Es un patron que se utiliza para asegurar varias operaciones a una base de datos,
en una sola entidad de trabajo, asegurango que todas estas operaciones se ejecutan o no se 
ejecuten. (se ejectua como una unica operacion, transaccion)
En resumen, lo importante es que apliquemos Unit Of Work para todas 
aquellas operaciones que necesitan alterar más de una tabla en la base de datos
 
Es importate mencionar que tambien existe Entity Framework que implementa de manera interna 
el patron Unit of work con el patron repositorio para facilitar el acceso a la base de datos

Proporciona una capa de abstraccion flexible para el acceso a los datos, que mejora la capacidad de mantenimiento y las 
pruebas.

Permite separar las preocupaciones y facilitar el mantenimiento y la escabilidad
del codigo.

Ventajas:

1.optimiza el manejo datos.

2.mejora la organizacion del codigo.

3.facilitar el mantenimiento.

4.simplifica las operaciones de consulta y persistencia.

## Mediator (MediatR, libreria)

El patrón mediador simplemente es la definición de un objeto que encapsula como otros objetos interactúan entre sí. En lugar
de tener dos o más objetos que dependen directamente de otros objetos, solo toman dependencia directa de un “mediador” 
y este se encarga de gestionar las interacciones entre objetos:

Es un Patron de Diseño de comportamiento que permite reducir las dependencias entre objetos. El Patron restringe las
comunicaciones directas entre los objetos, forzandolos a colaborar unicamente a traves de un objeto mediador.

EL Patron Mediador evita la comunicaicon directa entre componentes, forzando implementacion de un objeto mediador para la comunicacion. 
Como resultado, los componentes dependen unicamente de una sola clase mediadora, en lugar de estar acoplados directamente.

Caracteristicas:

`Permite desacoplar logica de un componente`
`Reduce desacoplamiento entre objetos`

### Imnplementacion:

MediatR tiene dos tipos de mensajes que envía:

 -Request/response messages: Enviados a un único controlador (handler).
 -Notification messages: Enviado a múltiples controladores (handlers).

Mediadores: En MediatR, un mediador es el componente central que maneja la comunicación entre diferentes partes de tu aplicación 
(ejemplo mediator.Send(request)).

Mensajes: Los mensaje son objetos que representan solicitudes (request) que deseas transmitir entre las partes de tu aplicacion. 

Handlers: Los handlers son clases que contienen la logica para manejar el tipo especifico de mensaje (solicitud).

```
// Definir una solicitud (mensaje) 
public class MyRequest : IRequest<string>
{
    public string Data { get; set; }
}

// MyRequest: una clase que representa una solicitud. 
// IRequest<string> : Indica que esta solicitud espera como resultado de tipo string despues de ser manejada.

// IRequest<TResponse>
// Es una interfaz generica que se utiliza para representar una soliciud que puede ser manejado por un handler.
// TResponse es el tipo de dato que se espera como resultado de la solicitud.
```

### Flujo del mediatR

Cuando envias una solicitud de este tipo al mediador (ej: mediador.Send(request)), buscara un handler que pueda procesar la solicitud
`MyRequest` y devolvera un resultado de tipo string. Los handlers que pueden manejar este tipo de solicitud deben implementar
la interfaz `IRequestHandler<TRequest, TResponse>`, donde `TRequest` es el tipo de solicitud y `TResponse` es el tipo de resultado
esperado.

Ejemplo de un Handler que maneja una solicitud `MyRequest`:

```
public class MyRequestHandler : IRequestHandler<MyRequest, string>
{
    public Task<string> Handle(MyRequest request, CancellationToken cancellationToken)
    {
        // Realizar algún trabajo con la solicitud y devolver un resultado
        return Task.FromResult($"Procesado: {request.Data}");
    }
}
    
``` 

`MyRequest` Es el tipo de solicitud que se va a manejar
`string` Es el tipo de dato que se espera como resultado de la manipulación de esa solicitud. 

Este manejador implementa la interfaz `IRequestHandler<MyRequest, string>` y define la lógica para procesar la solicitud MyRequest. 
En este caso, devuelve una cadena que indica que la solicitud ha sido procesada.
Cuando se envía una solicitud MyRequest al mediador, MediatR identificará este manejador y ejecutará el método Handle del mismo, 
obteniendo así el resultado esperado de tipo string.

# ASP.NET

## Validaciones
Validacion con anotaciones:
Validacion con Fluent:
Middlewares con validaciones:

## Logger
Los logs (registros) en programacion se refieren  a la practica de registrar informacion relevante durante la ejecucion de
un programa.
Con loggers podemos procesar mendajes en nuestra app y colorar estos mensajes en algun lugar (ej: consola, db)
 
## Model binders
Se encarga de mapear los datos enviados por el cliente, como datos JSON a los modelos o clases definidas
por la app.
Cuando un cliente envia una solicitud HTTP a un controlador de asp net core, el model binder se activa y se encarga de 
extraer los datos del cuepo de la solicitud (por ejemplo, JSON o datos de un form) y los parametros de una URL. Luego 
intenta asignar esos datos a las propiedades del modelo o a los parametros de accion del controlador.

Algunos model binders son: 
FromnBody (extrae los datos del cuerpo de la solicitud) 
FromQuery (obtiene los datos de la URL)
Tambien es posible crear crear model binders personalizados.

Tecnicamente frombody es un atributo para indicar que el valor de un parametro de accion en un controlador debe ser 
vinculado desde el cuerpo de la solicitud.

## Dapper
Libreria para consumir procedimientos almacenados desde sql server (alternativa a entity framework)

## Startup File
## Program:
Es donde se registran y se configurar el pipeline de peticion de asp net core.

## Builder: 
Es un objeto de la de tipo IWebHostBuilder, se utiliza para construir y configurar nuestra app (WebHost 
clase que administra y aloja nuestra app asp.net core) 
Adentro del builder registramos los sevicios que la app nececite    

## Services
Se refiere a los servicios que se agrega al contenedor de inyeccion de dependencias durante la configuracion 
de la app.

El contenedor de servicios es una caracteristica de asp net que permite la inyeccion de dependencias.

Registrar servicio, significa poner a disposicion un servicio para y utilizar en nuestra app mediante un constructor
(sin inyeccion (se agrega al contener de inyeccion de dependencias), la inyeccion ocurre cuando se genera en el constructor de la clase)

    -   Tipos de servicios, se puede implementar el algun patron de inyeccion de dependencias (transient, scoped, singleton)

## Objeto app
Las operaciones que se van a ejecutar por cada peticion en una app de net core

## Logger 
Un logger es usado para crear mensajes de error personalizados, lo bueno de hacer logs es que estos pueden registrarse 
a nivel del mismo sistema operativo/ container que esta ejecutando tu app. Si estas en Windows a traves del Event Log.

## Middlewares (software intermedio)
Un middleware (funcion) es un componente que se ejecuta en cada solicitud de asp.net app
Son funciones que se ejecutan en cada solicitud de asp.net
Un middleware esta en medio, entre la peticion, el servidor y la respuesta
 
El middleware se encuentra entre la solicitud y el objetivo (antes de la respuesta http, antes que un servidor haga el envio la respuesta) 
y puede modificar directamente la respuesta

FLujo de comunicacion basico:
Interaccion HTTP se compone de: solicitud (navegador, api) -> respuesta

SOLICITUD (solicitantes: Navegador web, api) -> OBJETIVO (servidor web, otra api) -> RESPUESTA  
Los Middlewares se encuentran entre solicitante y el objetivo
caracteristicas: pueden modificar la respuesta, modificar el comportamiento del codigo que genera la respuesta

ASP.NET implementa un Pipeline (canalizacion o secuencia de acciones o comandos) que consta de una serie de clases de middleware en la clase program.
Esta secuencia se ejecucion varia segun el middleware utilizado, algunos ejemplos son 
 run() = ese middleware siempre será terminal el último middleware ejecutado antes de que se devuelva la respuesta
 use() = la mayoría de las veces querremos agregar middleware a la canalización con Use() 
 map() = averiguar mas 

En resumen el middleware son módulos de código o clases que forman una canalización (pipeline)
Esa canalización procesa las solicitudes entrantes y las respuestas salientes.  
En el archivo Program.cs, podemos colocar el middleware en un orden específico, que luego ejecutará las solicitudes en ese orden y las respuestas en orden inverso.

## Controller base:
Es una clase base para definir controlodadores que manejan solicitudes HTTP y generan respuestas.
Esta estrechamente relacionada  con la creacion de respuestas a las solicitudes HTTP.
Controller base contiene propiedades y metodos que son esenciales para el manejo de solicitudes y la generacion de respuestas.
Tambien tiene la capacidad de crear y retornar diferentes tipos de ActionResult.

## Action Result
Es un tipo de resultado que se utiliza para representar el resultado de una accion de controlador
Es un aclase abstracta que representa el resultado de una accion en un controlador.
Usar action result permite que el controlador sea mas flexible, puede manejar diferentes escenarios de manera mas generalizada.

## Controlador
Son los encargados de manejar las solicitudes entrantes y devolver una respuesta.

## Filtros:
Son componentes para agregar logica adicional y reutilizable antes o despues de las acciones de un controlador. 
Se ejecuta antes o despues de una accion de controladores o en otras etapas de procesamiento de una solicitud HTTP.
Son componentes adiconales que agregar funcionalidades extra a nivel de accion o controlador de una forma reutilizable 
y desacoplada.

Son comnponentes que se utilizan para interceptar y manipular las solicitudes  y respuestas http(normalemente se aplican a los controladores). Estos filtros se aplican al nivel del controlador o a nivel de accion,
y se ejecutan en puntos especificos del ciclo de vida de una solicitud., permitiendo realizar tareas como validacion, autenticacion, autorizacion, registro, cache, manipulacion de exepciones, 
entre otros.
Son clases que implementan una mas interfaces de filtros como por ejemplo IActionResulter, IResultFilter, IExepcionFIlter, IAuthorizationFilter
Pueden ser aplicados en controladores, metodos de acciones, o globalmente en la app.

    Tipos de filtros:
        -Action FIlters: se aplican acciones especificas y permiten ejecutar codigo antes y despues de la ejecucion de la accion.
        -Exception Filters: Capturan y manejan las exepciones que se producen durante la ejecucion de la accion.
        -Result Filters: Manipulan el resultado que se enviara al cliente despues de que se ha ejecutado una accion.

## Atributos 
Los atributos son una característica fundamental de .NET que permiten agregar información adicional a 
los tipos, miembros (métodos, propiedades, etc.) u otros elementos del código
Son clases que se aplican a elementos de codigo, como clases, metodos o propiedades para proporcionar informacion adicional o comportamiento especial.
Son clases que deriban de "Attribute" class, pueden ser usados para decorar controladores, action method o propiedades con metadata adicional.

Normalmente los atributos se utilizan en combinacion con los filtros para definir el comportamiento de los filtros.

## Entity Framework Core
El Contexto de Datos en Entity Framework Core
Context: contexto a la base de datos

## Automapper(libreria) = _mapper
Asignar valores de un objeto a otro (Ejmplo Model a los DTO)

## Paquetes Nuget 
Es un administrador de paquetes de .NET

## Capa de abstracción  
La abstraccion es la ocultación de la complejidad intrinseca de una aplicacion al 
exterior. La abstraccion consiste en ocultar la complejidad que algo puede tener por dentro,
ofreciendonos funciones de alto nivel, por lo general sencillas de usar, que pueden ser 
usadas para interactuar con la aplicacion sin tener conocimiento de lo que hay por dentro.
    
# C#

## Interfaces

IEnumerable, ICollection e IList son interfaces en .NET, las cuales son utilizadas frecuentemente. IEnumerable 
es la base de las interfaces ICollection e IList (y muchas otras).

Se encuentran en el namespace System.Colecctions 
Se encuentran en el namespace System.Colecctions.Generics 

IEnumerable > IColecction > IList


### IEnumerable

Es una interfaz que permite ejecutar consultas LINQ.

`PERMITE` recorrer mediante itereacion `FOREACH` cada uno de los elementos y ejecutar filtros de busqueda con la clausula `WHERE`.

`NO PERMITE` operaciones de edicion sobre los elementos (agregar, eliminar, actualizar, etc)
`NO PERMITE` recuentos de dichos elementos, si quieres saber la cantidad total debes obtenerla manualmente mediante un foreach.

**Cuando usarla?** Lo unico que quieres iterar sobre los elementos de una coleccion. Solo necesita acceso de solo lectura a esa coleccion.

### ICollection

Deriva directamente de IEnumerable. 

`PERMITE` agregar, editar, eliminar y contar los elementos de una coleccion (.Count).

**Cuando usarla?** Cuando es necesario modificar la coleccion o se necesita su tamaño. 

### IList

Deriva directamente de IColecction

Reune todos las caracteristicas de IEnumerable y IColecction, agregando la funcionalidad de indexacion, esto significa que la posicion en la 
que se almacenan los datos es importante. Debera usarse cuando se quiera tener una coleccion ordenada o acceder a posiciones especificas.

**Cuando usarla?** Cuando es necesario modfiicar la coleccion y se nececita ordenamiento y/o posicionamiento de los elementos de la coleccion. 

*SI NO ESTAS SEGURO SOBRE QUE COLECCION UTILIZAR ILIST SIEMPRE ES LA "VIEJA CONFIABLE".

## Colecciones

Son clases de C# que representan estructuras de datos
Las colecciones son estructuras de datos (tamaño dinicamico y no fijo como los arrays) que permiten almacenar y manipular un conjunto de elementos o datos relacionados.
Agregar, eliminar, buscar e insertar datos en la coleccion, son algunos ejemplos de manipulacion de datos.

### Caracteristicas

- Son clases que pertenecen al namespace System.Collection.Generic (y no generica en System.Collections)
- La mayoria de las clases de coleccion implementan las mismas interfaces.
- Estas colecciones implementan interfaces como IEnumerable, IReadOnlyColecction, ICollection por nombrar algunas. 
- Cada clase de coleccion definida implementa una caracteristica unica.

###  Algunas operaciones basicas que son posibles en cualquier coleccion

- Buscar objetos especificos en cualquier coleccion.
- Agregar o remover objetos dinamicamente en la coleccion.
- Iterar la coleccion. 

### Porque una coleccion  ? 

- El tamaño de un array es fijo y no puede ser incrementado dinamicamente.
- En escenarios actuales de desarrollo se nececita procesar y agregar dinamicamente el mismo tipo de objetos y el tamaño de de los elementos debe crecer o reducirce en concecuencia.
- Ademas la forma en que se deben almacenar estos objetos puede ser diferente, puede ser de forma secuencial, no secuencial, ordenados, etc.

### Tipos de colecciones en C#
- List<T>
- Dictionary<T>
- SortedList
- Stack<T> = FIFO (first-in, first-out) 
- Queue<T>

## Linq
Lenguaje de consulta de .net. Generalmente utilizado para  consultas a las bases de datos

## readonly
Valor puede cambiar en el constructor 
Se utiliza para la inyeccion de dependencias

## Delegados
Es un puntero de una funcion

## Predicado  
Es un delegado que devuelve un booleano

## Expresiones lambda
Funciones anonimas.
Expresiones similar a un callback de JS.
Es una funcion que se pasa como argumento a otra funcion y se ejecuta cuando se cumple una condición
especifica (generalmente ejecuta después de que la función principal ha completado su tarea). 
Por ejemplo la funcion seTimeout recibe un callback que se ejecutara segun los el tiempo
señalado en la funcion


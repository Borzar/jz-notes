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

## Asincronia
Utilizar solo cuando realizamos peticiones a servicios externos. 
Por ejemplo una bd, api o servidores. Cualquier recurso externo a nuestra app.


# Patrones de diseño: 

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
La capa de datos hace referencia a la parte de la APP, que controla 
los datos y la logica de negocio de la APP.


# ASP.NET

## Enumerable:
Retorna una coleccion

## validaciones
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
 
## Program:
Es donde se registran y se configurar el pipeline de peticion de asp net core.

## Builder: 
Es un objeto de la de tipo IWebHostBuilder, se utiliza para construir y configurar nuestra app (WebHost 
clase que administra y aloja nuestra app asp.net core) 
Adentro del builder registramos los sevicios que la app nececite    

## Services
Se refiere a los servicios que se agrega al contenedor de inyeccion de dependencias durante la configuracion 
de la app.
El contenedor de servicios es una caracteristica de asp net que permite la inyeccion de dependencias

Registrar servicio, significa poner a disposicion un servicio para y utilizar en nuestra app mediante un constructor
(sin inyeccion (se agrega al contener de inyeccion de dependencias), la inyeccion ocurre cuando se genera en el constructor de la clase)

    -   Tipos de servicios, se puede implementar el algun patron de inyeccion de dependencias (transient, scoped, singleton)

## Ciclos de vida o Patrones(inyeccion de dependencias)
Transient = crear un nuevo objeto por cada peticion (transitorio, ej: contador se reinicia por cada peticion)
Scoped = genera 1 objeto por ambiente (pero bajo 1 solo contexto)
Singleton = genera 1 objeto para toda la app (contador aumenta por cada peticion)

## Inyeccion de dependencias
Nos permite realizar el desacoplamiento de nuestros componentes (clase adentro o afuera del proyecto)
Se implementa en el constructor de la clase (y se configura segun el patron en services)

## Objeto app
Las operaciones que se van a ejecutar por cada peticion en una app de net core

## Mediator (MediatR, libreria):
Mediador Patter es una libreria que injecta el objeto para acceder a la db
El patrón mediador simplemente es la definición de un objeto que encapsula como otros objetos interactúan entre sí. En lugar
de tener dos o más objetos que dependen directamente de otros objetos, solo toman dependencia directa de un “mediador” 
y este se encarga de gestionar las interacciones entre objetos:

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

## Entity Framework Core:
El Contexto de Datos en Entity Framework Core
Context: contexto a la base de datos

## Automapper(libreria) = _mapper
Asignar valores de un objeto a otro (Ejmplo Model a los DTO)

## Inyección de Dependencias y Acoplamiento 
Una dependencia es cuando se utiliza una clase adentro de otra. 
Cuando una clase A utiliza una clase B, se dice
que la clase B es una dependencia de la clase A.

## Paquetes Nuget 
Es un administrador de paquetes de .NET

## Capa de abstracción  
La abstraccion es la ocultación de la complejidad intrinseca de una aplicacion al 
exterior. La abstraccion consiste en ocultar la complejidad que algo puede tener por dentro,
ofreciendonos funciones de alto nivel, por lo general sencillas de usar, que pueden ser 
usadas para interactuar con la aplicacion sin tener conocimiento de lo que hay por dentro.
    
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
2.mejora la organizacion del codigo
3.facilitar el mantenimiento
4.simplifica las operaciones de consulta y persistencia.

----------------C#--------------------------------

## Linq
Lenguaje de consulta de .net para realizar consultas a las bases de datos

## readonly
Valor puede cambiar en el constructor 
Se utiliza para la inyeccion de dependencias

## Delegados ]
Es un puntero de una funcion

## Predicado  
Es un delegado que devuelve un booleano

## Expresiones lambda
Expresiones similar a un callback de JS.
Es una funcion que se pasa como argumento a otra funcion y se ejecuta cuando se cumple una condición
especifica (generalmente ejecuta después de que la función principal ha completado su tarea). 
Por ejemplo la funcion seTimeout recibe un callback que se ejecutara segun los el tiempo
señalado en la funcion


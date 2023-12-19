# Caching (Almacenamiento en cache)

El almacenamiento en cache es una tecnica para almacenar datos o informacion de uso frecuente en memoria local (RAM),
durante un periodo de tiempo determinado.

Por ejemplo si hablamos de la CPU, esta tiene su propio cache (memoria local o interna)

Entonces, la siguiente vez, cuando el cliente solicita la misma informacion, en vez de consultar la informacion
a la base de datos, esta informacion sera dada desde la memoria local.

La gran ventaja del almacenamiento cache es que mejora el rendimiento al reducir la carga de procesamineto. 

## Tipos de caches

### Caché de bases de datos

En aplicaciones web que utilizan bases de datos, se puede implementar la cache para almacenar en memoria resultados de 
consultas frecuentes. Esto reduce la carga en la base de datos y acelera la recuperar de datos.

Aquí hay algunas ubicaciones comunes donde se puede almacenar el caché de una base de datos:

Memoria RAM: La caché de una base de datos a menudo se almacena en la memoria RAM del sistema. La RAM es más rápida 
que otros tipos de almacenamiento, lo que permite un acceso rápido a los datos almacenados en caché.

Cache distribuidas: En sistemas distribuidos, la caché puede distribuirse entre varios nodos o servidores para 
mejorar el rendimiento y la escalabilidad. Cada nodo puede tener su propia caché local.

Disco duro o SSD

### Cache de hardware (CPU)

Se encuentra a nivel del procesador y almacena datos e intrucciones frecuentemente utilizados para evitar acceder 
a la memoria principal, que es mas lenta.

el caché de la CPU se refiere a una memoria pequeña y ultrarrápida incorporada en el procesador (o cerca de él) 
que almacena copias de datos y/o instrucciones utilizadas con frecuencia para reducir los tiempos de acceso a 
la memoria principal. Este tipo de caché está diseñado para mejorar el rendimiento de la CPU al minimizar los 
tiempos de espera para la recuperación de datos.

### Cache de software

Implementado a nivel de aplicacion o del sistema operativo para almacenar resultados de operaciones costosas o datos
utilizados con frecuencia. Puede incluir cache en disco, cache de base de datos, entre otros.

Cuando se menciona que algunas aplicaciones implementan su propio mecanismo de caché a nivel de aplicación, generalmente 
se refiere a que la aplicación reserva parte de la memoria del sistema (memoria RAM) para almacenar temporalmente datos 
que se acceden con frecuencia. Esta memoria en la que se almacena el caché a nivel de aplicación puede ser conocida 
como "memoria caché de la aplicación" o simplemente "memoria caché".

Además de la memoria RAM, algunas aplicaciones también pueden utilizar archivos temporales en el sistema de archivos 
del dispositivo para almacenar datos en caché. Estos archivos temporales actúan como almacenamiento persistente que 
puede retener el caché incluso después de que la aplicación se cierre y se reinicie.

En resumen, el caché a nivel de aplicación puede almacenarse en la memoria RAM de la máquina donde se ejecuta la 
aplicación, así como en archivos temporales en el sistema de archivos. La elección entre estas opciones depende de los requisitos y el diseño específico de la aplicación.

### Cache de red

Se utiliza para almacenar copias locales de datos obtenidos a traves de red, reduciendo asi la latencia y el
trafico de red.

### Cache Navegador

Los navegadores web almacenan en cache recursos como images, hojas de estilo css, scripts de JS y otras partes de 
una pagina web.

Cuando un usuario vuelve a visitar una pagina, el navegador puede cargar estos recursos desde la cache local en lugar
de descargarlos nuevamente del servidor, lo que acelera el tiempo de carga.

Cuando visitas una página web, el navegador descarga y almacena localmente varios tipos de recursos, como imágenes, 
hojas de estilo, scripts, fuentes y otros archivos. Estos recursos se almacenan en una ubicación temporal llamada 
"caché del navegador".

## Client Side Caching (Almacenamiento en caché del lado del cliente)

El almacenamineto en cache del lado del cliente es el almacenamiento de datos de la red en un caché local para su
reutilizacion futura.

Despues de que una palicacion recupera datos de la red, almacena ese recurso en una memoria cache local. Una vez que 
un recurso se ha almacenado en cache, el navegador utiliza el cache en futuras solicitudes de ese recurso para mejorar el
rendimiento.

## Server-side caching (Almacenamiento en caché del lado del servidor)

Los servidores web tambien pueden implementar tecnicas de almacenamiento en cache. Por ejemplo, se pueden almacenar en cache
las respuestas generadas dinamicamente para solicitudes frecuentes, evitando asi tener que volver a generar la misma
respuesta cada vez que se realiza la misma solicitud.

El almacenamiento en cache del lado del servidor almacena temporalmente archivos y datos web en el servidor
de origen para reutilizarlos mas adelante.

Cuando el usuario solicita la pagina web por primera vez, el sitio web pasa por  el proceso normal de recuperacion de datos
del servidor y genera o construye la pagina web del sitio web. UNa vez realizada la solicitud y enviada la respuesta, 
el servidor copia la pagina web y la almacena como cache.

La proxima vez que el usuario vuelva a visitar el sitio web, carga la copia ya guardada o en cache de la pagina web,
lo que la hace mas rapida.

## CDN (Content Delivery Network)

Las CDN son redes de servidores distribuidos globalmente que almacenan en cache contenido estatido (como images, videos y
archivos de estilo) en ubicaciones cercanas a los usuarios. Esto reduce la lantencia al entregar el contenido desde
servidores mas cercanos en lugar de los servidores originales del sitio web.

¿Qué es una CDN? Una red de entrega de contenido (CDN) es una red de servidores interconectados que acelera la carga de 
las páginas web para las aplicaciones que tienen un uso intensivo de datos. CDN puede significar red de entrega de 
contenido o red de distribución de contenido.


# Redis

Es un sistema de almacenamiento en cache de datos de codigo abierto y una base de
datos en memoria.

Redis == "Remote Dictionary Server"

## Como funciona el cache de redis

Redis es una base de datos en memoria, lo que significa que almacena datos en la RAM (memoria principal del sistema) 
en lugar de en un disco. El término "caché" en Redis se refiere a la capacidad de almacenar en memoria datos 
que se acceden con frecuencia, proporcionando así tiempos de acceso rápidos y reduciendo la necesidad de acceder
a fuentes de datos más lentas, como una base de datos en disco.

## Almacenamiento en memoria

Almacena datos en memoria principal en lugar de un disco, lo que permite un acceso rápido y eficiente a los datos  
Esto lo convierte en una excelente opción para casos de uso que requieren alta velocidad y baja latencia.

## Estructuras de datos

Redis admite una variedad de estructuras de datos, como cadenas, listas, conjuntos, mapas hash, conjuntos ordenados, 
bitmaps, entre otros. Estas estructuras permiten a los desarrolladores realizar operaciones complejas de manera eficiente.

## Persistencia opcional

Aunque Redis es conocido como una base de datos en memoria, también admite persistencia opcional en disco. 
Esto significa que los datos pueden guardarse en disco para su recuperación en caso de reinicio o fallo del sistema

## Claves con tiempo de vida

Puedes asignar un tiempo de vida a una clave, después del cual la clave y su valor asociado se eliminarán 
automáticamente. Esto es útil para implementar estrategias de almacenamiento en caché con expiración automática.

## Protocolo de red simple

Redis utiliza un protocolo de red simple basado en texto, lo que facilita la implementación de 
clientes en una variedad de lenguajes de programación.


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

Autenticacion(login) y Autorizacion (roles).
 
Nos permite almacenar la informacion de nuestros usuarios y la autorizacion a estos usuarios en nuestra app.

Es un sistema de identitad que nos permite llevar el control de usuarios, roles, contraseñas, claims, tokens, confirmacion de email y mas.

Soporta proveedores externos como Facebook, Google, Twitter, etc.

Identity Core te da la estructura (tablas) para que mediante comandos (mediante EF) puedas crear tablas y la logica de seguridad de tu aplicacion. 

Flujo:

1. Cliente (React) envia Usuario y Contraseña. 

2. Idendity reconoce esta data mediante un controller y valida que estos datos existan en la base de datos.

3. Si estos existen y son validos, se generara un token (JWT) con la informacion relevante al usuario (Claims).

4. El JWT se envia al cliente. 

5. El cliente almancena ese JWT localmente (localstorage, cookie, variable local del browser).

6. Teniendo ese token almacenado, puede enviar ese token como referencia al identity core para acceso  a otros recursos.
7. Ejemplo: Si queremos obtener una lista de tareas, lo que tendria que hacer el Cliente (React) es adjuntar en la request el token -> Idendity
valida que ese token sea el correcto  y le da acceso a todo el servicio para obtener la data.

Identity nos provee nos da un conjunto de clases para realizar la funcionalidad de un sistema de usuarios tipico:

Incluye :

    - Registro de un usuario: UserManager<T>
    - Login: SignInManager<T>
    - Roles: RoleManager<IdentityRole>

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

Cuando hablamos de CORS (Cross-Origin Resource Sharing en inglés, que en español sería algo así como intercambio de recursos de origen cruzado) nos referimos 
a un mecanismo de seguridad que aplican los navegadores cuando estamos haciendo una petición a un recurso que está alojado en otro origen. 
Si el recurso está en otro origen, el navegador automáticamente comprobará las cabeceras HTTP buscando una autorización expresa por parte del servidor.

Por repasar, te recuerdo que el concepto origen es la suma de protocolo, dominio y puerto. Es decir, CORS aplica cuando el origen es diferente, 
por lo tanto se comprueba que sea el mismo protocolo (http o https), el mismo dominio (sin incluir subdominios) y el mismo puerto (80, 443, 8080, etc.). 
Si el origen que hace la petición no coincide con el origen del recurso entra CORS en juego.

Por ejemplo, imagina que estás diseñando una aplicación que está ubicada en miapp.es y las peticiones de datos las realiza a una API, 
situada en api.miapp.es. En cuanto vayas a hacer una consulta con el método fetch de JS al dominio 
(o subdominio donde en este caso tienes la API) te aparecerá el siguiente error:


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
Se refiere a los servicios que se agrega al contenedor de inyeccion de dependencias.  

El contenedor de servicios es una caracteristica de asp net que permite la inyeccion de dependencias.

Registrar servicio, significa poner a disposicion un servicio para y utilizar en nuestra app mediante un constructor.
La inyeccion ocurre cuando se genera en el constructor de la clase)

    -   Tipos de servicios, se puede implementar el algun patron de inyeccion de dependencias (transient, scoped, singleton)

## IConfiguration (Configuration es una instancia de IConfiguration)

Se utiliza para acceder a las configuracion de la aplicacion.

IConfiguration se utliza comunmente para acceder a valores definidos en el archivo appsettings.json y en otros origines de configuracion.

    - settings files, such as appsettings.json
    - Environment variables
    - Azure Key Vault
    - Azure App Configuration
    - Command-line arguments
    - Custom providers, installed or created
    - Directory files
    - In-memory .NET objects

## IOptions y Configure

Configure es  utilizado para vincular secciones especificas de la configuracion a clases que representan esas opciones.

Para acceder a esas opciones  las clases implementan IOptions<T>.

IOptions es una interfaz que se utiliza para acceder a las opciones de configuracion de tu app de una manera desacoplada (por intermedio de clases).

Permite pruebas unitarias mediante la inyeccion de opciones.

Permite tener difererentes configuraciones para diferentes entornos(Desarrollo y produccion).

1. Clase MyOptions:

```
public class MyOptions
{
    public string Option1 { get; set; }
    public int Option2 { get; set; }
}
```

2. Configuración en el archivo appsettings.json:

```
{
  "MyOptions": {
    "Option1": "Value1",
    "Option2": 42
  }
}
```

3. Registro de las opciones en el contenedor de dependencias: 

```
services.Configure<MyOptions>(Configuration.GetSection("MyOptions"));
```

4. Inyección de dependencias y uso:

```
public class MyService
{
    private readonly MyOptions _myOptions;

    public MyService(IOptions<MyOptions> options)
    {
        _myOptions = options.Value;
    }

    public void DoSomething()
    {
        // Acceder a las opciones
        var option1Value = _myOptions.Option1;
        var option2Value = _myOptions.Option2;
    }
}
```

## Patron Options


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

## Automapper

*_mapper*
Asignar valores de un objeto a otro (Ejmplo Model a los DTO)

## Paquetes Nuget 
Es un administrador de paquetes de .NET

## Capa de abstracción  
La abstraccion es la ocultación de la complejidad intrinseca de una aplicacion al 
exterior. La abstraccion consiste en ocultar la complejidad que algo puede tener por dentro,
ofreciendonos funciones de alto nivel, por lo general sencillas de usar, que pueden ser 
usadas para interactuar con la aplicacion sin tener conocimiento de lo que hay por dentro.
    
# C#

## Carpetas OBJ y BIN
Son directorios generados durante el proceso de compilación de un proyecto.

La carpeta /obj es utilizada por compilador para guardar archivos temporales que necesita generar como paso previo 
a los archivos finales que genera en la carpeta \bin cuando finaliza la compilación.

La carpeta /obj se utiliza para almacenar archivos temporales y objetos intermedios generados durante el proceso de compilación. 
Estos archivos son necesarios para producir los archivos binarios finales en la carpeta bin.

La carpeta bin contiene archivos binarios, que son el código ejecutable real para su aplicación o biblioteca.

Cada una de estas carpetas se subdivide en carpetas Debug(depurar) y Release(lanzar), que simplemente corresponden a las configuraciones de compilación del proyecto.

## Diferencias entre un array y colecciones
Los arrays y colecciones son estructuras de datos en programacion que se utilizan para almacenar y manipular conjuntos
de elementos, Pero hay algunas diferencias:

- Tipos de Datos: 
Los Arrays son estructuras de datos que almacenan elementos del mismo tipo en una secuencia contigua en memoria.
Todos los elementos deben ser del mismo tipo.

Las colecciones, proporcionadad por el espacio de nombres System.Collections y System.Collections.Generic, pueden almacenar
elementos de diferentes tipos y pueden ser mas flexibles en terminos de manipulacion de datos.

-Tamaño: Los arrays tienen un tamaño fijo que se establece al crearlos y no puede cambiar dinamicamente. 

Las colecciones como las Listas, pueden cambiar de tamaño dinamicamente.


## Interfaces

EnIEnumerable, ICollection e IList son interfaces en .NET, las cuales son utilizadas frecuentemente. IEnumerable 
es la base de las interfaces ICollection e IList (y muchas otras).

Se encuentran en el namespace System.Colecctions 
Se encuentran en el namespace System.Colecctions.Generics 

IEnumerable > IColecction > IList


### IEnumerable

Es una interfaz que permite ejecutar consultas LINQ.
Es una interfaz que se utiliza para representar una secuencia de elementos que se pueden iterar.

Por ejemplo el metodo ToList() esta disponible  en el contexto de las colecciones que implementan la interfaz IEnumerabl<T>.

Estre metodo se encuentra en la clase System.Linq.Enumerable y proporciona una forma conveniente de convertir una secuencia
(IEnumerable) en una lista (List<T>).

(explicacion larga)

IEnumerable es una interfaz en el framework .NET que define un método llamado GetEnumerator(). Este método devuelve un objeto que 
implementa la interfaz IEnumerator. La interfaz IEnumerator a su vez proporciona métodos como MoveNext() y Current para realizar 
la iteración a través de una colección de elementos, uno a la vez.

Por ejemplo un Array ya implementa la interfaz IEnumerable, por lo que podemos iterar mediante un foreach.
En terminos simples IEnumerable es una interfaz diseñada para facilitar la iteracion a traves de una secuencia de elementos, pero 
no especifican como se alamacenan o estructuran esos elementos. Pueden ser implementadas por diversas estructuras de datos, 
como arrays, listas, conjuntos y otros tipos de colecciones.

`PERMITE` recorrer mediante itereacion `FOREACH` cada uno de los elementos y ejecutar filtros de busqueda con la clausula `WHERE`.

`NO PERMITE` operaciones de edicion sobre los elementos (agregar, eliminar, actualizar, etc)
`NO PERMITE` recuentos de dichos elementos, si quieres saber la cantidad total debes obtenerla manualmente mediante un foreach.

`CUANDO USAR` Lo unico que quieres iterar sobre los elementos de una coleccion. Solo necesita acceso de solo lectura a esa coleccion.

### ICollection

Deriva directamente de IEnumerable. 

`PERMITE` agregar, editar, eliminar y contar los elementos de una coleccion (.Count).

`CUANDO USAR` Cuando es necesario modificar la coleccion o se necesita su tamaño. 

### IList

Deriva directamente de IColecction

Reune todos las caracteristicas de IEnumerable y IColecction, 

`PERMITE` Agrega la funcionalidad de indexacion, esto significa que la posicion en la 
que se almacenan los datos es importante. Debera usarse cuando se quiera tener una coleccion ordenada o acceder a posiciones especificas.

`CUANDO USAR` Cuando es necesario modfiicar la coleccion y se nececita ordenamiento y/o posicionamiento de los elementos de la coleccion. 

***Si no estas seguro sobre que coleccion utilizar IList siempre es la "vieja confiable.***

### IList vs List

Para entender la diferencia primero tenemos que entender la diferencia entre clases y interfaces.
IList es una interface y List es una clase en concreta que utiliza IList.

Siempre tenemos que codificar en terminos de interfaces, ya que proporciona un codigo mas generico. 
Solo debemos tener presente y asegurarmos que clase extienda de IList. 

Para que cada vez que nuestro tipo o clase cambie en el futuro podamos
adaptarnos a cualquier tipo que implemente la interfaz mencionada.

Sin embargo si utilizamos las clase List tenemos a disposicion muchos metodos que estan presenten especificamente en la clase List. 
Por ejemplo el metodo Sort().

```
    List<string> myList = new List<string>();

    Display(myList);

    GenericDisplay(myList);


    private static void GenericDisplay(IList<string> myList) // Acepta cualquier clase que implemente IList
    {
        foreach (var item in myList)
        {
            Console.WriteLine(item);
        }
    }

    private static void Display(List<string> myList)
    {
        foreach (var item in myList)o
        {
            Console.WriteLine(item);
        }
    }
```

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

## Conexion  base de datos MySqL con C#
Comando.Parameters.Add("?var")  -> Se utiliza en consultas SQL con parametros y para evitar sql inyection. Si hay consultas o precedimientos con parametros, 
los parametros son agregados mediante .add e indicar los parametros de la funcion.

comando.ExecuteNonQuery()       -> Para ejecutar una consulta contra la base de datos (INSERT, UPDATE, DELETE).

comando.ExectuteReader()        -> Se utiliza para leer la base de datos. Para retornar los valores de la base de datos(GET).


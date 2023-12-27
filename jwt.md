### JSON Web Tokens 

## Que es un JWT?

Es una cadena, un conjunto de caracteres, que contiene un poco de información. Para las sesiones de usuario puede incluir el username 
y el tiempo de expiración (fecha y hora). Pero en realidad puede representar lo que sea, incluso un identificador de sesión o el perfil 
completo del usuario que ha iniciado sesión. Aunque, por favor, esto debe evitarse.

Tiene una firma segura que evita que agentes externos malintencionados generen tokens falsos. Se necesita acceder a la clave privada del servidor 
para firmarlos; y gracias a esta firma se puede verificar que no se hayan modificado (desde que el servidor los firmó).

Se envían en cada petición (tal como sucede con las cookies). Comúnmente se envían a través del Authorization header de las peticiones HTTP, 
pero curiosamente también se pueden usar cookies para transportarlos.

Cada token es firmado, y así el servidor puede verificar su validez. El servidor confía en su habilidad para firmar los tokens de forma segura. 
Para esto existen bibliotecas estándares, que se recomiendan sobre las implementaciones que uno mismo pueda realizar.

A fin de transportar de manera segura el token, lo adecuado es enviarlo a través de un canal encriptado (generalmente https).

La autenticación basada en tokens carece de estado (es stateless).

El servidor ya no guarda información de qué usuarios están conectados o qué tokens se han emitido. Esto es así porque cada solicitud 
realizada al servidor va acompañada de un token, y el servidor verifica la autenticidad de la solicitud basándose únicamente en el token.

Como ya comentamos antes, JWT define un formato para los tokens. Pero JWT no nos ata a ningún mecanismo de persistencia de datos en el lado del cliente y tampoco 
a ninguna regla de cómo se debe transportar el token.

Los tokens se envían generalmente como un Authorization header, con el valor Bearer {JWT}; pero pueden enviarse también en el cuerpo de una petición POST o 
incluso como un query parameter.

Veamos cómo funciona:

 1. Un usuario ingresa sus credenciales (datos que le permiten iniciar sesión)

 2. El servidor verifica que las credenciales sean correctas, y devuelve un token firmado

 3. El token es guardado en el lado del cliente, comúnmente en el local storage (pero puede guardarse también en el session storage o incluso como una cookie)

 4. Las peticiones siguientes al servidor incluyen este token (a través de un Authorization header o alguno de los otros métodos antes mencionados)

 5. El servidor decodifica el JWT y si el token es válido procesa la solicitud

 6. Una vez que el usuario se desconecta, el token es destruido en el lado del cliente (no es necesaria la interacción con el servidor)

## Sin estado, escalable y desacoplado

Probablemente la mayor ventaja de usar tokens y no cookies es el hecho de que ofrecen una autenticación sin estado (stateless).

Desde backend no se necesita tener un registro de los tokens. Cada token es autónomo: contienen en sí mismos toda la data necesaria para confirmar su 
validez (así como también información puntual del usuario que ha iniciado sesión).

De esta forma, el único trabajo del servidor es: firmar tokens ante un inicio de sesión exitoso, y verificar que los tokens entrantes sean válidos.

## Los Tokens son firmados (estructura)

JSON Web Token (JWT) es un estándar abierto (RFC 7519) que define una forma compacta y autónoma de transmitir información de forma segura entre
partes como un objeto JSON. Esta información puede ser verificada y confiable porque está firmada digitalmente.

Los JWT se pueden firmar mediante un sercreto (con el algoritmo HMAC) o un par de claves publica/privadas mediante RSA o ECDSA.

La firma también certifica que solo el portador o el creador del token que posee la clave privada puede descifrar el token, por lo tanto si queremos utilizar
dicho token, debemos conocer la palabra sercreta o la firma del servicio que genero dicho token, para que token queden valido. De lo contrario quedara invalido.
Esto es con el fin de verificar que el remitente del JWT es quien dice ser.

La firma tambien se utiliza para verificar que el mensaje no se modificó en el camino y, en el caso de tokens firmados con una clave privada, 
también puede verificar que el remitente del JWT es quien dice ser.

Un JSON Web Token se compone de 3 partes: header, payload, y signature.

### header 

El encabezado normalmente consta de dos partes: el tipo de token, que es JWT, y el algoritmo de firma que se utiliza, como HMAC SHA256 o RSA.

Ejemplo:

```
{
  "alg": "HS256",
  "typ": "JWT"
}
```

Luego, este JSON es codificado en Base64Url para formar la primera parte del JWT

### payload

La segunda parte del token es el payload, que contiene los Claims. Los Claims son declaraciones 
sobre una entidad (normalmente, el usuario) y datos adicionales. Hay tres tipos de Claims: 

### Claims registradas 

Se trata de un conjunto de reclamaciones predefinidas que no son obligatorias pero 
sí recomendadas, para proporcionar un conjunto de reclamaciones útiles e interoperables. 

Algunos de ellos son: iss (issuer), exp (Expiration time), sub (subject), aud (audiencie) y otros.

    - iss = emisor
    - expiration time = Tiempo de vencimiento
    - sub = asunto 
    - aud = audiencia

### Claims públicas  

Estos pueden ser definidos a voluntad por quienes usan JWT. Pero para evitar colisiones, deben definirse en el Registro de tokens web JSON de IANA o 
definirse como un URI que contenga un espacio de nombres resistente a colisiones.


### Cliams privadas.

Estos son reclamos personalizados creados para compartir información entre partes que acuerdan usarlos y no son reclamos registrados ni públicos.

Ejemplo de Claims: 

```
{
  "sub": "1234567890",
  "name": "John Doe",
  "admin": true
}
```

Luego, el payload se codifica en Base64Url para formar la segunda parte del token web JSON.

### signature

Para crear la parte de la firma, debe tomar el encabezado codificado, la carga útil codificada, un secreto, el algoritmo especificado en el encabezado y firmarlo.

Por ejemplo si desea utilizar el algoritmo HMAC SHA256, la firma se creará de la siguiente manera:

```
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  secret)
```

La firma se utiliza para verificar que el mensaje no se modificó en el camino y, en el caso de tokens firmados con una 
clave privada, también puede verificar que el remitente del JWT es quien dice ser.


## Formato del JWT

El formato de los JWT consiste en unir estas partes usando un punto entre ellas: header.payload.signature.

Por ejemplo, si tuviéramos que firmar un JWT con el algoritmo HMACSHA256, la clave secreta 'shhhh' y el siguiente contenido (payload):

```
{
  "sub": "1234567890",
  "name": "Ado Kukic",
  "admin": true
}
```

A continuación se muestra un JWT que tiene el encabezado y la carga útil anteriores codificados y está firmado con un secreto.

El JWT generado sería:

```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkFkbyBLdWtpYyIsImFkbWluIjp0cnVlLCJpYXQiOjE0NjQyOTc4ODV9.Y47kJvnHzU9qeJIN48_bVna6O0EDFiMiQ9LpNVDFymM
```

Lo más importante a tener en cuenta aquí, es que este token está firmado usando el algoritmo HMACSHA256, pero el encabezado (header) y los datos (payload) 
están codificados en Base64URL (no están encriptados).

### Encriptación

Implica transformar datos para que solo aquellos que posean una clave específica puedan revertir la transformación y acceder a 
la información original. La encriptación se utiliza para proteger la confidencialidad de los datos y suele requerir una clave para desencriptar la información.

### Codificación

La codificación es simplemente la representación de datos en un formato específico. El objetivo principal de la codificación es garantizar que los 
datos sean legibles dentro de un sistema particular.

La codificación Base64 no proporciona seguridad

Su objetivo principal es representar datos binarios de una manera segura para su transmisión o almacenamiento.

REVERSIBILIDAD: La codificación es reversible, lo que significa que puedes recuperar los datos originales si conoces el esquema de codificación utilizado. 

No hay seguridad ni ocultamiento de datos involucrados en la codificación.


## Cross Domain y CORS

Las cookies funcionan bien con un dominio (o subdominio) en específico, pero cuando se trata de administrar cookies en diferentes dominios, 
el manejo se torna complicado.

En contraste, un enfoque basado en tokens con CORS habilitado hace que sea trivial exponer las APIs a diferentes servicios y dominios.

Dado que se requiere y se verifica un token en cada una de las llamadas al backend, siempre que haya un token válido, las solicitudes se pueden procesar. 

## Guardar datos en los JWT

Con un enfoque basado en cookies, simplemente guardamos el identificador de sesión.

Los tokens por otro lado nos permiten guardar cualquier tipo de metadata, siempre que se trate de un JSON válido.

La especificación de JWT indica que podemos incluir diferentes tipos de datos (llamados claims), y que se pueden guardar como datos reservados, públicos y privados.

Dependiendo del contexto, podemos optar por usar una cantidad mínima de claims, y guardar sólo la identificación de usuario y el vencimiento del token, 
o bien podemos incluir claims adicionales, como el email del usuario, quién emitió el token, los alcances y/o permisos de los que dispone el usuario, etcétera.

## Listo para móviles
Las APIs modernas no solo interactúan con el navegador.

Escribir correctamente una API implica que pueda ser usada tanto por navegadores como desde plataformas móviles nativas (como iOS y Android).

Las plataformas móviles nativas y las cookies no operan muy bien en conjunto, ya que se debe tener en cuenta toda una serie de consideraciones para su correcto 
funcionamiento.

Los tokens, por otro lado, son mucho más fáciles de implementar (tanto en iOS como en Android). También son más fáciles de implementar para aplicaciones
y servicios de Internet of Things (que no incorporan el concepto de gestión de cookies).







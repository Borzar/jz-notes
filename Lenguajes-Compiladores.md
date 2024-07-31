# Lenguaje Máquina

Es el conjunto de datos que la parte física de la computadora (hardware) es capaz de comprender e interpretar "El Código binario" comprendido por los valores 0 y 1.

Estos datos son tensiones de corriente eléctrica comprendidas entre 0 y 4 voltios, estas secuencias de valores formaran cadenas de información para que se realice una instrucción.

## ¿Que tiene que ver el 0 y 1?

Conforman los valores denominados Sistema binario o codigo binario. Se le denomina así por poseer solamente dos valores.

## ¿Existen otros sistemas de números? 

Si, ejemplo Sistema Decimal, Intervienen 10 valores. (0 y 9) y Sistema Hexadecimal, Intervienen 16 valores. (0-9 y A-F)

## ¿Cómo entiende la computadora lo que escribo?

Cuando se escribe se envian estas pulsaciones a un circuito integrado donde esta almacenado la información de los caracteres ASCII. Esta información es enviada mediante unos cables (USB) a la CPU de la computadora que los interpreta.

## ¿Que es ASCII?

- Es un sistema de codificación de caracteres alfanuméricos. 
- Para cada letra o simbolo de nuestro teclado se le asigna un codigo.
- Estos codigos son introducidos o programados en cada teclado y en el ordenador para que los pueda codificar.

## ¿Cómo se forman los datos?

- Los datos se forman a partir de los ***Bit*** (unidad básica de almacenamiento de datos).
- En el Sistema Binario el valor 0 y 1 se le denomina ***Bit***(se utiliza para representar un valor binario de 0 o 1).
- **Byte** = 8 ***bits*** (minimo necesario para construir un caracter, ejemplo 01110010).
- Un grupo de 8 ***bits*** (1 **Byte**) formara un caracter, una letra, un numero, un simbolo o un color en la computadora.

## Mas información

- Lenguaje se ejecuta diractamente en la CPU de la computadora y actúa sobre el hardware que compone el equipo.
- Es un lenguaje de bajo nivel.
- Esta compuesto por numeros binarios.
- Para que la computadora pueda entender o interpretar cualquier instrucción que el usuario le suministre, es necesario que esta informacion este escrita en código binario. 
- Datos binarios = tensión de corriente eléctrica:
-  - 0 = ausencia de tensión
-  - 1 = presencia de tensión
- Con el uso de dos únicos digitos, o condición en los transitores, la máquina ejecutara cualquier condición que le hagas.
- El codigo de cualquier lenguaje de programación siempre  terminará siendo 'traducida' al lenguaje máquina.
- Con este lenguaje es la unica forma de poder hacer que el procesador lleva a cabo las tareas que le encomiendas.

## Compilación 

Proceso de convertir a unos y ceros todas las lineas de código que el programador ingresó en su lenguaje de programación.
Es el proceso de empaquetar las mencionadas líneas de código en una forma comprensible para el procesador, que las ejecutara y devolverá de una forma util para ti.

## Tips

- Los dispositivos digitales como las computadores y otro hardware programable solo pueden interpretrar datos binarios
- Todo lo que se ve en la computadora esta compuesto por unos y ceros. Cada imagen que componen un programa que usas, video que miras o canción  que escuchas, es binario.
- Todo el código convertido a unos y ceros, es decir el programa compilado, es enviado al procesador, que luego, al ejecutarlo, lo devuelvede modo visual para que puedas tomar una determinación o sólo consultar los datos.
- Las computadoras y demas dispositivos digitales programables como microcontroladores, usan para llevar a cabo sus tareas el llamado lenguaje máquina. 

<br>

# ¿Que función cumple la CPU? (Unidad Central de Procesamiento)

El procesador es la unidad de hardware responsable de ejecutar las instrucciones del binario. El procesador lee las instrucciones del binario, las decodifica y las ejecuta secuencialmente. Cada instrucción realizada por el procesador produce efectos en el estado de la CPU y en la memoria.

## Resumen CPU

1. Cambios en el estado de los registros: La CPU tiene varios registros internos que almacenan datos temporales y estados relacionados con la ejecución de las instrucciones. Estos registros pueden modificarse como resultado de operaciones aritméticas, lógicas y de control realizadas por la CPU.

2. Resultados de cálculos y operaciones: La CPU puede realizar cálculos matemáticos y lógicos, como sumas, restas, multiplicaciones, divisiones, operaciones de comparación, desplazamientos de bits, entre otros. Los resultados de estas operaciones se almacenan en registros específicos y pueden ser utilizados posteriormente por el programa en ejecución.

3. Cambios en el estado de las banderas o flags: Las banderas o flags son indicadores de estado que reflejan el resultado de operaciones anteriores realizadas por la CPU. Estos indicadores pueden incluir el estado de igualdad, desbordamiento, acarreo, signo, entre otros. Los cambios en estas banderas pueden ser utilizados por instrucciones de control de flujo condicional para tomar decisiones.

4. Generación de interrupciones: La CPU puede generar interrupciones para señalar eventos o condiciones específicas que requieren la atención del sistema operativo o de otros componentes. Estas interrupciones pueden ser generadas por instrucciones específicas del programa o por eventos externos, como la llegada de datos a través de un dispositivo de entrada/salida.

5. Acceso a dispositivos de entrada/salida: La CPU puede interactuar con dispositivos de entrada/salida (E/S) para leer o escribir datos desde o hacia ellos. Estos dispositivos pueden incluir teclados, pantallas, discos duros, tarjetas de red y otros periféricos. La CPU emite señales de control y datos a través de buses y puertos para comunicarse con estos dispositivos.

## Ejecución del binario

1. El sistema operativo transfiere el control al punto de entrada del binario, que generalmente es una dirección de memoria específica.
2. El procesador inicia la ejecución del binario, leyendo y ejecutando las instrucciones una tras otra.
3. El procesador sigue el flujo de control definido por las instrucciones, como saltos condicionales, bucles y llamadas a funciones.
4. A medida que se ejecutan las instrucciones, se pueden realizar operaciones de cálculo, manipulación de datos, operaciones de E/S y otros tipos de acciones definidas en el programa.

## Salida del binario

1. Durante la ejecución, si el programa genera una salida visible, como texto en la pantalla, esta salida se envía al sistema operativo.
2. El sistema operativo se encarga de mostrar la salida en la interfaz gráfica o en la consola, según corresponda.
3. También puede haber otros tipos de salida, como escribir en archivos o enviar datos a través de la red, que el sistema operativo manejará según sea necesario.

<br>

# Lenguaje Ensamblador 

El lenguaje ensamblador expresa las instrucciones de una forma más natural al hombre a la vez que muy cercana al microcontrolador, ya que cada una de esas instruccines corresponde con otra en código máquina.

- Lenguaje de bajo nivel.
- El lenguaje ensamblador puede variar según la arquitectura del procesador utilizado.
- Cada arquitectura tiene su propio conjunto de instrucciones y sintaxis especifica.
- Los computadores emplean lenguaje binario para llevar a cabo cada proceso.
- El lenguaje ensamblador trabaja con __nemónicos__, que son grupos de caracteres alfanuméricos que simbolizan las órdenes o tareas a realizar.
-  La traducción de los nemónicos a código máquina entendible por el microcontrolador la lleva a cabo un programa ensamblador.

 ***El programa escrito en lenguaje ensamblador se denomina código fuente (*.asm). El programa ensamblador proporciona a partir de este fichero el correspondiente código máquina, que suele tener la extensión *.hex***

## ¿Como funciona?

Los computadores tienen su propio lenguaje, compuesto de un código binario representado por ceros y unos en secuencias únicas. El lenguaje ensamblador está a un nivel intermedio (lenguajes de programación y binario).

Usa código mnemotécnico para formular las instrucciones básicas que son interpretadas por los computadores, procesadores, controladores y cualquier circuito integrado que sea programable.

Ejemplos de instrucciones en lenguaje ensamblador:

- add. Instruye al procesador para que sume dos operandos y almacene el resultado.
- mov. Sirve para mover datos o registros de un sitio a otro.
- mul. Da instrucciones al procesador de realizar la multiplicación de dos operandos.
- and. Instrucción necesaria para utilizar el operador lógico 'y' en lenguaje ensamblador.

***Importante: Cada lenguaje ensamblador emplea instrucciones propias, esto es solo un ejemplo***

## Caracteristicas

- Consume pocos recursos.
- Es legible por humanos y programable.
- Cada instrucción del lenguaje corresponde a una instrucción de código de máquina
- Los programas de lenguaje ensamblador se traducen directamente en instrucciones de código máquina y cada instrucción de ensamblaje se traduce en una sola instrucción de código de máquina.
- Funciona bien con dispositivos que tienen poca RAM.
- No es portable, es decir el código generado es propio de cada sistema o arquitectura del computador.
- La CPU solo tiene capacidad de interpretar información que son datos binarios, por lo que el lenguaje ensamblador nececita ser traducido a datos binarios que serán entendidos por la CPU.

## ¿Donde se utiliza?

- Se utliza en procesadores 
- Programación de sistemas operativos 
- Controladores y microcontroladores

<br>

# Lenguajes de alto nivel

Tienen por objetivo facilitar el trabajo del programador permitiendo desarrollar aplicaciones independientes de la máquina.

Algunas diferencias con los lenguajes máquinas y ensamblador, es que no permiten aprovechar completamente los recursos internos de la máquina. Estas caracteristicas ponen de manifiesto un acercamiento a las personas y un alejamiento de la máquina.

Es por esta razón, los programas escritos en lenguaje de alto nivel no pueden ser interpretados directamente por la computadora, por lo que es necesario realizar previamiente su traducción a lenguaje máquina.

Es por ello que se deben utilizar unos programas traductores (desarrollados con antelación por cada computadora) para que realicen dicha traducción.

<br>

# Compiladores e intérpretes

Como el ordenador puede interpretar y ejecutar sólo el código máquina, existen programas especiales, llamados __traductores__, que traducen programas escritos en un lenguaj de programación al lenguaje máquina de la computadora.

Un traductor es un metaprograma que toma como entrada un programa (o parte de un programa) escrito en lenguaje simbólico -alejado de la maquina- denominado programa fuente y proporciona como salida otro programa semánticamente equivalente y escrito en un lenguaje comprensible por el __hardware__ de la computadora que recibe el nombre de programa objeto.

<br>

# Compilador

Un compilador traduce completamente en programa fuente, con lo que genera un programa objeto escrito en lenguaje máquina. El programa fuente suele estar contenido en un fichero, y el programa objeto puede almacenarse como otro fichero en memoria masiva para ser ejecutado más adelante, sin nececidad de volver a realizar la traducción. Una vez traducido un programa, su ejecución es independiente de su compilación.

Ejemplo:

   - Imagina que tienes un receta de cocina escrita en latin. Hay dos formas en que tú, alguien que no habla latin, podrias seguir dichas instrucciones.
   - La primera es si alguien ya lo a traducido al español para ti. Luego podras leer la version en español y hacer la receta. Piensa en esta receta traducida como la versión __compilada__.

<br>

# Intérprete

Un intérprete permite que un programa fuente escrito en un determinado lenguaje sea traducido y ejecutado directamente sentencia a sentencia por la computadora. El intérprete capta una sentencia fuente, la analiza y la interpreta, lo que da a lugar a su ejecución indmediata. No se crea ningún fichero o programa objeto almacenable en memoria masiva para posibles ejecuciones futuras. 

Ejemplo:

   - Una segunda manera es si tienes un amigo que sabe latin. Cuando estes listo para hacer esta receta, tu amigo se sienta junto a ti y traduce al español mientras avanzas, linea por linea. En este caso tu amigo es el intérprete de la version __interpretada__ de la receta.

<br>

# Lenguajes compilados

Los lenguajes compilados son convertidos directamente a código máquina que el procesador puede ejecutar. Como resultado suelen ser más mas rápidos y más eficientes al ejecutarse en comparación con los lenguajes interpretados. También le dan al desarrollador más control sobre aspectos del hardware, como la gestión de memoria y el uso del CPU.

Los Lenguajes compilados nececitan un paso de compilación (build) - primero necesitan compilarse manualmente. Necesitas "recompilar" el programa cada vez que nececites hacer un cambio.

Ejemplo:

   - C, C++, C#, Erlang, Haskell, Rust y Go.

<br>

# Lenguajes interpretados

Estos lenguajes ejecutan línea por línea el programa y ala vez ejecutan cada comando.

Los lenguajes interpretados alguna vez fueron significativamente más lentos que los lenguajes compilados. Pero, con el desarrollo de la compilación justo a tiempo, esa diferencia se está reduciendo.

Ejemplo:

   - PHP, Ruby, Python y javaScript.

<br>

___Ambos todman el código legible por los humanos y lo convierten en código máquina legible por las computadoras___



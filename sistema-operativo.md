# Sistema Operativo

Nos permite comunicarnos con el computador sin hablar el idioma del computador. Sin un sistema operativo el computador es inutil.
Un sistema operativo es un software que actúa como intermediario entre el hardware de un computadora y los programas que se ejecutan en ella.
Su funcion es gestionar la memoria, los procesos, archivos, seguridad, recursos, dispositivos, I/O, etc.

Hardware(CPU, Memoria, Disco duro) --> SO (Windows, OS X, Linux) --> Programas --> Usuario Final (ejecucion de programas)

## Funcion del SO (entre otros)

Gestion de recursos        : Controla el acceso y asignacion de recursos del hardware, como la CPU, la memoria, el disco duro y perifericos.
                             Para garantizar la que multiples programas puedan ejecutarse simultaneamente.
Gestion de procesos        : Administra la ejecucion de programas o procesos, programando tareas a utilizar la CPU de manera eficiente
(programas)                  y garantizando la multitarea. 
                             Administra la ejecucion de procesos o programas en la CPU, asignando tiempo de CPU, y administrando su creacion,
                             suspension, reanudacion y finalizacion.
Gestion de memoria         : Controla la asignacion y liberacion de memoria (RAM) para programas garantizando un uso eficiente de la Memoria
                             disponible.
Gestion de archivos        : Ofrece un sistema de archivos que permite la creacion, lectura, escritura y eleminacion de archivos. A si como la 
                             organizacion de y proteccion de datos en el almecenamieto.
Gestion de dispositivos    : Controla la comunicacion entre programas y perifericos (impresoras, teclados, mouse, etc) a traves de controladores 
                             de dispotivos.
Interfaz de usuario  
Seguridad y autenticacion  : Controla el acceso a recursos y datos protegiendo el sistema contra amenazas y asegurando la autenticacion del usuario.
Gestion de redes
Gestion de errores
Gestion de energia
Gestion del Procesador
Gestion de I/O             : Se refiere a la administracion y control de operaciones de entrada y salida (dispositivos externos, teclados, ratones, monitores,
                             discos duros, impresoras, redes) de un sistema.
## Caracteristicas 

Permite la ejecucion de programas
Gestión de memoria Memoria virtual Multitarea
Manejo de operaciones de I/O
Manipulación del sistema de archivos
Detección y manejo de errores
Asignación de recursos

## Cuales son las app que un SO?

Seguridad: SO impide el acceso no autorizado a programas y datos.
Control del rendimiento del sistema: Registro de retrasos entre la solicitud de un servicio y la respuesta del sistema. 
Contabilidad del trabajo: puede realizar un seguimiento del tiempo y los recursos.
Ayuda para deteccion de errores: El SO ayuda a rastrear mensajes de error y otras ayudas de depuracion.
Ayuda en la cordinacion otros programas: Coordinacion y asignacion de compiladores, interpretes, ensambladores y otro software. 

## Que es el Kernel de un Sistema Operativo

Es el componente central de un sistema de operativo. El unico trabajo del kernel es gestionar la comunicacion entre el software(apps) y el hardware. El kernel es el 
nucleo de un computador. Mientras que el kernel es la parte mas interna de un sistema operativo, la shell es la parte mas externa.

Es un mediador entre el software y el hardware. Concede el acceso al hardware, al software que lo solicite de una manera segura.

Actúa como puente entre el software y el hardware de la computadora.

El kernel es definido como el núcleo o corazón del sistema operativo, y se encarga principalmente de mediar entre los procesos de usuario y el 
hardware disponible en la máquina, es decir, concede el acceso al hardware, al software que lo solicite, de una manera segura; y el procesamiento paralelo de varias tarea

Hardware --> SO (Kernel (parte mas interna del SO) --> Shell (parte mas externa del SO) ) --> Terminal --> User

## Caracteristcias del Kernel

Programacion de procesos de bajo de nivel
Comunicacion entre Procesos
Sincronizacion de Procesos
Cambio de Contexto


## POSIX
Portable Operating System Interface for Unix
Es un conjunto de estandares y derectrices para sistemas operativos tipo Unix. 
Los sistemas que siguen las especificaciones POSIX implementan las funciones y la interfaz definida por estos estandares.

Las cosas mas importantes definidas por POSIX:
    1. C API (Proporciona un conjunto de funciones y llamadas al sistema que permiten  a los programadores interactuar con el SO, "Biblioteca del lenguaje C"):
        file operations: mkdir, dirname, symlink, readlink, link, proporciona funciones para abrir, leer, escribir, y cerrar archivos.
        Process and Threads: fork, execl, wait, pipe.(Puedes crear, administrar y controlar procesos utilizando funciones, permiten lanzar nuevos programadas
                             entre otros)
        Networking: Socket
        Memory Managamen: mmap, mlock, mprotect, madvice, brk. (funciones).
        Utilities:  Regular expresion.
    2. CLI Utilities:
        Ejemplo: cd, ls, echo                
    3. Shell Lenguage
    4. Enviroment Variables: HOME, PATH
    5. Program exit status: ANSI C says 0 or EXIT_SUCCESS for success, EXIT_FAILURE for failure, and leaves the rest implementation defined.
    6. Regular expresion.
    7. Directory structure: Ejemplo: /dev/null, /tmp
    8. Filenames: / es el separador de ruta


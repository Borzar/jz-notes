# Asignacion de memoria (Memory Allocation)

La asignacion de memoria se refiere al proceso de reservar un espacio en memoria del sistema (RAM) para el uso de un programa en ejecucion.
Este proceso es fundamental en la programacion y en el funcionamiento de los sistemas operativos, ya que garantiza que los programas
puedan almacenar y acceder a datos mientras se ejecutan.

## Tipos de memoria

### Memoria Stack
- El stack es una estructura de datos que sigue el principio Last In, First Out (LIFO). 
- <b>Uso:</b> Es utilizado para almacenar variables locales, parámetros de funciones, y datos temporales durante la ejecución de un programa.
- <b>Asignacion Dinamica:</b> 
  - Asignacion dinamica se refiere al proceso de reservar espacio en memoria en tiempo de ejecucion, en lugar de hacerlo en tiempo de compilacion. 
  - La memoria Stack maneja automáticamente la asignación y liberación de memoria, sin intervención explícita por parte del programador. 
  - Cuando una funcion es llamada, se crea un nuevo stack frame (reserva de espaco en el stack) que contiene las variables.
locales y parametros de una funcion. Al finzalizar la funcion, el stack frame se destruye y la memoria se libera.
  - Si se pasa un objeto como parametro, si es por valor, se crea una copia del objeto en el Stack para usarlo adentro de la funcion. (C y C++)
  - Si es por referencia (C# y Java), es decir, que cualquier cambio realizado afecta al objeto original, la liberacion de memoria se gestiona en el contexto donde se creo el 
objeto, no en la funcion. 
- <b>Ventajas:</b> Rapida y de gestion automatica
- Tipos de datos del Stack:
  - int, short, long.
  - char
  - float
  - bool

### Memoria Heap
- Ocurre en tiempo de ejecucion.
- La memoria heap se utiliza para almacenar datos cuya cantidad o tamaño puede cambiar durante la ejecución del programa.
- La memoria debe ser liberada manualmente para evitar fugas de memoria (Gestionada manualmente o por el Garbage Collector). 
- Se utiliza para estructuras de datos dinamicas como listas y arboles, clases y objetos.
- Permite asignar grandes bloques de memoria y gestionar datos de larga duración.
- Más lenta y propensa a errores como fugas de memoria (memory leaks) si no se libera correctamente.
- Ejemplo en C:
'''
int *ptr = (int *)malloc(sizeof(int) * 10); // Asignación dinámica
free(ptr); // Liberación de memoria
'''

### Segmento de Datos:
- Se ubica dentro de la memoria ram.
- Está diseñado para contener variables globales y estáticas.
- Estas variables tienen una duración de almacenamiento que abarca toda la ejecución del programa.
- La cantidad de memoria requerida y el espacio reservado son conocidos y no cambian durante la ejecución del programa.
- Se utiliza en variables globales y variables globales estaticas.
  - <b>Variables Globales:</b> Declaradas fuera de cualquier funcion.
  - <b>Variables Estáticas:</b> Pueden ser variables globales o locales (dentro de una función) declaradas con la palabra clave static. 
También existen durante toda la vida del programa.
- Ejemplo en C:
'''
static int a; // Asignacion estatica
'''  

## Resumen:
-C y C++: La memoria asignada dinámicamente debe ser liberada manualmente utilizando free en C o delete en C++.
- Cuando hay una asignación dinámica dentro de una función, la memoria asignada en el Heap no se libera automáticamente cuando la función retorna. 
Debe ser gestionada manualmente por el programador, independientemente de lo que la función retorne.

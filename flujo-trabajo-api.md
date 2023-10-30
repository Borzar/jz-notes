## Flujo para trabajar en una API (procedimientos)

Repository --> DTO --> Model --> BO(se llama a la interface ejemplo IMantenimientoPlanillasRepository) --> Mapper --> Endpoint 

Repository --> DTO --> Model --> BO --> Mapper --> API***


## TIPS:

* El dato de salida es un dynamic usamos esto para una salida numerica generalmente
en este caso no hay mapper de salida, pero si la clase input del model debe tener algo diferente
fijate que el request devuelve un decimal (IRequest del model)

* Interfaces => Las interfaz contienen todos los procedimientos almacenados del Package. Esta interfaz se utiliza el repository y en BO.
* Mapper => ordenado por #region segun el business. Por Ejemplo #region Proceso --- #endregion
* Repository => Cada repository apunta a uno o mas packages y adentro sus procedimientos almacenados.
* BO => Cada BO representa un packeage.


Ejemplo: 
    nombre de la carpeta     -> Repository/IngresoAlFondo/MovimientosBancariosRepository
    nombre repository        -> MovimientosBancariosRepository
    nombre del Package       -> PING_MOVIMIENTOS_BANCARIOS
    nombre del procedimiento -> CREAR_AUX_SIN_DOC
    nombre BO                -> MovBancariosCrearAuxSinDocBO (o tambien el nombre del procedimiento mas la palabra BO)

*el nombre del Repository es igual al nombre del package

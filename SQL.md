# SQL  

## SQL DATABASE
## DATA DEFINITION LANGUAGE (DDL)

### CREATE DATABASE 
```
CREATE DATABASE databasename;
```

### CREATE TABLE
 ```
create table table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
   ....
);
 ```

```
create table employees (
    id int not null,
    name varchar(255) not null,
    salary int,
    department varchar(255),
    position varchar(255)
);
```

### ALTER TABLE
Permite alterar la estructura de una tabla existente
 ```
alter table tablename
add (columnname1 datatype,
     columnname2 datatype,
     ...
     );
 ```

### DROP TABLE
Se utiliza para eliminar una base de datos SQL existente.
 ```
DROP TABLE table_name;
 ```

### SQL TRUNCATE TABLE
La declaración se utiliza para eliminar los datos dentro de una tabla, pero no la tabla en sí.
```
TRUNCATE TABLE table_name;
```

## DATA MANIPULATION LANGUAGE (DML)

# INSERT 
La instrucción INSERT INTO se utiliza para insertar nuevos registros en una tabla.
```
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
```

# UPDATE 
El comando ACTUALIZAR en SQL se utiliza para modificar los registros existentes en una tabla.
*La cláusula WHERE en la declaración UPDATE especifica qué registros modificar. Si omite la cláusula WHERE, ¡se actualizarán todos los registros de la tabla!
```
UPDATE table_name
SET column1 = value1, column2 = value2...., columnN = valueN
WHERE [condition];
```
`Set: Esta palabra clave se utiliza para establecer los valores de la columna.`

# DELETE 
La declaración DELETE se utiliza para eliminar registros existentes en una tabla.
```
DELETE FROM students WHERE student_id = '1001';
```
*Precaución: tenga mucho cuidado al utilizar la declaración DELETE. Si omite la cláusula WHERE, ¡se eliminarán todos los registros!

M students WHERE student_id = '1001';

# SELECT

## CLAUSE (WHERE, GROUP BY, HAVING, ORDER BY)

Syntax: 

```
SELECT column1, column2,...columnN 
FROM table_name
[WHERE]
[GROUP BY]
[HAVING]
[ORDER BY column(s) [ASC|DESC]]
```
### WHERE
La clausula where es usada para filtrar registros 
Operadores que pueden ser usados en la clausula WHERE

Operator	Description
    =           Equal
    >           Greater than
    <           Less than
    >=          Greater than or equal
    <=          Less than or equal
  <> or !=	    Not equal. In some databases, the != is used to compare values which are not equal.
 BETWEEN        Between some range
  LIKE          Search for a pattern
   IN           To specify multiple possible values for a column
  AND           Muestra el registros solo si todas las condiciones se cumplen.      
   OR           Muestra el registro si alguna de las condiciones es verdadera 

### GROUP BY
Agrupa filas que tienen los mismos valores en filas resumen. Como ejemplo seria "encontrar el numero de clientes de cada pais"
Se usa a menudo con funciones count(), max(), min(), sum(), etc. Para agrupar el conjunto de resultados en un columna

```
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
ORDER BY column_name(s);
```

### HAVING 
La clusula HAVING se agrego a SQL porque la clusula WHERE no puede ser usada con funciones sql.
Actua sobre las funciones de aggragate (funciones agregadas en sql como max(), mix(), etc)).

```
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) > 5;
```

### ORDER BY
Puede ser usada para ordenar registros en una o mas columnas en order ASC o DESC 

```
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;
```

## CONDITIONAL OPERATORS (IN, <, >, =, LIKE, BETWEEN)
Operator	Description
    =           Equal
    >           Greater than
    <           Less than
    >=          Greater than or equal
    <=          Less than or equal
  <> or !=	    Not equal. In some databases, the != is used to compare values which are not equal.
 BETWEEN        Between some range
  LIKE          Search for a pattern
   IN           To specify multiple possible values for a column

### IN 
Permite especificar multimple valores en una clausula WHERE.
Es un atajo para multiples condiciones OR.
También puedes usar IN con una subconsulta en la cláusula WHERE. Con una subconsulta puede devolver 
todos los registros de la consulta principal que están presentes en el resultado de la subconsulta

Syntax:

```
SELECT column1, column2,..
FROM table
WHERE column IN (value1, value2, value3,...)

-- or

SELECT column1, column2,..
FROM table
WHERE column IN (SELECT query)
```

```
SELECT EmpId, FirstName, LastName, Salary
FROM Employee
WHERE EmpId IN (1, 3, 5, 6)
```

La query anterior retornara los registros donde EmpId es 1 o 3 o 5 o 6.

## AGGREGATE FUNCTIONS
- SUM
- COUNT
- AVG
- MIN
- MAX

### MAS FUNCIONES ... 

## SQL EXPRESSIONS

### CASE

La expresion devuelve un valor cuando se cumple la primera condicion.
(como una declaracion if else). Una vez que que la condicion es verdadera, dejara de leer y devolvera el resultado.

```
case
    when condition1 then result1
    when condition2 then result2
    when conditionn then resultn
    else result
end
```

```
SELECT OrderID, Quantity,
    CASE
        WHEN Quantity > 30 THEN 'The quantity is greater than 30'
        WHEN Quantity = 30 THEN 'The quantity is 30'
        ELSE 'The quantity is under 30'
    END AS QuantityText
FROM OrderDetails;
```

```
SELECT
    CASE
        WHEN A+B<=C OR A+C<=B OR B+C<=A THEN 'Not A Triangle'
        WHEN A=B AND B=C THEN 'Equilateral'
        WHEN A=B OR B=C OR C=A THEN 'Isosceles'
        ELSE 'Scalene'
    END AS TRIANGLE
FROM TRIANGLES
```


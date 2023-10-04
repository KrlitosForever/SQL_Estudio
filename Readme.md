# ESTUDIO SOBRE SQL

Este repositorio esta destinado a mi aprendizaje sobre SQL.
La base de datos con la que se esta trabajando se encuentra en la carpeta DB.

# ÍNDICE
- [Día 1](#día-1)
- [Día 2]()
- [Día 3]()
- [Día 4]()
- [Día 5]()
- [Día 6]()
- [Día 7]()
- [Día 8]()
- [Día 9]()
- [Día 10]()
- [Día 11]()
- [Día 12]()
- [Día 13]()
- [Día 14]()
- [Día 15]()

# Día 1

**¿Qué significa SQL?**

SQL (por sus siglas en inglés Structured Query Language; en español lenguaje de consulta estructurada) es un lenguaje específico de dominio, diseñado para administrar, y recuperar información de sistemas de gestión de bases de datos relacionales.[^1]

La importancia de SQL es que nos permite interactuar con nuestra base de datos.

Las bases de datos están compuestas por tablas. Cada tabla tiene **Filas** y **Columnas** en donde se almacenara la información.

SQL nos permite recuperar, analizar, definir o actualizar la información que se encuentre en nuestra base de datos.

Para poder trabajar sobre nuestra base de datos necesitaremos un *database management system (DBMS)*  esto nos permite crear y administrar nuestras bases de datos.

Existen variaciones en SQL siendo *PostgreSQL* el más cercano al estándar de *SQL*. Las diferencias entre un lenguaje de consulta y otro deben suelen ser mínimas.

## SELECT

La palabra clave **SELECT** es una de las más básicas a la hora de consultar información en SQL. Éste comando selecciona toda la información de las columnas que necesitemos de la tabla. El caso más básico es seleccionar toda la información de la tabla como se aprecia en el ejemplo:

 ```SQL
 SELECT
 *
 FROM
 clientes
 ```
Un ejemplo más genérico sería 

 ```SQL
 SELECT 
 nombre_de_la_columna
 FROM
 nombre_de_la_tabla
 ```

Para seleccionar multiples columnas de una tabla lo que debemos hacer es separarlas por coma (*,*), veamos un ejemplo

 ```SQL
 SELECT 
 nombre_de_la_columna1,
 nombre_de_la_columna2
 FROM
 nombre_de_la_tabla
 ```

> [!NOTE]
> Momento de aplicar lo aprendido, es tiempo de resolver el Desafio1.txt que se encuentra en la carpeta Día_1

## ORDER BY

La palabra clave **ORDER BY** nos ayuda a ordenar nuestro resultado, ya sea de manera alfabética, numérica o cronológica dependiendo del tipo de dato por el cual se desea ordenar.
Siguiendo con el ejemplo anterior esta es la forma de ordenar en base a la columna 1.

```SQL
 SELECT 
 nombre_de_la_columna1,
 nombre_de_la_columna2
 FROM
 nombre_de_la_tabla
 ORDER BY
 nombre_de_la_columna1
 ```
 Ésta consulta producirá como resultado que se ordenara de manera alfabética con respecto a la columna 1

 Podemos también ordenar de manera **DESC** *descendente* y **ASC** *ascendente*.
 Los ejemplos Serian los siguientes

 ```SQL
 -- Ordenar de manera Descendente
 SELECT 
 nombre_de_la_columna1,
 nombre_de_la_columna2
 FROM
 nombre_de_la_tabla
 ORDER BY
 nombre_de_la_columna1 DESC
 ```

 ```SQL
 -- Ordenar de manera Ascendente
 SELECT 
 nombre_de_la_columna1,
 nombre_de_la_columna2
 FROM
 nombre_de_la_tabla
 ORDER BY
 nombre_de_la_columna1 ASC
 ```

 Otra de las características de **ORDER BY** es que se pueden ordenar según el orden de la cascada, ejemplo

 ```SQL
 -- Ordenara por orden alfabético(ascendente) el nombre y luego el apellido
 SELECT 
 nombre,
 apellido
 FROM
 clientes
 ORDER BY
 nombre,
 apellido
 ```

 Otro ejemplo sería ordenar de manera descendente la primera columna para luego ordenar ascendente por la segunda

  ```SQL
 -- Ordenara por orden descendente el nombre y luego el apellido ascendente
 SELECT 
 nombre,
 apellido
 FROM
 clientes
 ORDER BY
 nombre DESC,
 apellido
 ```

> [!NOTE]
> Momento de aplicar lo aprendido, es tiempo de resolver el Desafio2.txt que se encuentra en la carpeta Día_1

## DISTINCT
La palabra reservada **DISTINCT** nos entrega los valores no duplicados. Quiere decir que si un valor se repite muchas veces en la columna con **DISTINCT** solo lo mostrará solo una vez.
Un ejemplo de ello sería:

  ```SQL
 -- Nos mostraría los nombres de los clientes sin duplicarlos
 SELECT DISTINCT
 nombre
 FROM
 clientes
 ```
> [!NOTE]
> Momento de aplicar lo aprendido, es tiempo de resolver el Desafio3.txt que se encuentra en la carpeta Día_1

## LIMIT
La palabra reservada **LIMIT** nos permite limitar la cantidad de resultados que necesitamos visualizar. Un ejemplo de ello sería:

  ```SQL
 -- Nos mostraría los "n" resultados que le solicitemos
 SELECT 
 nombre_de_la_columna1,
 nombre_de_la_columna2
 FROM
 nombre_de_la_tabla
 LIMIT n
 ```
Además se puede complementar con otras palabras reservadas, haciendo presente que **LIMIT** siempre tendría que ubicarse al final de la consulta.
Un ejemplo sería:

  ```SQL
 -- Ordenara por orden nombre y muestra 4 resultados
 SELECT 
 nombre,
 apellido
 FROM
 clientes
 ORDER BY
 nombre
 LIMIT 4
 ```

## COUNT
La función **COUNT** nos permite contar la cantidad de objetos que tenemos en un columna. Esto quiere decir que si queremos saber cuantas filas posee nuestra columna esta es una manera de saberlo.
Un ejemplo de esta función sería:

  ```SQL
 -- Esta función nos indicara numéricamente cuantos nombres hay.
 SELECT 
 COUNT(nombre)
 FROM
 clientes
 ```
Si quisiéramos saber la cantidad de estos nombres sin repetir podríamos utilizar la siguiente combinación:

  ```SQL
 -- Esta función nos indicara la cantidad de nombres sin duplicar.
 SELECT 
 COUNT(DISTINCT nombre)
 FROM
 clientes
 ```
Una forma simplificada de saber cuantas filas cuenta nuestra tabla sería:

  ```SQL
 -- Ordenara por orden nombre y muestra 4 resultados
 SELECT 
 COUNT(*)
 FROM
 clientes
 ```

> [!NOTE]
> Momento de aplicar lo aprendido, es tiempo de resolver el Desafio_final.txt que se encuentra en la carpeta Día_1

# Día 2

## WHERE
La palabra reservada **WHERE** nos permite filtrar la información en base a la condición que le otorguemos.
Veamos como emplear el **WHERE**:

  ```SQL
 -- Forma de emplear el Where
 SELECT 
 nombre_de_la_columna1,
 nombre_de_la_columna2
 FROM
 nombre_de_la_tabla
 WHERE condición
 ```

Un ejemplo practico sería buscar la cantidad de **CARLOS** que se encuentran en nuestra columna nombre:

 ```SQL
 -- Ejemplo practico de WHERE
 SELECT 
 nombre,
 apellido
 FROM
 clietes
 WHERE nombre = 'CARLOS'
 ```

> [!NOTE]
> Momento de aplicar lo aprendido, es tiempo de resolver el Desafio1.txt que se encuentra en la carpeta Día_2

Los Operadores que se pueden ocupar con **WHERE** son los siguientes:

``` 
1.- >
2.- <
3.- >=
4.- <=
5.- =
6.- !=
```
Otro caso de operadores son los siguientes:
```SQL
- is
- is not 
```
En los que se pueden definir como:
```SQL
...
WHERE columna_1 is null

...
WHERE columna_1 is not null
```

> [!NOTE]
> Momento de aplicar lo aprendido, es tiempo de resolver el Desafio1.txt que se encuentra en la carpeta Día_2

Continuando con los operadores que podemos emplear se pueden generar condiciones en donde queremos aplicar más de una condición es por eso que existe **AND** y **OR**. Un ejemplo de ello 

 ```SQL
 -- Forma de emplear el Where y operador AND
 SELECT 
 nombre_de_la_columna1,
 nombre_de_la_columna2
 FROM
 nombre_de_la_tabla
 WHERE condición 1
 AND condición 2
 ```

```SQL
 -- Forma de emplear el Where y operador OR
 SELECT 
 nombre_de_la_columna1,
 nombre_de_la_columna2
 FROM
 nombre_de_la_tabla
 WHERE condición 1
 OR condición 2
 ```

Inclusive puede ir más de un operador
```SQL
 -- Forma de emplear el Where con más de un operador
 SELECT 
 nombre_de_la_columna1,
 nombre_de_la_columna2
 FROM
 nombre_de_la_tabla
 WHERE condición 1
 AND condición 2
 AND condición 3
 ```

Si La condición se esta ejerciendo sobre una misma columna puede aplicarse lo siguiente:
```SQL
 -- Forma de emplear el Where y operador OR
 ...
 WHERE Precio_producto = 10.99 OR 9.99 
 ```

También se puede hacer el uso de paréntesis para generar condiciones distintas de resultado, ejemplo:

```SQL
 -- Forma de emplear el Where con más de un operador
 SELECT 
 nombre_de_la_columna1,
 nombre_de_la_columna2
 FROM
 nombre_de_la_tabla
 WHERE condición 1
 AND (condición 2
 OR condición 3)
 ```



[^1]:Morteo, Bocalandro, Francisco, Nicolás (2004). Un enfoque práctico de SQL. Ediciones Cooperativas. ISBN 987-1076-61-4.
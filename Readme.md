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

¿Qué significa SQL?
SQL (por sus siglas en inglés Structured Query Language; en español lenguaje de consulta estructurada) es un lenguaje específico de dominio, diseñado para administrar, y recuperar información de sistemas de gestión de bases de datos relacionales.[^1]

La importancia de SQL es que nos permite interactuar con nuestra base de datos.

Las bases de datos están compuestas por tablas. Cada tabla tiene **Filas** y **Columnas** en donde se almacenara la información.

SQL nos permite recuperar, analizar, definir o actualizar la información que se encuentre en nuestra base de datos.

Para poder trabajar sobre nuestra base de datos necesitaremos un *database management system (DBMS)*  esto nos permite crear y administrar nuestras bases de datos.

Existen variaciones en SQL siendo *PostgreSQL* el más cercano al estándar de *SQL*. Las diferencias entre un lenguaje de consulta y otro deben suelen ser mínimas.

## SELECT

La palabra clave **SELECT** es una de las más básicas a la hora de consultar información en SQL. Éste comando selecciona toda la información de las columnas que necesitemos de la tabla. El caso más básico es seleccionar toda la información de la tabla como se aprecia en el ejemplo:

 ```SQL
 SELECT * FROM clientes
 ```
Un ejemplo más genérico sería 

 ```SQL
 SELECT 
 nombre_de_la_columna
 FROM nombre_de_la_tabla
 ```

Para seleccionar multiples columnas de una tabla lo que debemos hacer es separarlas por coma (*,*), veamos un ejemplo

 ```SQL
 SELECT 
 nombre_de_la_columna1,
 nombre_de_la_columna2
 FROM nombre_de_la_tabla
 ```

> [!NOTE]
> Momento de aplicar lo aprendido, es tiempo de resolver el Desafio1.txt que se encuentra en la carpeta Día_1



[^1]:Morteo, Bocalandro, Francisco, Nicolás (2004). Un enfoque práctico de SQL. Ediciones Cooperativas. ISBN 987-1076-61-4.
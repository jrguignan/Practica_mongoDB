# Práctica MongoDB  - En Construcción 🚧

<p align="center">
<img src="images/mongodb.png"  height=150>
</p>

# Índice
* [MongoDB](#MongoDB)
* [Crear Conexiones en mongoDB Compass](#Crear-Conexiones-en-mongoDB-Compass)
* [Crear Cluster mongoDB - ATLAS](#Crear-Cluster-mongoDB---ATLAS)
* [Operadores](#Operadores)
  * [Comparación](#Comparación)
  * [Elementos](#Elementos)
  * [Evaluación](#Evaluación)
  * [Indexación](#Indexación)
  * [Método de Cursores](#Método-de-Cursores)
* [Consulta de Datos (CRUD)](#Consulta-de-Datos-(CRUD))
  * [Comandos Básicos y Proyección](#Comandos-Básicos-y-Proyección)
  * [Inserción](#Inserción)
  * [Lectura](#Lectura)
  * [Actualización](#Actualización)
  * [Borrado](#Borrado)
* [Agregación](#Agregación)  
* [Práctica de Comandos](#Práctica-de-Comandos)  
* [Tegnologías Utilizadas](#Tegnologías-Utilizadas)
* [Autor](#Autor)


# MongoDB 

Es un sistema de gestión de bases de datos de código abierto y orientado a documentos, que se clasifica dentro de la categoría de bases de datos NoSQL (Not Only SQL). Está diseñado para ser escalable, flexible y fácil de usar. En lugar de almacenar datos en tablas con filas y columnas, como en las bases de datos relacionales tradicionales, MongoDB almacena datos en documentos BSON (Binary JSON) dentro de colecciones.<br>

Las colecciones serían el homologo a tablas en SQL.

Algunas de las ventajas de MongoDB incluyen:

- Modelo de Datos Flexible.
- Escalabilidad Horizontal.
- Alto Rendimiento.
- Replicación y Alta Disponibilidad.
- Admite Consultas Avanzadas. 
- Soporte para Indexación.

<br>[Volver al Índice](#Índice)

# Crear Conexiones en mongoDB Compass

Se puede hacer con una el Uniform Resource Identifier (URI) o rellenando los campos. Tambien se puede crar la conexion en el servidor local o en un servidor externo con mongodb ATLAS.

Al intentar crer una nueva conexión por defecto intenta establecer la conexión con el servidor local.

<p align="center">
<img src="images/local.png"  height=300>
</p>

En el caso anterior se está creando la conexión local utilizando la URI, luego de esto se puede salvar la conexión y asignarle un color, para mayor facilidad.

Para el siguiente caso se está mostrando que se debe entrar en las opciones avanzadas de conexión para rellenar **Host** en **General**, **Username** y **Password** en **Authentication** y luego **Replica Set Name** en **advance**.

<p align="center">
<img src="images/atlas.png"  height=350>
</p>


## Datos conexión

### URI Servidor local: 
- mongodb://localhost:27017/
<br>

### URI Conexión de Práctica: 
- [mongodb://m001-student:m001-mongodb-basics@cluster0-shard-00-00-jxeqq.mongodb.net/?replicaSet=Cluster0-shard-0&tls=true](mongodb://m001-student:m001-mongodb-basics@cluster0-shard-00-00-jxeqq.mongodb.net/?replicaSet=Cluster0-shard-0&tls=true)
<br>

### Datos a Rellenar Conexión de Práctica:
Hostname: cluster0-shard-00-00-jxeqq.mongodb.net<br>
Authentication: Username / Password<br>
Username: m001-student<br>
Password: m001-mongodb-basics<br>
Replica Set Name: Cluster0-shard-0<br>
Read Preference: Primary Preferred<br>
<br>

La conexión de práctica es una base de datos que consta de 13 colecciones.

<br>[Volver al Índice](#Índice)

# Crear Cluster mongoDB - ATLAS

Esto nos va ha facilitar hacer inserciones y modificaciones sobre bases de datos en una conexion remota.

Ir a la pagina de [mongoDB - Atlas](https://www.mongodb.com/es/lp/cloud/atlas/try4?utm_source=google&utm_campaign=search_gs_pl_evergreen_atlas_core_retarget-brand_gic-null_amers-all_ps-all_desktop_eng_lead&utm_term=mongodb%20atlas&utm_medium=cpc_paid_search&utm_ad=e&utm_ad_campaign_id=14412646314&adgroup=131761122132&cq_cmp=14412646314&gad_source=1&gclid=Cj0KCQjwztOwBhD7ARIsAPDKnkA3SerxVVe3vQyp7GRi1S5JYbAOIAaozkAcp4-kfOhkYi28hgf-S-4aAsY-EALw_wcB?utm_source=google&utm_campaign=search_gs_pl_evergreen_atlas_core_retarget-brand_gic-null_amers-all_ps-all_desktop_eng_lead&utm_term=mongodb%20atlas&utm_medium=cpc_paid_search&utm_ad=e&utm_ad_campaign_id=14412646314&adgroup=131761122132&cq_cmp=14412646314&gad_source=1&gclid=Cj0KCQjwztOwBhD7ARIsAPDKnkA3SerxVVe3vQyp7GRi1S5JYbAOIAaozkAcp4-kfOhkYi28hgf-S-4aAsY-EALw_wcB), crear una cuenta y luego escoger el servicio gratuito, en mi caso.

<p align="center">
<img src="images/free1.png"  height=450>
</p>


Luego sigue los pasos que te muestren, lo principal es la configuración del cluster, en mi caso utilicé AWS, en Virginia.

Al terminar faltaría configurar un usuario y una contraseña para acceder a la base de datos. esto se hace en Database Access, se debe colocar la opción de lectura y escritura para el usuario.

tambien sería útil por ser un práctica configurar la entrada para cualquier IP, esto ahorraría tiempo en configuración, esto se hace en Network Access

Luego en database y dando click a connect se puede obtener la URI para conectar con Compass y la shell de VS, sólo hay que cambiar <password> por la contraseña de usuario creada.

<br>[Volver al Índice](#Índice)

# Operadores

Es mejor tener claro primero los operadores, para poder hacer el filtrado más adelante. 


## Operadores de Lógicos

```mongoDB
// AND
{ $and: [ { <expression1> }, { <expression2> }, ... , { <expressionN> } ] }

// OR
{ $or: [ { <expression1> }, { <expression2> }, ... , { <expressionN> } ] }

// NOR - Lo contrario a la condicción OR
{ $nor: [ { <expression1> }, { <expression2> }, ... ,  { <expressionN> } ] }

// NOT
{ field: { $not: { <operator-expression> } } }

// Ejemplo
db.basedd.find( { $and: [ { year: 1998 }, { price: 10 } ] } )

```
<br>[Volver al Índice](#Índice)

## Comparación

```mongoDB
// Igual a
{ field: { $eq: <value> } }

// Mayor que
{ field: { $gt: value } }

// Menor que
{ field: { $lt: value } }

// Mayor o igual que
{ field: { $gte: value } }

// Menor o igual que
{ field: { $lte: value } }

// Devuelve documentos que cumplen con los valores específicos del arreglo
{ field: { $in: [<value1>, <value2>, ... <valueN> ] } }

// Devuelve documentos que NO cumplen con los valores específicos del arreglo
{ field: { $in: [<value1>, <value2>, ... <valueN> ] } }


// Devuelve los documentos en los que el valor especificado no es igual
{ $ne: value } }

// Ejemplo

```
<br>[Volver al Índice](#Índice)

## Elementos

```mongoDB

// Coincide con los documentos que tienen un campo especificado. Este operador
//tiene un valor booleano que puede ser true o false.

{ field: { $exists: <boolean> } } 


// Hace coincidir los documentos según el tipo de campo especificado. Es útil cuando 
//tienes datos muy desestructurados, o cuando los tipos de datos no son predecibles.

{ field: { $type: <BSON type> } }


// Hace coincidir con los documentos que contienen un campo de matriz con al menos un elemento 
//que coincide con todos los criterios de consulta especificados.

{ : { $elemMatch: { <query1>, <query2>, ... } } }

```

<br>[Volver al Índice](#Índice)

## Evaluación

```mongoDB
// Para hacer coincidir los documentos en los que el valor de un campo especificado 
//es igual al resto después de ser dividido por un valor especificado

{ field: { $mod: [ divisor, remainder ] } }



// busca un texto dentro del contenido del campo especificado, indexado con un índice 
//de texto

{  
  $text:  
    {  
      $search: <string>,  
      $language: <string>,  
      $caseSensitive: <boolean>,  
      $diacriticSensitive: <boolean>   
    }  
}



// Permite aprovechar las expresiones de agregación dentro del lenguaje de consulta

{ $expr: { <expression> } }



// Se usa para pasar una cadena que contenga una función completa de JavaScript o una
//expresión de JavaScript al sistema de consulta

{ $where: <string|JavaScript Code> }

```

<br>[Volver al Índice](#Índice)

## Indexación
```mongoDB

Es un proceso similar al de SQL, se usa para mejorar el rendimiento de la base de datos. Pueden ser índices simples y múltiples.

//Crear indexación con índice único para un campo.

db.coleccion.createIndex({field : value},{unique : true})

db.coleccion.getIndexes()

// Oculta la indexación

db.coleccion.hideIdex()
```

# Método de Cursores
```mongoDB
//

.sort()

//

.limit()

```


<br>[Volver al Índice](#Índice)

# Consulta de Datos (CRUD)

## Comandos Básicos y Proyección
```mongoDB


//Muestra las bases de datos

show dbs


//Posiciona el cursor en la coleccion pertinente

use coleccion


// asigna la referencia de la nueva base de datos (basedd) a la variable db

db = db.getSiblingDB("basedd")


//Muestra comandos mas usados

bd.help()



```

<br>[Volver al Índice](#Índice)

## Inserción
```mongoDB
//Insertar un documento

db.coleccion.insertOne({})


//Insertar varios documentos

db.coleccion.insertMany({})

```

<br>[Volver al Índice](#Índice)

## Lectura
```mongoDB
//Consultar una colección

db.coleccion.find()


// Consulta una coleccion, pero la muestra mas ordenada

db.coleccion.find().pretty()


// Devuleva el primer documento que encuentre que cumpla la condición

db.coleccion.findOne(query, projection, options)

```

<br>[Volver al Índice](#Índice)

## Actualización
```mongoDB
// Modifica un documento

db.coleccion.replaceOne()


// Modifica varios documentos

db.coleccion.updateOne()


db.coleccion.findAndModify({query:{ }, update:{ }, new : false })

```
<br>[Volver al Índice](#Índice)

## Borrado
```mongoDB
//Borra un documento

db.coleccion.deleteOne()


//Borra varios documentos

db.coleccion.deleteMany()

```

<br>[Volver al Índice](#Índice)

# Agregación
```mongoDB
Claro, aquí tienes un ejemplo de cómo usar las etapas de agregación en MongoDB, incluyendo $project, $match, $group, $set, $count y $out:

Supongamos que tienes una colección de "ventas" que contiene documentos con la siguiente estructura:

json
Copy code
{
    "_id": ObjectId("60b674e31234567890abcdef"),
    "producto": "Camiseta",
    "cantidad": 5,
    "precio_unitario": 20,
    "fecha": ISODate("2022-06-01T00:00:00Z"),
    "sucursal": "Sucursal_A"
}

db.ventas.aggregate([
    // Etapa $match para filtrar ventas después de cierta fecha
    { $match: { fecha: { $gte: ISODate("2022-01-01") } } },

    // Etapa $group para agrupar por producto y sucursal y calcular el total de ventas
    { $group: {
        _id: { producto: "$producto", sucursal: "$sucursal" },
        total_ventas: { $sum: { $multiply: ["$cantidad", "$precio_unitario"] } }
    } },

    // Etapa $project para darle un formato a los resultados
    { $project: {
        _id: 0,
        producto: "$_id.producto",
        sucursal: "$_id.sucursal",
        total_ventas: 1
    } },

    // Etapa $out para guardar los resultados en una nueva colección
    { $out: "ventas_totales_por_sucursal" }
])

//Explicación de las etapas de agregación:

$match: Filtra las ventas para incluir solo aquellas después de cierta fecha.
$group: Agrupa las ventas por producto y sucursal, y calcula el total de ventas para cada grupo.
$project: Da formato a los resultados, mostrando solo el producto, la sucursal y el total de ventas.
$out: Guarda los resultados en una nueva colección llamada "ventas_totales_por_sucursal".


```

<br>[Volver al Índice](#Índice)

# Prática de Comandos
```mongoDB
db.Peliculas.insertOne({year : 2023 , title : "The Little Mermaid" , director : "Rob Marshall" })


db.Peliculas.insertMany([
  {title:"Kung Fu Panda 4", year:2024, director:"Mike Mitchell"},
  {title:"Karate Kid",      year:2024, director:"Jonathan Entwistle"}
                        ]) 

Revisar si se agregarondb.
db.Peliculas.find({ _id:ObjectId('66266b7716622642e49f990b') } )

db.Peliculas.find({year:2024},{year:1, title:1}) 

varios ejemplos de find, con distintos operadores, incluyendo cursores

db.Peliculas.find({year:2024},{year:1, title:1}).sort({title:1})

db.Peliculas.find({year:1999},{_id:0,year:1,title:1}).limit(3)

Ejemplo de modificar un archivo
ejemplo de modificar varios archivos

borrado de un archivo
borrado de varios archivos

ejemplos de agregacion

ejemplos de indexacion







```

<br>[Volver al Índice](#Índice)

# Tegnologías Utilizadas
- mongoDb - Version 7.0.7
- mongoDB Compass - Version 1.42.3
- mongoDB Shell - Version 2.2.2
- Visual Studio - Version 1.88.0
- Visulal Studio - Estension MongoDB for VS - V.1.5.0


<br>[Volver al Índice](#Índice)

# Autor
- José R. Guignan
- Mail: joserguignan@gmail.com
- Linkedin: [https://www.linkedin.com/in/jrguignan](https://www.linkedin.com/in/jrguignan)
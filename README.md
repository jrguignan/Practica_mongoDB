# Práctica mongoDB <img src="https://github.com/Anmol-Baranwal/Cool-GIFs-For-GitHub/assets/74038190/398b19b1-9aae-4c1f-8bc0-d172a2c08d68" width="50"> - En Construcción 🚧

<p align="center">
<img src="images/mongodb.png"  height=150>
</p>

# Índice
* [mongoDB](#mongoDB)
* [Crear Conexiones en mongoDB Compass](#Crear-Conexiones-en-mongoDB-Compass)
* [Crear Base de Datos en mongoDB - ATLAS](#Crear-Base-de-Datos-en-mongoDB---ATLAS)
* [Consulta de Datos (CRUD)](#Consulta-de-Datos-(CRUD))
* [Operadores de Consultas](#Operadores-de-Consultas)
* [Tegnologías Utilizadas](#Tegnologías-Utilizadas)
* [Autor](#Autor)


# mongoDB

Es un sistema de gestión de bases de datos de código abierto y orientado a documentos, que se clasifica dentro de la categoría de bases de datos NoSQL (Not Only SQL). Está diseñado para ser escalable, flexible y fácil de usar. En lugar de almacenar datos en tablas con filas y columnas, como en las bases de datos relacionales tradicionales, MongoDB almacena datos en documentos BSON (Binary JSON) dentro de colecciones.<br>

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
<img src="images/local.png"  height=400>
</p>

En el caso anterior se está creando la conexión local utilizando la URI, luego de esto se puede salvar la conexión y asignarle un color, para mayor facilidad.

Para el siguiente caso se está mostrando que se debe entrar en las opciones avanzadas de conexión para rellenar **Host** en **General**, **Username** y **Password** en **Authentication** y luego **Replica Set Name** en **advance**.

<p align="center">
<img src="images/atlas.png"  height=500>
</p>


## Datos conexión

### URI Servidor local: 
mongodb://localhost:27017/
<br>

### URI Conexión de Práctica: 
mongodb://m001-student:m001-mongodb-basics@cluster0-shard-00-00-jxeqq.mongodb.net/?replicaSet=Cluster0-shard-0&tls=true
<br>

### Datos a Rellenar Conexión de Práctica:
Hostname: cluster0-shard-00-00-jxeqq.mongodb.net
Authentication: Username / Password
Username: m001-student
Password: m001-mongodb-basics
Replica Set Name: Cluster0-shard-0
Read Preference: Primary Preferred
<br>

La conexión de practica es una base de datos que consta de 

<br>[Volver al Índice](#Índice)

# Crear Base de Datos en mongoDB - ATLAS



<br>[Volver al Índice](#Índice)

# Consulta de Datos (CRUD)

```mongoDB

```

# Operadores de Consultas

```mongoDB

```


<br>[Volver al Índice](#Índice)

# Tegnologías Utilizadas
- mongoDb - Version 7.0.7
- mongoDB Compass - Version 1.42.3
- mongoDB Shell - Version 2.2.2
- Visual Studio - Version 1.88.0
- Visulal Studio - Estension MongoDv for VS - V.1.5.0


<br>[Volver al Índice](#Índice)

# Autor
- José R. Guignan
- Mail: joserguignan@gmail.com
- Linkedin: [https://www.linkedin.com/in/jrguignan](https://www.linkedin.com/in/jrguignan)
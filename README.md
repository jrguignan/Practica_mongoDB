# Práctica mongoDB <img src="https://github.com/Anmol-Baranwal/Cool-GIFs-For-GitHub/assets/74038190/398b19b1-9aae-4c1f-8bc0-d172a2c08d68" width="50"> - En Construcción 🚧

<p align="center">
<img src="images/mongodb.png"  height=150>
</p>

# Índice
* [mongoDB](#mongoDB)
* [Crear Conexiones en mongoDB Compass](#Crear-Conexiones-en-mongoDB-Compass)
* [Crear Cluster mongoDB - ATLAS](#Crear-Cluster-mongoDB---ATLAS)
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

La conexión de practica es una base de datos que consta de: 13 colecciones.

<br>[Volver al Índice](#Índice)

# Crear Cluster mongoDB - ATLAS

Esto nos va ha facilitar hacer inserciones y modificaciones sobre bases de datos en una conexion remota.

Ir a la pagina de [mongoDB - Atlas](https://www.mongodb.com/es/lp/cloud/atlas/try4?utm_source=google&utm_campaign=search_gs_pl_evergreen_atlas_core_retarget-brand_gic-null_amers-all_ps-all_desktop_eng_lead&utm_term=mongodb%20atlas&utm_medium=cpc_paid_search&utm_ad=e&utm_ad_campaign_id=14412646314&adgroup=131761122132&cq_cmp=14412646314&gad_source=1&gclid=Cj0KCQjwztOwBhD7ARIsAPDKnkA3SerxVVe3vQyp7GRi1S5JYbAOIAaozkAcp4-kfOhkYi28hgf-S-4aAsY-EALw_wcB?utm_source=google&utm_campaign=search_gs_pl_evergreen_atlas_core_retarget-brand_gic-null_amers-all_ps-all_desktop_eng_lead&utm_term=mongodb%20atlas&utm_medium=cpc_paid_search&utm_ad=e&utm_ad_campaign_id=14412646314&adgroup=131761122132&cq_cmp=14412646314&gad_source=1&gclid=Cj0KCQjwztOwBhD7ARIsAPDKnkA3SerxVVe3vQyp7GRi1S5JYbAOIAaozkAcp4-kfOhkYi28hgf-S-4aAsY-EALw_wcB) y crear una cuenta, en mi caso gratis.

<p align="center">
<img src="images/free1.png"  height=450>
</p>


Luego sigue los pasos que te muestren, loprincipal es la configuración del cluster, en mi caso utilicé AWS, en Virginia.

Al terminar faltaría configurar un usuario y una contraseña para acceder a la base de datos. esto se hace en Database Access, se debe colocar la opción de lectura y escritura para el usuario.

tambien sería útil por ser un práctica configurar la entrada para cualquier IP, esto ahorraría tiempo en configuración, esto se hace en Network Access

Luego en database y dando click a connect se puede obtener la URI para conectar con Compass y la shell de VS, sólo hay que cambiar <password> por la contraseña de usuario creada.

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
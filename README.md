# Proyecto_III_Microservices

# Web application:
Es un container que ejecuta Apache Httpd. En este Web Server, se ejecuta una aplicación web escrita en
React JS. La aplicación es sumamente sencilla. Provee una tabla que lista archivos almacenados en la base
de datos. Permite subir/descargar archivos y mantener su metadata: Nombre, descripción, fecha de
creación, última actualización y usuario que lo crea. Como puede notar, la solución tiene un componente de
autorización y autenticación. Es decir, debe solicitar login al usuario. No todos los usuarios pueden subirarchivos, solo los que tengan ciertos permisos.

El archivo se guarda en una tabla de la base de datos del container de File Storage junto con su metadata.
El archivo se comprime mediante el servicio provisto por el microservicio de compresión.
Para la interfaz gráfica se recomienda utilizar los componentes de Material UI de Google para React.

# Authentication & Authorization:
Es un container que provee un REST API que se ejecuta en NodeJS y que se alimenta de un XML que
contiene la lista de usuarios y sus permisos. La aplicación web se comunica directamente por HTTP con
este container.

# Compression Microservice
Es un container que ejecuta un Spring Boot. A este microservicio se le envía un stream de datos y lo retorna
comprimido utilizando Huffman.

# FileStorage API
Es un microservicio que interactúa con un motor de bases de datos MySQL. Se compone de dos containers:
el container de la base de datos MySQL y el container que ejecuta Liberty para el API en Java.

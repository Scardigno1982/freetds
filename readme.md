# Guía de Instalación y Conexión a SQL Server 2000 desde Ubuntu 22.04

Esta guía te mostrará cómo conectar Ubuntu 22.04 a una base de datos SQL Server 2000 utilizando FreeTDS. Sigue estos sencillos pasos para lograrlo.

## Instalación de FreeTDS

1. Abre una terminal en tu sistema Ubuntu 22.04.

2. Ejecuta el siguiente comando para buscar los paquetes relacionados con iODBC y FreeTDS:

   ```bash
   bash# apt-cache search iodbc

bash# apt-get install iodbc

Configuración de FreeTDS
Abre el archivo de configuración freetds.conf en un editor de texto. Puedes utilizar nano, por ejemplo:

nano /etc/freetds/freetds.conf

Agrega una sección para tu servidor SQL Server 2000 de la siguiente manera:

# A typical Microsoft server
[egServer73]
        host = 192.168.0.0
        port = 1433
        tds version = 7.3


Asegúrate de cambiar la información de host, puerto y versión TDS según tu configuración.

Guarda y cierra el archivo freetds.conf.

Realizando la Conexión
Para conectarte a tu base de datos SQL Server 2000 desde la terminal, utiliza el siguiente comando:

tsql -S egServer73 -U user -P password -D nombre_base_datos

Asegúrate de reemplazar egServer73, user, password y nombre_base_datos con tus propias credenciales y nombre de base de datos.

¡Eso es todo! Ahora puedes conectarte y trabajar con tu base de datos SQL Server 2000 desde Ubuntu 22.04 utilizando FreeTDS.

¡Buena suerte y feliz conexión!

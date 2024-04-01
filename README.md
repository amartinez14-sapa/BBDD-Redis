# Instalación y Configuración de Sistemas Gestores de Bases de Datos (SGBD)

## Índice
1. [Introducción](#introducción)
2. [Sistemas Gestores de Bases de Datos](#sistemas-gestores-de-bases-de-datos)
3. [Descripción del SGBD Elegido: Redis](#descripción-del-sgbd-elegido-redis)
    - [Historia y Soporte](#historia-y-soporte)
    - [Casos de Uso Recomendados](#casos-de-uso-recomendados)
    - [Versiones de la Solución](#versiones-de-la-solución)
    - [Comparación con Otros SGBD](#comparación-con-otros-sgbd)
4. [Documentación de Instalación](Instalacion_redis.md)
    - [Requisitos](#requisitos)
    - [Securización de la Instalación](#securización-de-la-instalación)
    - [Instrucciones de Arranque, Verificación de Estado y Apagado del Servicio](#instrucciones-de-arranque-verificación-de-estado-y-apagado-del-servicio)
    - [Ubicación y Nombre del Archivo de Configuración](#ubicación-y-nombre-del-archivo-de-configuración)
    - [Puertos de Escucha del Servicio](#puertos-de-escucha-del-servicio)
    - [Conexión a la Base de Datos](#conexión-a-la-base-de-datos)
5. [Entrega](#entrega)

## Introducción

El presente proyecto tiene como objetivo analizar uno de los sistemas gestores de bases de datos más utilizados en la actualidad. Se abordarán las tareas necesarias para la instalación y configuración del SGBD elegido, así como la preparación de una presentación para explicar los aspectos más relevantes del mismo.

Este proyecto se puede realizar en grupos de dos o tres alumnos.

## Sistemas Gestores de Bases de Datos

Se pueden seleccionar entre los siguientes sistemas gestores de bases de datos:

- In-Memory Databases: Redis, Memcached
- Spatial Databases: PostGis
- Time-Series Databases: InfluxDB, Prometheus
- Graph databases: Neo4j
- Distributed databases: Apache Cassandra
- Relational Databases: SqlServer, Oracle

## Descripción del SGBD Elegido: Redis

### Historia y Soporte

Redis fue iniciado por Salvatore Sanfilippo, también conocido como "Antirez", en 2009. Su desarrollo ha sido respaldado por la comunidad de código abierto, así como por empresas como Redis Labs. Para obtener más información sobre la historia de Redis, consulte la [entrevista con Salvatore Sanfilippo](https://eu-startups.com/interview-with-redis-creator-salvatore-sanfilippo-who-works-in-sicily/).

### Casos de Uso Recomendados

Redis es ideal para casos de uso que requieran alta velocidad, caché en memoria, almacenamiento de sesiones, mensajes en espera y análisis en tiempo real. Algunos ejemplos de estos casos de uso son la segmentación en tiempo real en redes sociales, almacenamiento de datos de sesiones en aplicaciones móviles y gestión de inventarios en el comercio electrónico.

### Versiones de la Solución

- Community Edition: Gratuita y de código abierto, adecuada para proyectos pequeños o medianos.
- Enterprise Edition: Versión comercial con funciones avanzadas y soporte.
- Redis Cloud: Servicios gestionados en la nube para escalabilidad y mantenimiento automatizado.

### Comparación con Otros SGBD

Redis destaca por su rendimiento en tiempo real, modelo de datos en memoria, diversidad de estructuras de datos, escalabilidad y disponibilidad.

## Documentación de Instalación

### Requisitos

- Paquetes necesarios: `lsb-release`, `curl`, `gpg`
- Obtener la clave de firma de paquetes de Redis
- Añadir el repositorio de Redis
- Actualizar las listas de paquetes
- Instalar Redis

### Securización de la Instalación

Por defecto, Redis bloquea el acceso remoto a la base de datos. Para modificar esta configuración, se deben seguir los siguientes pasos.

### Instrucciones de Arranque, Verificación de Estado y Apagado del Servicio

- Arrancar el servicio: `systemctl start redis`
- Verificar el estado del servicio: `systemctl status redis`
- Apagar el servicio: `systemctl stop redis`

### Ubicación y Nombre del Archivo de Configuración

El archivo de configuración de Redis se encuentra en `/etc/redis/redis.conf`.

### Puertos de Escucha del Servicio

Por defecto, Redis escucha en el puerto 6379. Para cambiar este puerto, se deben realizar modificaciones en el archivo de configuración.

### Conexión a la Base de Datos

Para conectarse a Redis, se puede utilizar una herramienta de gestión de bases de datos o un programa que admita Redis.

## Entrega

- Identificación de los miembros del grupo.
- Documentación de instalación completa.
- Capturas de imágenes pertinentes y referencias bibliográficas.

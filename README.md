# Rhythm of Lockdown: A Pandemic Analysis

## **¿Cómo cambió nuestro ritmo durante el confinamiento?** 

Análisis de tendencias musicales (2018-2022): pre-pandemia, pandemia y post-pandemia
La elección de este rango de años tiene el propósito de obtener una muestra sobre cómo fueron las tendencias musicales en torno a la pandemia de COVID-19 y, con estos datos, invitar a una pequeña reflexión acerca de cómo impactan los eventos de carácter mundial en las necesidades e intereses musicales de las personas.

Extracción, limpieza y creación de BBDD en MySQL para jerarquizar los resultados a partir de datos obtenidos a través de las APIS de Spotify y last.fm.



## Índice

1. [El Proyecto](#1-el-proyecto)
2. [Stack Tecnológico](#2-stack-tecnológico)
3. [Guía de Uso y Configuración](#3-guía-de-uso-y-configuración)
4. [Estructura del repositorio](#2-estructura-del-repositorio)
5. [Fuente de los datos](#3-fuente-de-los-datos)
6. [Esquema de la base de datos](#5-esquema-de-la-base-de-datos)
7. [Autoras y metodología](#7-autoras-y-metodología)


# 1. El Proyecto

Este análisis nace de la curiosidad por entender cómo eventos de carácter mundial impactan en las necesidades e intereses musicales de las personas. 

Mediante la **extracción, limpieza y creación de bases de datos**, analizamos las tendencias en tres etapas críticas:
* **Pre-pandemia (2018-2019):** El ritmo habitual.
* **Lockdown (2020-2021):** El sonido del aislamiento.
* **Post-pandemia (2022):** La nueva normalidad sonora.

El objetivo es ofrecer una reflexión sobre el consumo cultural y proporcionar una **infraestructura de código escalable** para explorar otros rangos temporales.


## 2. Stack Tecnológico

* **Lenguaje:** Python 3.8+ 
* **Base de Datos:** MySQL Workbench 
* **Librerías principales:**
    * `pandas` (Tratamiento y limpieza de datos)
    * `spotipy` (Conexión API Spotify)
    * `python-dotenv` (Gestión de credenciales seguras)


## 3. Guía de Uso y Configuración
### Instrucciones para usar python-dotenv (una librería que permite cargar variables de entorno desde un archivo *.env* a tu código Python)

1. Instala *python-dotenv*
2. Crea un archivo *.env* en la misma **carpeta** que el *.ipynb* donde vas a usar tus credenciales.
3. Escribe en él:

    `CLIENT_ID = tu_client_id_de_spotify`
    `CLIENT_SECRET=tu_client_secret_de_spotify`

4. Crea un archivo *.gitignore* en la raíz (*main*), si ya existe, comprueba que el siguiente paso está contenido en él.
5. Escribe dentro *`.env`* (así evitamos que GitHub suba el archivo con nuestras credenciales personales al repositorio, permanecerá localmente en nuestra carpeta en el ordenador).
6. Guarda **estos dos archivos** y ejecuta las instrucciones siguientes en el *.ipynb* donde quieras usar tu credencial de API.

7. Tendrás que importar la nueva librería:

        from dotenv import load_dotenv
        import os

8. Ejecutar *dotenv*:

        load_dotenv()  # carga nuestras claves
        safeclient_id = os.getenv("CLIENT_ID")
        safeclient_secret = os.getenv("CLIENT_SECRET")

    Ya puedes sustituir tus credenciales por estas nuevas variables (en el caso de este ejemplo *safeclient_id* y *safeclient_secret*) y ejecutar tu código.

### Instrucciones para replicar el proyecto:
**Clona este repositorio:**

    git clone https://github.com/andrearvirgos/Rhythm-of-Lockdown-Pandemic-Analysis.git

Es recomendable tener cuenta de desarrollador en [Spotify](https://developer.spotify.com/) para obtener `CLIENT_ID` y `CLIENT_SECRET` (las credenciales para el uso de la API) para poder ejecutar una nueva extracción de datos.


## 4. Estructura del repositorio

        este_repositorio/
        |
        ├── extracción-spotify-spotipy             # Notebooks organizados por género
        │   ├── country/
        │   ├── metal/
        │   ├── pop/
        │   ├── r&b/
        │   └── rock/
        |
        ├── extracción-last.fm/                    # Scripts de apoyo y cruce con Last.fm
        ├── working_agreement.md                   # Protocolo de trabajo en equipo (SCRUM)
        └── README.md                              # Documentación principal



## 5. Fuente de los datos

Los datos han sido obtenidos mediante el consumo de las APIs oficiales de las plataformas musicales más relevantes, garantizando la fiabilidad de las métricas de popularidad y metadatos:

* **[Spotify for Developers](https://developer.spotify.com/documentation/web-api/):** Utilizada para la extracción de métricas de popularidad, ID de pistas y categorización por géneros.
* **[Last.fm API](https://www.last.fm/api):** Utilizada como fuente complementaria para el cruce de datos y el análisis de tendencias de escucha global.

> **Fecha de obtención:** Octubre de 2025.


## 6. Esquema de la base de datos

La información se jerarquiza en una base de datos relacional diseñada para optimizar las consultas por año y género.


## 7. Autoras y metodología
Este proyecto ha sido desarrollado bajo la metodología ágil **SCRUM**, aplicando un flujo de trabajo colaborativo para la gestión de tareas y control de versiones.

* 👩‍💻 **Violeta**
* 👩‍💻 **María Gómez** 
* 👩‍💻 **Micaela Lafratta** 
* 👩‍💻 **Ona Z. Fernández** 
* 👩‍💻 **Andrea R. Virgós** 


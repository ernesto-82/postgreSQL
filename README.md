# Practica 1 - PostgreSQL con Docker Compose

Despliegue de PostgreSQL 16 en Docker Compose con:

-Docker Secrets (POSTGRES_PASSWORD_FILE)
-Volumenes nombrados para datos y logs
-Red Bridge personalizada
-Configuración Core personalizada
-Auditoria slow queries (>2s)
-Aislamiento Perimetral (listen_addresses=localhost)

## Video explicativo

-Enlace al video de la nube https://drive.google.com/file/d/167gKYWRUmEa16tQ8gkZATw-zKg7lMnTY/view?usp=sharing

## Infraestructura del proyecto

-docker-compose.yml: definicion de servicios
-.gitignore: proteccion de contraseñas (no sube el directorio seguridad/)
-seguridad/: contiene el secret (no se sube a github)
-config/: configuracion de referencia

## Como levantar el proyecto

-docker compose up -d
-docker compose ps -a

## Como conectarse (desde dentro del contenedor)

-docker exec -it postgres01 psql -U admin -d practica01

## Informacion util

-La contraseña se almacena y se lee desde /run/secrets/postgres_password
-Logs almacenados en el volumen nombrado postgres01_logs01
-Con listen_addresses=localhost, el motor de la base de datos solo acepta conexiones internas
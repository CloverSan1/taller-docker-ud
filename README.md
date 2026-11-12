# Taller Docker Desktop y GitHub Actions - Universidad Distrital

Proyecto mínimo de ejemplo. No requiere instalar Python en el computador: Docker incluye
el intérprete en la imagen `python:3.13-slim`.

## Ejecución local

Desde esta carpeta, con Docker Desktop iniciado:

```shell
docker build -t ud-docker-taller:1.0 .
docker run -d --name ud-taller -p 8080:8000 -e APP_VERSION=1.0 ud-docker-taller:1.0
```

Visitar: http://localhost:8080/ y http://localhost:8080/health

Detener y borrar: `docker rm -f ud-taller`

## GitHub Actions

Subir `app.py`, `Dockerfile`, `.dockerignore` y `.github/workflows/docker-ci.yml`
a la rama principal de un repositorio de GitHub. Abrir la pestaña `Actions`.
El workflow crea la imagen y prueba `/health` en un runner temporal de GitHub.
No sube nada a Docker Hub y no utiliza contraseñas ni tokens adicionales.

Más instrucciones y conceptos en el documento Word entregado con el taller.

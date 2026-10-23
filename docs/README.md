---
## Flujo completo
```markdown
## Build y Despliegue
Sigue estos pasos en orden para compilar y levantar la aplicación completa:

## Compilar frontend (Angular)
Genera los archivos estáticos del frontend en `dist/`:
```bash
ng build 

## Compilar Backend (MAVEN)
Genera el artefacto .jar del backend:
mvn clean package

## Limpiar entorno Docker
Detiene los contenedores en ejecución:
docker compose down
docker compose down -v ##Elimina también los volúmenes asociados (borra datos persistentes):

## Reconstruir imágenes
Reconstruye todas las imágenes Docker sin usar caché:
docker compose build --no-cache

## Levantar servicios
Inicia todos los servicios definidos en docker-compose.yml:
docker compose up

## Datos adicionales
Para que funcione en localhost se debe quitar o comentar la linea 13: SET transaction_timeout = 0; de V1__init.sql en el backend

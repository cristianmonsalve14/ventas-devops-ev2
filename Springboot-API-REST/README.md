# Springboot-API-REST-VENTAS

Microservicio Spring Boot para la gestión de ventas. Permite registrar, consultar, actualizar y eliminar información de ventas, integrándose con otros servicios del sistema.

## Características
- API RESTful para operaciones CRUD de ventas.
- Conexión a base de datos MySQL.
- Documentación Swagger.
- Listo para desarrollo local y despliegue en Docker.


## Requisitos previos
- Java 21
- Maven 3.8+
- Docker
- Git

## Ejecución con Docker

1. Construye la imagen Docker:
   ```sh
   docker build -t ventas-backend .
   ```
2. Ejecuta el contenedor:
   ```sh
   docker run -d -p 8088:8088 \
     -e SPRING_DATASOURCE_URL="<jdbc_url>" \
     -e SPRING_DATASOURCE_USERNAME="<usuario>" \
     -e SPRING_DATASOURCE_PASSWORD="<contraseña>" \
     ventas-backend
   ```
   El backend estará disponible en: [http://localhost:8088](http://localhost:8088)

## Variables de entorno importantes
Debes definir las variables de entorno para la conexión a la base de datos al ejecutar el contenedor:
- `SPRING_DATASOURCE_URL`
- `SPRING_DATASOURCE_USERNAME`
- `SPRING_DATASOURCE_PASSWORD`

## Endpoints principales
- `GET /api/ventas` — Listar todas las ventas
- `GET /api/ventas/{id}` — Obtener una venta por ID
- `POST /api/ventas` — Crear una nueva venta
- `PUT /api/ventas/{id}` — Actualizar una venta existente
- `DELETE /api/ventas/{id}` — Eliminar una venta

## Documentación Swagger
- [http://localhost:8088/swagger-ui.html](http://localhost:8088/swagger-ui.html)

## Notas
- Si ves un error 404 en la raíz (`/`), es normal: la API no sirve archivos estáticos, solo endpoints REST.
- Asegúrate de que el puerto 3306 esté libre antes de levantar los servicios.

## Despliegue y DevOps
- Incluye Dockerfile con multi-stage build listo para producción.
- Configurado para despliegue automatizado mediante GitHub Actions.
- Puedes usar este repositorio en pipelines CI/CD para construir y desplegar automáticamente en AWS EC2.

---

## Cómo contribuir
1. Haz tus cambios en una rama nueva.
2. Realiza commit con mensajes claros.
3. Haz push y crea un Pull Request.

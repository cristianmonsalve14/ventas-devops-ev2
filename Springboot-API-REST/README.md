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
- Docker y Docker Compose
- Git

## Ejecución con Docker Compose

1. Construye la imagen y levanta los servicios:
   ```sh
   docker-compose up --build
   ```
2. El backend estará disponible en: [http://localhost:8088](http://localhost:8088)

## Variables de entorno importantes
Las credenciales y URL de la base de datos se configuran automáticamente en docker-compose.yml.

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
- Incluye Dockerfile y docker-compose.yml listos para producción.
- Puedes usar este repositorio en pipelines CI/CD para construir y desplegar automáticamente.

---

## Cómo contribuir
1. Haz tus cambios en una rama nueva.
2. Realiza commit con mensajes claros.
3. Haz push y crea un Pull Request.

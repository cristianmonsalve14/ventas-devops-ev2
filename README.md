# ventas-devops-ev2

Microservicio Spring Boot para la gestión de ventas. Permite registrar, consultar, actualizar y eliminar información de ventas, integrándose con otros servicios del sistema.

## Características

- API RESTful para operaciones CRUD de ventas.
- Conexión a base de datos MySQL.
- Documentación interactiva con Swagger.
- Configuración lista para desarrollo local y despliegue en contenedores.

## Requisitos previos

- Java 21
- Maven 3.8+
- MySQL 8+
- Git

## Instalación y ejecución

1. **Clona el repositorio:**
   ```sh
   git clone https://github.com/tu_usuario/ventas-devops-ev2.git
   cd ventas-devops-ev2

   2. **Configura la base de datos:**
   - Crea la base de datos y el usuario en MySQL:
     ```sql
     CREATE DATABASE IF NOT EXISTS ventas_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
     CREATE USER IF NOT EXISTS 'ventas_user'@'localhost' IDENTIFIED WITH mysql_native_password BY 'tu_contraseña';
     GRANT ALL PRIVILEGES ON ventas_db.* TO 'ventas_user'@'localhost';
     FLUSH PRIVILEGES;
     ```
   - Edita `src/main/resources/application.properties` con tus credenciales.

3. **Compila y ejecuta la aplicación:**
   ```sh
   ./mvnw clean install
   ./mvnw spring-boot:run

   4. **Accede a la documentación Swagger:**
   - [http://localhost:8088/swagger-ui.html](http://localhost:8088/swagger-ui.html)


## Ejecución con Docker

### Build de la imagen Docker

Desde la carpeta `Springboot-API-REST`:

```sh
docker build -t ventas-backend .
```

Luego, ejecuta el contenedor con las variables de entorno necesarias para conectarse a la base de datos.
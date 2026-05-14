# Etapa de build
FROM eclipse-temurin:21-jdk AS builder
WORKDIR /app
COPY . .
RUN chmod +x ./mvnw && \
    ./mvnw clean package -DskipTests && \
    rm -rf ~/.m2/repository

# Etapa de producción
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY --from=builder /app/target/Springboot-API-REST-0.0.1-SNAPSHOT.jar app.jar

# Variables de entorno para la base de datos (pueden ser sobreescritas en tiempo de ejecución)
ENV SPRING_DATASOURCE_URL="${SPRING_DATASOURCE_URL}"
ENV SPRING_DATASOURCE_USERNAME="${SPRING_DATASOURCE_USERNAME}"
ENV SPRING_DATASOURCE_PASSWORD="${SPRING_DATASOURCE_PASSWORD}"

EXPOSE 8088
USER 1000
ENTRYPOINT ["java", "-jar", "app.jar"]

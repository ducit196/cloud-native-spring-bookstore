FROM openjdk:17-jdk as builder
WORKDIR /app
COPY . /app
RUN ./mvnw package -DskipTests

FROM openjdk:17-slim
WORKDIR /app
COPY --from=builder /app/target/catalog-service-0.0.1-SNAPSHOT.jar /app/catalog-service.jar
CMD ["java", "-jar", "catalog-service.jar"]

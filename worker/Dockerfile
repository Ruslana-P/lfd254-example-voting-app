# Stage 0: Build the application
FROM maven:3.9-eclipse-temurin-11 AS build
WORKDIR /code
COPY . .
RUN mvn package -DskipTests
# Stage 1: Create the runtime image
FROM eclipse-temurin:11-jre AS run
WORKDIR /run
COPY --from=build /code/target/worker-jar-with-dependencies.jar worker.jar
CMD ["java", "-jar", "worker.jar"]

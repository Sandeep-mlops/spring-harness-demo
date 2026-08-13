# Stage 1: Build the Spring Boot application
FROM eclipse-temurin:17-jdk AS builder
WORKDIR /source
# Copy the project files into the container
COPY . .
# Grant execution rights and build the jar natively inside Docker
RUN chmod +x gradlew
RUN ./gradlew clean bootJar -x test

# Stage 2: Create the lightweight production image
FROM eclipse-temurin:17-jre
WORKDIR /app
# Pull the exact compiled jar from the builder stage
COPY --from=builder /source/build/libs/app.jar app.jar
# Expose the port
EXPOSE 8080
# Start the application
CMD ["java", "-jar", "app.jar"]

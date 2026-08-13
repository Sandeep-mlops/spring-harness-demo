# Use a lightweight Java 17 runtime image
FROM eclipse-temurin:17-jre

# 1. Create and move into a working directory
WORKDIR /app

# 2. Copy the entire contents of the libs folder into /app
COPY build/libs/ ./

# Expose the port your Spring Boot app runs on
EXPOSE 8080

# 3. Let the Linux shell dynamically find and execute the JAR
CMD ["sh", "-c", "java -jar *.jar"]

# Use OpenJDK base image
FROM openjdk:17-jdk-slim

# Create working directory
WORKDIR /app

# Copy your built jar from Maven into container
COPY target/BankingSystem-1.0-SNAPSHOT.jar app.jar

# Expose port
EXPOSE 8080

# Run the app
ENTRYPOINT ["java", "-jar", "app.jar"]

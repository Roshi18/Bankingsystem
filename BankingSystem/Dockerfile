# Use OpenJDK image
FROM openjdk:17-jdk-slim

# Copy source
COPY target/BankingSystem-*.jar app.jar

# Run the jar file
ENTRYPOINT ["java", "-jar", "/app.jar"]

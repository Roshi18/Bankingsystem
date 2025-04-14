# Step 1: Use a base image with Maven
FROM maven:3.8.6-openjdk-17-slim AS builder

# Step 2: Set the working directory
WORKDIR /app

# Step 3: Copy the pom.xml and install dependencies
COPY BankingSystem/pom.xml .

# Step 4: Download dependencies
RUN mvn dependency:go-offline

# Step 5: Copy the source code into the container
COPY BankingSystem/src /app/src

# Step 6: Package the application
RUN mvn clean package -DskipTests

# Step 7: Create the runtime image
FROM openjdk:17-jdk-slim

# Step 8: Set the working directory
WORKDIR /app

# Step 9: Copy the packaged .jar file from the builder image
COPY --from=builder /app/target/BankingSystem-1.0-SNAPSHOT.jar /app/app.jar

# Step 10: Expose the port the app will run on
EXPOSE 8080

# Step 11: Define the entry point for the container
ENTRYPOINT ["java", "-jar", "/app/app.jar"]

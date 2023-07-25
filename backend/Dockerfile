# Use the official OpenJDK image as the base image
FROM openjdk:17

# Set the working directory inside the container
WORKDIR /app

# Copy the JAR file to the working directory
COPY target/cryptotracker-0.0.1-SNAPSHOT.jar app.jar

# Expose the port your Spring Boot app is listening on
EXPOSE 8080

# Define the command to run your application
CMD ["java", "-jar", "app.jar"]

# Use the official Node.js image as the base image
FROM node:16 as builder

# Set the working directory inside the container
WORKDIR /app

# Copy the package.json and package-lock.json to the working directory
COPY package*.json ./

# Install Angular CLI
RUN npm install -g @angular/cli

# Install the Angular project dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Build the Angular app
RUN ng build --configuration production

# Use a lightweight web server to serve the Angular app
FROM nginx:alpine

# Copy the built Angular app from the previous stage
COPY --from=builder /app/dist/defi-frontend /usr/share/nginx/html

# Expose the default Nginx port
EXPOSE 80

# Start Nginx to serve the Angular app
CMD ["nginx", "-g", "daemon off;"]

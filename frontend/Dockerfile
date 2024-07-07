# Stage 1: Build the React app
FROM node:19.5.0-alpine AS builder

# Set the working directory to /app
WORKDIR /app

# Copy the package.json and package-lock.json files to the working directory
COPY package.json package-lock.json ./

# Install the dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .

# Build the app for production
RUN npm run build

# Stage 2: Serve the React app with Nginx
FROM nginx:alpine

# Copy the build output to the Nginx html directory
COPY --from=builder /app/dist /usr/share/nginx/html

# Expose the port that the app runs on
EXPOSE 80

# Run Nginx
CMD ["nginx", "-g", "daemon off;"]

# Use Node LTS base image
FROM node:18-alpine

# Set working directory inside container
WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy source files
COPY ..

# Expose backend port
EXPOSE 3400

# Start the server
CMD ["npm", "start"]

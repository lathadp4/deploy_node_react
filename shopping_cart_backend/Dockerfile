# Use Node.js base image
FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY shopping_cart_backend/package*.json ./
RUN npm install

# Copy rest of the backend source code
COPY shopping_cart_backend/ .     
# Expose backend port
EXPOSE 3400

# Start backend
CMD ["npm", "start"]

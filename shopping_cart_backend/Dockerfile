# Use Node.js base image
FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy rest of the backend source code
COPY . .     
# Expose backend port
EXPOSE 3400

# Start backend
CMD ["npm", "start"]

# Build phase
FROM node:18-alpine as build

WORKDIR /app
# Copy prebuilt files
COPY build /app/build

# COPY package*.json ./
# RUN npm install

# COPY . .
# RUN npm install @babel/plugin-transform-private-property-in-object --save-dev
# RUN npm install @rollup/plugin-terser --save-dev
# RUN npx update-browserslist-db@latest
# RUN npm run build

# Serve phase
FROM nginx:stable-alpine

# Remove default nginx static assets
RUN rm -rf /usr/share/nginx/html/*

# Copy build output to nginx
COPY --from=build /app/build /usr/share/nginx/html

# Copy custom nginx config if needed
COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

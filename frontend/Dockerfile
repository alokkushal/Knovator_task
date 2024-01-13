# Stage 1: Build
#FROM node:14-alpine as build
#WORKDIR /app
#COPY . /app
#RUN npm install
#RUN npm run build

# Stage 2: Production
#FROM nginx:alpine
#EXPOSE 80
#CMD ["nginx", "-g", "daemon off;"]
# Stage 1: Build
FROM node:14-alpine as build

WORKDIR /app
COPY . /app

RUN npm install
RUN npm run build

# You can optionally use a smaller base image for the final image
FROM nginx:alpine

# Copy built files from the previous stage
COPY --from=build /app /usr/share/nginx/html

# Expose port 80 for the NGINX server
EXPOSE 80

# Start NGINX
CMD ["nginx", "-g", "daemon off;"]

# Stage 1: Build
FROM node:14-alpine as build
WORKDIR /app
COPY . /app
RUN npm install
RUN npm run build

# Stage 2: Production
FROM node:14-alpine
WORKDIR /app
CMD ["npm", "start"]

# stage 1: Build React App
FROM node:22-alpine AS builder
WORKDIR /app

# copy dependencies in package.json package-lock.json
COPY package.json package-lock.json ./

#clean and fast install using lock file through "npm ci" command
RUN npm ci

# copy the rest of the app
COPY . .

# Build the React app to obtail app or dist folder which contains app.js
RUN npm run build

#Stag 2: serve with Nginx
FROM nginx:alpine

#copy the built static files resulted from the builder stage
COPY --from=builder /app/build /usr/share/nginx/html

# add custom nginx config
COPY default.conf /etc/nginx/conf.d/default.conf

# Expose port 80 for HTTP
EXPOSE 80
# start Nginx in the Foreground not in the background
CMD ["nginx", "-g", "daemon off;"]

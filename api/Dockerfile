FROM node:22-alpine
WORKDIR /app
# Just copy everything including the node_modules created by Jenkins
COPY . .
EXPOSE 5000
CMD ["node", "app.js"]

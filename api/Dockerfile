FROM node:22-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install --only=production   #--only=production to exclude dev dependenc>

COPY . .

EXPOSE 5000

CMD ["node", "app.js"]


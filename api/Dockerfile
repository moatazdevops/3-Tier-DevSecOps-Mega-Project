FROM node:22-alpine
WORKDIR /app
COPY package*.json ./

# Removed the inline comment and switched to the modern flag
RUN npm install --omit=dev --no-audit

COPY . .
EXPOSE 5000
CMD ["node", "app.js"]

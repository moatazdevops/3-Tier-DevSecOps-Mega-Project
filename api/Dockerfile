FROM node:22-alpine
WORKDIR /app

# Copy dependency files
COPY package*.json ./

# Set memory limit to prevent the 'Exit handler' crash
ENV NODE_OPTIONS="--max-old-space-size=512"

# Run install once with all optimizations
RUN npm install --omit=dev --no-audit --prefer-offline && npm cache clean --force

# Copy the rest of the code
COPY . .

EXPOSE 5000
CMD ["node", "app.js"]

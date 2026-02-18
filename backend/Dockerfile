# Backend (Node.js + Express)
FROM node:20-alpine AS base

# Set working directory
WORKDIR /app

# Install dependencies first (better layer caching)
COPY package*.json ./
RUN npm ci --only=production

# Copy the rest of the source code
COPY . .

# Environment
ENV NODE_ENV=production
ENV PORT=8000

# Expose API port
EXPOSE 8000

# Start the server
CMD ["node", "server.js"]

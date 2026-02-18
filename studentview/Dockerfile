# Studentview (Vite React)
FROM node:20-alpine

WORKDIR /app

# Install dependencies first
COPY package*.json ./
RUN npm ci

# Copy source
COPY . .

# Expose Vite dev server port
EXPOSE 5173

# Default dev command (compose will add --host)
CMD ["npm", "run", "dev"]

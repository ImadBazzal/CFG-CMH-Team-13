# Admin (React CRA)
FROM node:20-alpine

WORKDIR /app

# Install dependencies first
COPY package*.json ./
RUN npm ci

# Copy source
COPY . .

# CRA dev server config
ENV HOST=0.0.0.0
ENV PORT=3001
ENV CHOKIDAR_USEPOLLING=true

EXPOSE 3001

CMD ["npm", "start"]

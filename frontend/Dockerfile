# Frontend (React CRA)
FROM node:20-alpine

WORKDIR /app

# Install dependencies first
COPY package*.json ./
RUN npm ci

# Copy source
COPY . .

# CRA dev server config
ENV HOST=0.0.0.0
ENV PORT=3000
ENV CHOKIDAR_USEPOLLING=true

RUN npm run build

EXPOSE 3000

CMD ["npm", "start"]

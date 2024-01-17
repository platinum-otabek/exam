# First Stage - Builder
FROM node:20 AS builder

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

# Second Stage
FROM node:20-alpine

WORKDIR /app

# Copy everything from builder
COPY --from=builder /app .

EXPOSE 3000

CMD ["npm", "start"]

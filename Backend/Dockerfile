# FROM node:20 AS builder
FROM node:20.18.3-alpine3.21 AS builder
WORKDIR /opt/backend
COPY package.json ./
COPY *.js ./
RUN npm install

# ---------- Stage 2: Final ----------
# FROM node:20
FROM node:20.18.3-alpine3.21

# Create user and app dir
RUN apk add --no-cache shadow && \
    groupadd -r expense && \
    useradd -r -g expense expense && \
    mkdir -p /opt/backend && \
    chown -R expense:expense /opt/backend

ENV DB_HOST="mysql"

WORKDIR /opt/backend

# Use non-root user
USER expense

# Copy build artifacts from builder stage
COPY --from=builder /opt/backend /opt/backend

# Start the app
CMD ["node", "index.js"]

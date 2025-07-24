FROM node:20 AS builder

WORKDIR /opt/backend

# Copy dependencies first
COPY package*.json ./

RUN npm install

# Copy source files (make sure index.js exists)
COPY index.js /opt/backend/
COPY . /opt/backend/

# ---------- Stage 2: Final ----------
FROM node:20

# Create user and app dir
RUN groupadd -r expense && \
    useradd -r -g expense expense && \
    mkdir -p /opt/backend && \
    chown -R expense:expense /opt/backend

ENV DB_HOST="mysql"

WORKDIR /opt/backend

# Copy build artifacts from builder stage
COPY --from=builder /opt/backend /opt/backend

# Use non-root user
USER expense

# Start the app
CMD ["node", "index.js"]

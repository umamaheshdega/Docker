from node:20
workdir /opt/backend
copy package.json ./
copy *.js ./
run npm install

from node:20
run groupadd -r expense && \
    useradd -r -g expense expense && \
    mkdir -p /opt/backend && \
    chown -R expense:expense /opt/backend
env  DB_HOST="mysql"
workdir /opt/backend
user expense
# copy --from=builder /opt/backend /opt/backend
cmd ["node", "index.js"]

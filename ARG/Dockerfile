ARG version
from almalinux:${version:-9}
env course=devops \
    trainer=sivakumar \
    duration="120hrs"
ARG username=sivakumar
env username=$username
run echo "Hello User: ${username}, image version: ${version}" > /tmp/devops.txt
cmd ["sleep","100"]
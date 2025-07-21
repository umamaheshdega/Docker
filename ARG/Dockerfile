arg version
from almalinux:${version:-9}
env course = "devops" \
    trainer = "sivakumar"
    duration = "120hrs"
arg username = sivakumar
env username = $username
run echo "hello user:${username},image version:${version}" > /tmp/hello.txt
cmd ["sleep","100"]
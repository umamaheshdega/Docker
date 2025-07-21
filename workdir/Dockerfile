from almalinux:9
run mkdir /tmp/workdir
run useradd mahesh
workdir /tmp/workdir
run pwd
run echo "hello from workdir" > hello.txt
user mahesh
cmd ["sleep","100"]
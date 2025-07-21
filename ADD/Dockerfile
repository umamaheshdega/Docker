from almalinux:9
run dnf -y install nginx 
run dnf clean all 
run rm -rf /usr/share/nginx/html/index.html 
run mkdir -p  /usr/share/nginx/html 
add  sample-1.tar /tmp/
expose 8080
LABEL project="devops" \
      environment="dev" \
      component="frontend" \
      author="umamahesh"

cmd ["nginx", "-g", "daemon off;"]
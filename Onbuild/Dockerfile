from almalinux:9
run dnf install nginx -y 
run rm -rf /usr/share/nginx/html/index.html
onbuild copy index.html /usr/share/nginx/html/index.html
cmd ["nginx", "-g", "daemon off;"]
from almalinux:9
run dnf install nginx -y 
run rm -rf /usr/share/nginx/html/index.html
onbulid copy index.html /usr/share/nginx/html/index.html
CMD ["nginx", "-g", "daemon off;"]
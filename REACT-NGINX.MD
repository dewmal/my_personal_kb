REACT NGINX


server { 
        listen 80; 
        listen [::]:80;

        root  <root-path>;
        index index.html index.htm index.nginx-debian.html;

        server_name anroweb.egreen.io;

        location / {
             root <root-path>;
             try_files $uri $uri/ <root-path>/index.html;
        }
}

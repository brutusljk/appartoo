# appartoo
non
server { 
     listen       80; 
     server_name  localhost;
     location / { 
         root   /usr/share/nginx/html/symfony/web; 
         index  index.html index.htm index.php; 
     }
     location ~ ^(.+\.php)(.*)$ { 
     　　root   /usr/share/nginx/html/symfony/web; 
　　     fastcgi_index index.php;　　
   　　  fastcgi_split_path_info ^(.+\.php)(.*)$; 
     　　fastcgi_param   SCRIPT_FILENAME $document_root$fastcgi_script_name; 
　　     fastcgi_param   PATH_INFO               $fastcgi_path_info; 
   　　  fastcgi_param   PATH_TRANSLATED $document_root$fastcgi_path_info; 
　　     fastcgi_pass 127.0.0.1:9000; 
　　     include fastcgi_params;
    }
}

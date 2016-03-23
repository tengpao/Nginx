#简单php配置
```
sudo /etc/init.d/nginx start || sudo service nginx start
sudo vim /etc/nginx/sites-available/default
location ~ \.php$ {
    root /usr/share/nginx/html;
    fastcgit_split_path_info ^(.+\.php)(/.+)$;
    fastcgi_pass unix:var/run/php5-fpm.sock;
    fastcgi_index index.php;
    fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script-name;
    include fastcgi_params;
}
sudo nginx -t
sudo service nginx reload
```

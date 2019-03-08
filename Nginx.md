# NGINX
```
sudo yum update
sudo yum install epel-release
```
WGet Required Plugin:
```
wget https://payumcinartifact.blob.core.windows.net/artificate/headers-more-nginx-module-0.26.tar.gz
wget https://payumcinartifact.blob.core.windows.net/artificate/nginx_ajp_module-master.tar.gz
wget https://payumcinartifact.blob.core.windows.net/artificate/nginx-1.14.2.tar.gz
```
Configure Nginx:
```
./configure \
--prefix=/etc/nginx \
--sbin-path=/usr/sbin/nginx \
--conf-path=/etc/nginx/nginx.conf \
--error-log-path=/var/log/nginx/error.log \
--http-log-path=/var/log/nginx/access.log \
--pid-path=/var/run/nginx.pid \
--lock-path=/var/run/nginx.lock \ 
--user=nginx \
--group=nginx \
--with-pcre \
--with-http_stub_status_module \
--with-http_ssl_module \
--with-openssl=/tmp/openssl-1.0.2q \
--add-module=/tmp/nginx_ajp_module-master \
--add-module=/tmp/headers-more-nginx-module-0.26

make
make install
```

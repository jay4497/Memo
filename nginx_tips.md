# NGINX TIPS

### 获取 GET 参数

`$arg_username`: 表示获取 GET 参数中 `username` 的值。

### 获取 HEADER 值

`$http_X-API-KEY`: 表示获取 HEADER 中 `X-API-KEY` 的值。

### 替换响应内容

```
# 响应类型
sub_filter_types *;
# 是否只替换第一个匹配的内容，off 则替换所有
sub_filter_once off;
# 替换 username 为 user_name
sub_filter 'username' 'user_name';
```

### 添加响应头

```
# add_header HEADER_NAME value
add_header Access-Control-Allow-Origin 'example.com';
```

### Fastadmin ( ThinkPHP5.0 ) 主要配置备忘

```
server {
	listen 80;
	listen [::]:80;
	
	server_name localhost jay4497.cn;
	root /var/www/;
	index index.php;
	
	location / {
		if (!-e $request_filename) {
			rewrite  ^(.*)$  /index.php?s=/$1  last;
			break;
		}
	}
	
	location ~ \.php(.*)$ {
		# php-fpm 服务端口
		fastcgi_pass 127.0.0.1:9000;
		fastcgi_index  index.php;
        fastcgi_split_path_info  ^((?U).+\.php)(/?.+)$;
        fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name;
        fastcgi_param  PATH_INFO  $fastcgi_path_info;
        fastcgi_param  PATH_TRANSLATED  $document_root$fastcgi_path_info;
        include        fastcgi_params;
	}
}
```

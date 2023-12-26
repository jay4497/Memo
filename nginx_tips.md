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

### 文件流内部转发服务 X-Accel

可用于文件下载、音视频流读取等，方便在用户读取文件时进行鉴权、记录等前置操作。

Nginx 配置：

```
server {
    # other options

    # 访问 /downloads/abc.zip 会指向 /var/files/abc.zip
    location /downloads {
        internal;
        alias /var/files;
    }
}
```

实现下载文件功能的 PHP 示例：

```PHP
// 执行完其他自定义逻辑业务后输出文件流
// 设置 MIME 类型
header("Content-type: application/octet-stream");
// 设置文件名
header('Content-Disposition: attachment; filename="filename.zip"');
// 设置缓存 yes/no
header('X-Accel-Buffering: no');
// 下载速率 bytes
header('X-Accel-Limit-Rate: 50000');
// 文件转发路径
header("X-Accel-Redirect: /downloads/abc.zip");
```

参考：[X-Accel|Nginx](https://www.nginx.com/resources/wiki/start/topics/examples/x-accel/)

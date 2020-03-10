

# 安装
## 安装sphinx
```
pip install sphinx
```



## 安装sphinx-rtd-theme
```
pip install sphinx-rtd-theme
```


## 生成HTML
```
make html
```
HTML 页面保存在 build/html 目录



# 运行
在Nginx配置文件中添加如下配置
```
server {
	listen 8087;
	server_name localhost;
	location / {
		root /Users/zhengchao/code/github/sphinx-demo/build/html/; # 路径
		index index.html index.htm;
	}
	error_page 500 502 503 504 /50x.html;
	location = /50x.tml {
		root html;
	}
}
```
重启Nginx
```
nginx -s reload
```

## 访问地址
http://localhost:8087/





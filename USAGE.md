


1. 启动core server, 控制端口是0.0.0.0:7835
bore server --secret my_secret_string

2. 启动客户端本地服务8080 , /opt/tomcat/bin/start.sh

3. 启动bore client端
bore local 8080 --to 0.0.0.0 --secret my_secret_string

4. 查看tcp连接
控制连接： tcp        0      0 0.0.0.0:7835            0.0.0.0:*               LISTEN      24561/bore
client注册服务的对外开放端口： tcp        0      0 0.0.0.0:34477           0.0.0.0:*               LISTEN      24561/bore

5. curl发请求：
```
root@502f7b062706 ~/g/bore (main)# curl http://0 0.0.0.0:34477/

curl: (7) Failed to connect to 0.0.0.0 port 80 after 0 ms: Connection refused
<head>
	<h1>hello world</h1>
</head>
```


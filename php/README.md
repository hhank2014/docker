#centos 7.2
#centos nginx services

docker build -t 192.168.221.100:5000/centos:nginx .

docker images
REPOSITORY                      TAG                 IMAGE ID            CREATED             SIZE
192.168.221.100:5000/centos     nginx               4f4910e795e7        3 seconds ago       676.6 MB

docker run -d -P --name nginx 192.168.221.100:5000/centos:nginx
91c2065f8a47e17698294d48e45703436a70af5f3e4b084cf9879473415f6756

docker ps -a
CONTAINER ID        IMAGE                               COMMAND                  CREATED             STATUS              PORTS                                                                  NAMES
91c2065f8a47        192.168.221.100:5000/centos:nginx   "/run.sh"                36 seconds ago      Up 35 seconds       0.0.0.0:32811->22/tcp, 0.0.0.0:32810->80/tcp, 0.0.0.0:32809->443/tcp   nginx

curl http://127.0.0.1:32810
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
    body {
        width: 35em;
        margin: 0 auto;
        font-family: Tahoma, Verdana, Arial, sans-serif;
    }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

<p>For online documentation and support please refer to
<a href="http://nginx.org/">nginx.org</a>.<br/>
Commercial support is available at
<a href="http://nginx.com/">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>


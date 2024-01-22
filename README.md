# SSL setup
In the ssl folder under `docker/nginx`, create a self-generated certificate as follows;

```
mkdir ssl
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout ssl/nginx.key -out ssl/nginx.crt
```
This should generate two files, `nginx.crt` and `nginx.key`

# In the project folder run the following;
`docker-compose up -d` This will build the images and run the containers in the background.

The application should be accessible at https://127.0.0.1

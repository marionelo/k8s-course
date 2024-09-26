# Build

Primero se hace el build de la imagen que queremos de la siguiente manera

```sh
docker build -t mariossan/nginx:v1

# hacemos login de hub docker con nuestras credenciales
docker login 

# subimos nuestra imagen 
docker push mariossan/nginx:v1
```

Después es momento de crear al pod

```sh
kubectl create -f nginx.yaml
kubectl logs -f pod/nginx
```

Ahora podemos exponer el pod con un servicio

```sh
kubectl port-forward nginx 9999:80
```
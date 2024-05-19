
# Comandos utilizados:
```
kubectl apply -f namespace.yaml
```
```
kubectl apply -f nginx.yaml -n dllacsa
```

# Respondiendo la pregunta:
Una vez desplegada la aplicación, identificar el servicio, puerto y endpoint donde se
exponen las métricas de Nginx

Endpoint:
http://127.0.0.1:9113/metrics


![Ejemplo de imagen](https://github.com/DLlacsaSpace/compartido/blob/main/blob/main/images/Captura1.png?raw=true)
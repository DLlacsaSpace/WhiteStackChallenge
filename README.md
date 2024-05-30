# Whistack Challenge 2

Diagrama de arquitectura:

![Ejemplo de imagen](https://github.com/DLlacsaSpace/compartido/blob/main/blob/main/images/ws-challenge/diagrama.png?raw=true)

# Iniciar

1.- Para la primer punto de desplegar el nginx y nginx exporter no encontré ninguna dificultad, la URL expuesta con las métricas fue la siguiente:

http://metrics:9113/metrics

```
kubectl apply -f  0-nginx
```

2.- Para el segundo tuve que desplegar prometheus y prometheus-operator para la recoleccion de la métricas.

Primero se crean los CRD
```
kubectl create -f 1-prometheus/prometheus-operator-crd
```
Se despliega prometheus y sus componentes
```
kubectl apply -R -f 1-prometheus/monitoring
```
Para que prometheus pueda reconocer las métricas tuve que crear el serviceMonitor
```
kubectl apply -f   kubectl apply -f 1-prometheus/0-service-monitor.yaml
```
3.- Para el tercer requerimiento se solicita crear un grafana en ambiente local, por lo que desplegue un contenedor grafana con docker compose
```
cd 2-grafana
docker-compose up -d
```
y luego dentro de grafana se configura la fuente de datos con prometheus

4.- No tuve complicaciones en crear los primeros 4 graficos en prometheus, para los 3 ultimos tuve que habilitar cadvisor y kube-state-metrics para cumplir con los requerimientos
Para desplegar los componentes:
```
kubectl apply -f 3-adicionales/
```
Se podrá ubicar el dashboard en formato Json en la carpeta 5-entregables
5.- 


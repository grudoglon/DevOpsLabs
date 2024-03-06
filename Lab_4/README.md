# Лабораторная работа №4

## Цель работы

Сделать мониторинг сервиса с помощью prometheus и grafana

## Ход работы

**Установка Prometheus:**
```
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm install prometheus prometheus-community/prometheus
```
<p align="center">
    <img src="./images/img-1.png">
</p>

**Установка Grafana:**
```
helm repo add grafana https://grafana.github.io/helm-charts
helm install grafana grafana/grafana
```
<p align="center">
    <img src="./images/img-1.png">
</p>



## Вывод


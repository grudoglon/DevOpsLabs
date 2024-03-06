# Лабораторная работа №2

## Цель работы

Поднять кластер Kubernetes локально, в нём развернуть свой сервис.

## Ход работы

Для выполнения работы был использован локальный кластер Minikube, который позволяет поднять локальный кластер Kubernetes. После установки Minikube, был запущен кластер с помощью команды `minikube start`:
<p align="center">
    <img src="./images/img-1.png">
</p>

**Создадим виртуальное хранилище образов для докера на порту 5000:**
```
minikube addons enable registry
docker run --rm -it --network=host alpine ash -c "apk add socat && socat TCP-LISTEN:5000,reuseaddr,fork TCP:$(minikube ip):5000"
```
В качестве разворачиваемого сервиса было создано приложение выводящее в браузере: "Hello Kubernetes". Для этого было создано 3 файла: Dockerfile, app.py и requirements.

Dockerfile
```
```
app.py
```
```
requirements
```
```
**После создания всех необходимых файлов был собран докер-образ:**
<p align="center">
    <img src="./images/img-2.png">
</p>
<p align="center">
    <img src="./images/img-3.png">
</p>

Для того чтобы можно было развернуть созданное приложение с помощью kubernetes необходимо прописать манифесты (Deployment и Service) в формате yalm-файлов.

**deployment.yalm:**
```
```
**service.yalm:**
```
```
Для создания объектов в kubernetes нужно воспользоваться следующими командами:
```
kubectl apply -f deployment.yalm
kubectl apply -f service.yalm
```
Сервис был запущен с помощью команды `minikube service kuber-app`
**Результат:**
<p align="center">
    <img src="./images/img-4.png">
</p>

## Вывод

В результате выполнения лабораторной работы был поднят кластер Kubernetes локально, в нём был развернут свой сервис.

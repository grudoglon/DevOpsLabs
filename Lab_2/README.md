# Лабораторная работа №2

## Цель работы

Поднять кластер Kubernetes локально, в нём развернуть свой сервис.

## Ход работы

Для выполнения работы был использован локальный кластер Minikube, который позволяет поднять локальный кластер Kubernetes. После установки Minikube, был запущен кластер с помощью команды `minikube start`:
<p align="center">
    <img src="./images/img-1.png">
</p>

Создадим виртуальное хранилище образов для докера на порту 5000
```
minikube addons enable registry
docker run --rm -it --network=host alpine ash -c "apk add socat && socat TCP-LISTEN:5000,reuseaddr,fork TCP:$(minikube ip):5000"
```


## Вывод

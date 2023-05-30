Выполнено ДЗ №3

[+] Основное ДЗ
[+] Задание со *
[+] Задание со **
В процессе сделано:

Развернут кластер в kind
Создан frontend ReplicaSet - frontend-replicaset.yaml
Собран и помещен в Docker Hub образ с двумя тегами v0.0.1 и v0.0.2
Создан и запущен манифест paymentservice-replicaset.yaml с тремя репликами, разворачивающими из образа версии v0.0.1.
Переделан kind на Deployment - paymentservice-deployment.yaml
Опробовано создание 2х ReplicaSet
Созданы 2 Deployment paymentservice-deployment-bg.yaml и paymentservice-deployment-reverse.yaml с использованием maxSurge и maxUnavailable.
Создан манифест frontend-replicaset.yaml с настройками Probe
Создан манифест node-exporter-daemonset.yaml
PR checklist:

[+] Выставлен label с темой домашнего задания

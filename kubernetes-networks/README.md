# Выполнено ДЗ № 3

 - [+] Основное ДЗ
 - [+] Задание со * coredns
 - [+] Задание со * dashboard
 - [-] Задание со * canary

## В процессе сделано:
 - Правлена проблема с запуском миникуба с драйвером hyperkit. Не резолпвило с мэйнзоста дня запросы. Поставил и настроил на хосте dnsmasq https://gist.github.com/ogrrd/5831371
 - включил аддон metallb (minikube addons enable metallb)
 - запустил metallb-config.yaml
 - запустил web-pod с проверкой
 - запустил web-deploy с проверкой и стратегией развертки
 - поставил kubespy
 - поправил настройки kube-proxy (kubectl --namespace kube-system delete pod --selector='k8s-app=kube-proxy')
 - очищен ip-tabales, проверил  как kube-proxy добавляет правила
 - поставил в toolbox ipvsadm (dnf install -y ipvsadm && dnf clean all)
 - сделал маршрут через адрес кластера и зашел на http://172.17.255.1
 - прокинулась dns во вне (../coredns/dns.yaml)
 - активировал аддон ingress
 - исправил синтаксис в web-ingress.yaml
 - nginx-lb.yaml добавил адрес
 - настроен доступ из вне по адресу 172.17.255.3 (файлы nginx-lb.yaml, web-svc-headless.yaml, web-ingress.yaml)
 - добавил coredns(доступ из вне dns) и dashboard (https://172.17.255.3/dashboard/#/login)
 - 


## Как проверить работоспособность:
 - kubectl get event --watch 
 - kubespy trace deploy web
 - kubectl --namespace metallb-system get all
 - kubectl get services
 - kubectl --namespace kube-system edit configmap/kube-proxy
 - minikube service --url web-svc-lb
 - kubectl describe ingress/web
 - curl http://172.17.255.1
 - nslookup web.default.cluster.local 172.17.255.2
 - sudo nmap -p53 172.17.255.2 -sU -sT
 - minikube addons enable ingress
 - curl http://172.17.255.3/web/index.html

## PR checklist:
 -  [+] Выставлен label с темой домашнего задания


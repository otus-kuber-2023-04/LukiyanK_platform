# LukiyanK_platform
LukiyanK Platform repository
- Создал контейнер опубликован в публичной репе.
    - docker build -t my-apache2_2 .
    docker tag my-apache2_2:latest luliyan/for_hw_otus:latest
    docker push luliyan/for_hw_otus:latest 
- Написал манифест web-pod.yaml для k8s по запуску контейнера.
- Добыйвил init контейнер.
- После активации маницеста создался рабочий pod&
    - kubectl apply -f web-pod.yaml
- Прокин порты для доступа к сервису в поде.
    - kubectl port-forward pod/web 8000:8000
- Получил манифест для frontend.
    - kubectl run frontend --image avtandilko/hipster-frontend:v0.0.1 --restart=Never --dry-run -o yaml > frontend-pod.yaml
- При попытки запуска в лога явно видно, что ругается на переменные, добавил переменные, скопировав из файла репы.

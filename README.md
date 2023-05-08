# LukiyanK_platform
LukiyanK Platform repository
1. Создал контейнер опубликован в публичной репе.
	docker build -t my-apache2_2 .
	docker tag my-apache2_2:latest luliyan/for_hw_otus:latest
	docker push luliyan/for_hw_otus:latest 
2. Написал манифест web-pod.yaml для k8s по запуску контейнера.
  2.1 Добыйвил init контейнер.
3. После активации маницеста создался рабочий pod&
	kubectl apply -f web-pod.yaml
4. Прокин порты для доступа к сервису в поде.
	kubectl port-forward pod/web 8000:8000
5. Получил манифест для frontend.
	kubectl run frontend --image avtandilko/hipster-frontend:v0.0.1 --restart=Never --dry-run -o yaml > frontend-pod.yaml
6. При попытки запуска в лога явно видно, что ругается на переменные, добавил переменные, скопировав из файла репы.

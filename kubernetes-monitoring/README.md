Собрал обарз nginx
Запилил манифесты для деплоя nginx, ngonx-exporter,prometheus...
Из офф репы установил оператора:
	kubectl apply -f https://raw.githubusercontent.com/prometheus-operator/prometheus-operator/main/example/prometheus-operator-crd/monitoring.coreos.com_servicemonitors.yaml
Задеплоил всё:
kubectl apply -f nginx-deploy.yaml
kubectl apply -f nginx-exporter.yaml
kubectl apply -f prometheus.yaml
kubectl apply -f servicemonitor.yaml

Пробразываю порт для nginx:
kubectl port-forward deployments/nginx 8000:80
Заходим localhost:8000/basic_status
Проверяем работу nginx-exporter и prometheus
kubectl port-forward deployments/nginx-exporter 9113:9113
kubectl port-forward deployments/prometheus-deployment 9090:9090

Добавил lable ДЗ

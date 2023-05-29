Выполнено ДЗ № 5

[+] Основное ДЗ
[+] Задание со *
В процессе сделано:

Добавлены minio-statefulset.yaml и minio-headless-service.yaml
Добавлен secret.yaml, в minio-statefulset.yaml добалено использование секрета.
Как запустить проект:

kubectl apply -f kubernetes-volumes
Как проверить работоспособность:

Выполнить команды:
- kubectl get statefulsets
- kubectl get pods
- kubectl get pvc
- kubectl get pv
- kubectl describe <resource_name>

PR checklist:

[+] Выставлен label с темой домашнего задания

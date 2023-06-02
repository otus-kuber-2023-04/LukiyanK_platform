
## # Выполнено ДЗ № 4

- [+] Task01

    Bob получил роль админа кластера, dave с пустым roleRef: name: "". Всё сделал в одном файл для каждого акта
- [+] Task02

    Раздельно для учеток, ролей. В ClusterRoleBinding прописал отдельно для группы и для учетки.
- [+] Task03

    Создал отдоенные роли для каждой ученик.   

## Выполнение

Task01

```bash
  kubectl create -f kubernetes-security/task01
```
Проверка

```bash
  kubectl get serviceaccount 
  kubectl get RoleBinding
```

Task02

```bash
  kubectl create -f kubernetes-security/task02
```
Проверка

```bash
  kubectl auth can-i list pods --as system:serviceaccount:prometheus:carol -n prometheus
  kubectl auth can-i list pods --as system:serviceaccount:prometheus:carol
```

Task03

```bash
  kubectl create -f kubernetes-security/task03
```

Проверка

```bash
  kubectl auth can-i create deployments --as system:serviceaccount:dev:jane -n dev
  kubectl auth can-i create deployments --as system:serviceaccount:dev:ken -n dev
```
# Links

https://habr.com/ru/companies/southbridge/articles/655409/



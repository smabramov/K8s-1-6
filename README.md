# «Хранение в K8s. Часть 1» - Абрамов Сергей

### Цель задания

В тестовой среде Kubernetes нужно обеспечить обмен файлами между контейнерам пода и доступ к логам ноды.

------

### Чеклист готовности к домашнему заданию

1. Установленное K8s-решение (например, MicroK8S).
2. Установленный локальный kubectl.
3. Редактор YAML-файлов с подключенным GitHub-репозиторием.

------

### Дополнительные материалы для выполнения задания

1. [Инструкция по установке MicroK8S](https://microk8s.io/docs/getting-started).
2. [Описание Volumes](https://kubernetes.io/docs/concepts/storage/volumes/).
3. [Описание Multitool](https://github.com/wbitt/Network-MultiTool).

------

### Задание 1 

**Что нужно сделать**

Создать Deployment приложения, состоящего из двух контейнеров и обменивающихся данными.

1. Создать Deployment приложения, состоящего из контейнеров busybox и multitool.
2. Сделать так, чтобы busybox писал каждые пять секунд в некий файл в общей директории.
3. Обеспечить возможность чтения файла контейнером multitool.
4. Продемонстрировать, что multitool может читать файл, который периодоически обновляется.
5. Предоставить манифесты Deployment в решении, а также скриншоты или вывод команды из п. 4.

------

### Решение
 
Создадим пространство имен для задания:

![k1](https://github.com/smabramov/K8s-1-6/blob/afb1a39186d7ae743297ee468504840735e3010d/png/k1.png)

[deployment.yaml](https://github.com/smabramov/K8s-1-6/blob/afb1a39186d7ae743297ee468504840735e3010d/code/deployment.yaml)

![k2](https://github.com/smabramov/K8s-1-6/blob/afb1a39186d7ae743297ee468504840735e3010d/png/k2.png)

![k3](https://github.com/smabramov/K8s-1-6/blob/afb1a39186d7ae743297ee468504840735e3010d/png/k3.png)

![k4](https://github.com/smabramov/K8s-1-6/blob/afb1a39186d7ae743297ee468504840735e3010d/png/k4.png)

### Задание 2

**Что нужно сделать**

Создать DaemonSet приложения, которое может прочитать логи ноды.

1. Создать DaemonSet приложения, состоящего из multitool.
2. Обеспечить возможность чтения файла `/var/log/syslog` кластера MicroK8S.
3. Продемонстрировать возможность чтения файла изнутри пода.
4. Предоставить манифесты Deployment, а также скриншоты или вывод команды из п. 2.

------

### Решение

[DaemonSet.yaml](https://github.com/smabramov/K8s-1-6/blob/afb1a39186d7ae743297ee468504840735e3010d/code/DaemonSet.yaml)

![k5](https://github.com/smabramov/K8s-1-6/blob/afb1a39186d7ae743297ee468504840735e3010d/png/k5.png)

![k6](https://github.com/smabramov/K8s-1-6/blob/afb1a39186d7ae743297ee468504840735e3010d/png/k6.png)

![k7](https://github.com/smabramov/K8s-1-6/blob/afb1a39186d7ae743297ee468504840735e3010d/png/k7.png)

![k8](https://github.com/smabramov/K8s-1-6/blob/afb1a39186d7ae743297ee468504840735e3010d/png/k8.png)


### Правила приёма работы

1. Домашняя работа оформляется в своём Git-репозитории в файле README.md. Выполненное задание пришлите ссылкой на .md-файл в вашем репозитории.
2. Файл README.md должен содержать скриншоты вывода необходимых команд `kubectl`, а также скриншоты результатов.
3. Репозиторий должен содержать тексты манифестов или ссылки на них в файле README.md.

------

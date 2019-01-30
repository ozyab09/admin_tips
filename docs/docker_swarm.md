Директивы планировщика

- Placement - где разместить задачу
- Deploy Mode - как распределять задачи
- Resources - сколько ресурсов выделить на задачу
- Update-policy - как обновлять задачи
- Restart-policy - что делать, если задача завершилась
- Labels - какую метку присвоить задаче
- Endpoint Mode - как задачам взаимодействовать между собой


#### Placement
```
docker service create \
--name mongo \
--constraint 'node.labels.reliability == high’ \
--constraint 'engine.labels.provider == google’ \
mongo:3.2
```
добавить node label: `docker node update --label-add reliability=high master-1`

#### Deploy Mode

Как распределять задачи (в соответствии с placement) ?

- replicated - запустить определенное число задач (default)
- global - запустить задачу на каждой ноде

```
ui:
  image: ${USER_NAME}/ui:${UI_VERSION}
  deploy:
    mode: replicated
    replicas: 2
    placement:
      constraints:
    - node.role == worker #Не будем размещать на manager
```

```
node-exporter:
  image: prom/node-exporter:v0.15.0
  deploy:
    mode: global
  user: root
  volumes:
    - /proc:/host/proc:ro
```

#### Overlay network

- Overlay network – позволяет объединить в одну сеть контейнеры нескольких докер хостов
- Работает поверх vxlan
- Нужно хранить состояние распределенной сети

#### IP Virtual Server (IPVS)

Реализация балансировщика нагрузки в ядре Linux
- Включен по-умолчанию (Round Robin LB)
- Сервису назначается 1 VIP (Виртуальный IP-адрес)
- Клиенты не знают, сколько за этим адресом участников

* DNS Round Robin

Включается отдельно. DNS возвращает адреса всех участников

```
post:
  image: ${USER_NAME}/post:${POST_VERSION}
  deploy:
    endpoint_mode: dnsrr
    replicas: 3
```

* VIP:
```
post:
  image: ${USER_NAME}/post:${POST_VERSION}
  deploy:
    endpoint_mode: vip
    replicas: 3
```


#### Update Service

Обновить конфигурацию сервиса:
- docker stack deploy -c docker-compose.yml …
- docker service update …

#### Rolling Update

как обновлять задачи ?

```
ui:
  image: ${USER_NAME}/ui:${UI_VERSION}
  deploy:
    update_config:
	  parallelism: 2
delay: 5s
failure_action: rollback
monitor: 5s
max_failure_ratio: 2
order: start-first
```







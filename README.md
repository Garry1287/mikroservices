
На docker-host машине выполните команду:
`sudo ln -s /var/run/docker/netns /var/run/netns`
Теперь вы можете просматривать существующие в данный
момент net-namespaces с помощью команды:
`sudo ip netns`
Задание:
Повторите запуски контейнеров с использованием драйверов
none и host и посмотрите, как меняется список namespace-ов.
Примечание: ip netns exec <namespace> <command> - позволит выполнять
команды в выбранном namespace



```
f50d48555857 (id: 3)
8d1ad2c2f0a7 (id: 2)
6054a5d7f9f2 (id: 1)
4e7023b595da (id: 0)
default
```

Была ошибка
`ERROR: SSL error: HTTPSConnectionPool(host='34.76.154.80', port=2376): Max retries exceeded with url: /v1.30/info (Caused by SSLError(SSLError(1, u'[SSL: TLSV1_ALERT_PROTOCOL_VERSION] tlsv1 alert protocol version (_ssl.c:727)'),))`

Помогло
`export COMPOSE_TLS_VERSION=TLSv1_2`
`docker-compose -f ./docker-compose.yml up`

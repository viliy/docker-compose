# RabbitMQ 集群 (3.7.14-management)

## 安装

* git clone https://github.com/viliy/docker-compose.git 
* cd docker-compose/RabbitMQ
* docker-compose up -d

## 加入集群

```shell

// 节点1
docker exec rabbitmq_follwer-1_1 bash -c \
"rabbitmqctl stop_app && \
rabbitmqctl reset && \
rabbitmqctl join_cluster rabbitmq1@leader  && \
rabbitmqctl start_app"

// 节点2
docker exec rabbitmq_follwer-2_1 bash -c \
"rabbitmqctl stop_app && \
rabbitmqctl reset && \
rabbitmqctl join_cluster rabbitmq1@leader  && \
rabbitmqctl start_app"

```

## 查看web

> http://127.0.0.1:15672/#/

> 账号密码： guest guest

## 删除

```shell

# docker-compose stop
# docker-compose rm

```
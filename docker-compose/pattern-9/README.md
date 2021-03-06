### This repository contains API Manager 2.0.0 distributed deployment with Docker compose

![alt tag](https://github.com/wso2/docker-apim/blob/master/docker-compose/patterns/design/am-2.0-pattern-9.png)

#### How to run

 ```docker login dockerhub.private.wso2.com ```

 ```docker-compose up -d```

This will deploy the following,

* Mysql server (container) with apimdb, userdb, regdb
* APIM Store, Publisher, Gateway Manager, Gateway Worker, Keymanager, Traffic Manager distributed Containers
* APIM Analytics Container
* Nginx Load Balancer container and points the APIM components through the load balancer.


#### How to test

Add the following entries to the /etc/hosts
```
127.0.0.1 mgt.gateway.apim.wso2.com publisher.apim.wso2.com store.apim.wso2.com keymanager-tm-gw.apim.wso2.com analytics.apim.wso2.com
```
If you are using docker machine, please use the docker machine IP instead of the local machine IP.

#### How to access the environment

Publisher

```
https://publisher.apim.wso2.com/publisher
```

Store

```
https://store.apim.wso2.com/store
```

Gateway Manager

```
https://mgt.gateway.apim.wso2.com/carbon
```

Gateway Worker

```
https://keymanager-tm-gw.apim.wso2.com:8243
http://keymanager-tm-gw.apim.wso2.com:8280
```

Key Manager/ Traffic Manager

```
https://keymanager-tm-gw.apim.wso2.com/carbon
```

AM Analytics

```
https://analytics.apim.wso2.com:9444/carbon
```
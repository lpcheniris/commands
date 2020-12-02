## 进入docker容器的mongo 命令行
``docker exec -it ``
``timermanager-mongo bash``

## container 的一系列常用操作
``docker container ls  ``

``docker container stop ``

``docker container rm container_id ``

## 创建一个mongo 数据库

``docker run -d --network time-manager --name "time-manager-mongodb" -p 127.0.0.1:27017:27017 --rm mongo``

##  进入mongo
``docker exec -it time-manager-mongod bash ``

## delete images 
## grep 搜索指定的字符

docker rmi $(docker images | awk '$1 == "<none>" && $2 == "<none>" {print $3}')

docker images | grep -E "(hyperledger)" | awk '{print $3}' |  xargs -I {} docker rmi --force {}

## 查看镜像的详细信息
docker inspect 4954eae8ebbb
#docker镜像、容器、仓库

镜像是一个只可读最底层的一层，表示这是一个什么作用，可以理解为C++的类定义

容器：镜像的可读可惜运行太，可以理解为C++的实体

仓库：包含多个镜像的仓库



教程：

https://juejin.im/post/5cacbfd7e51d456e8833390c





![docker镜像_容器命令图](D:\Users\you\Desktop\tmp\docker镜像_容器命令图.jpg)





## docker镜像命令

查看镜像：docker images

查看具体信息docker inspect $CONTAINER_ID



创建镜像

三种方式：

已有镜像容器创建：docker commit [OPTIOINS] $CONTAINER [REPOSITORY[:TAG]]，-a 作者信息 -m 提交信息 -p 提交时暂停容器

基于本地目标导入：从一个操作系统导入一个镜像：cat ubuntu-18.tar.gz | docker import - ubuntu:18

基于dockerfile创建：



删除镜像：docker rm $IMAGE_NAME/$IMAGE_ID

存出镜像：docker save -o xxx.tar ubuntu:18.04

载入镜像：docker load --input ubunutu_18.04.tar

上传镜像：docker push NAME[:TAG]



#docker容器命令

查看容器：docker ps -a

创建容器：docker create [OPTION] IMAGE_NAME:TAG

启动容器：docker run -it ubuntu /bin/bash

启动已停止容器：docker ps -a后查看容器的ID，然后docker start $container_id

停止容器：docker ps -a后查看容器的ID，然后docker stop $container_id

进入容器：docker attach $container_id 或者docker exec -it $container_id /bin/bash

导出容器：docker export $container_id > xxx.tar

导入容器：docker import  xxx.tar > $container_name/ubuntu:$TAG

删除容器：





#仓库

##拉取镜像：

默认的docker官方镜像：docker pull NAME[:TAG]

别的比如腾讯云阿里云拉取镜像：docker pull url:port/NAME



##查找镜像

docker search TERM

参数：

--automated=false， 显示自动创建镜像

--no-trunc=false，输出信息不截断显示

-s， 仅显示星级以上镜像








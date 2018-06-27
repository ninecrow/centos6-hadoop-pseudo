ninecrow/centos-hadoop-pseudo</br>

单镜像参考 http://hadoop.apache.org/docs/r3.1.0/hadoop-project-dist/hadoop-common/SingleCluster.html#YARN_on_Single_Node</br>
按照Pseudo-Distributed Operation配置

Linux: Centos7</br>
安装版本: Apache Hadoop 3.1.0</br>
JDK版本: Oracle JDK 1.8.0_161</br>


【Docker启动参数】</br>
* 解决ssh启动</br>
添加--privilege参数</br>
entrypoint 设置为/usr/sbin/init </br>

* 启动方法 </br>
docker run -itd --privileged \</br>
-p 50010:50010 -p 50020:50020 -p 50070:50070 -p 50075:50075 -p 50090:50090 \</br>
-p 19888:19888 \</br>
-p 8030:8030 -p 8031:8031 -p 8032:8032 -p 8033:8033 -p 8040:8040 -p 8042:8042 -p 8088:8088 \</br>
-p 49707:49707 -p 2122:22 \</br>
ninecrow/hadoop-pseudo:v1 /usr/sbin/init</br>

【Docker登陆】</br>
* docker exec -it [container-id] bash </br>

* 启动yarn
$/opt/hadoop/sbin/start-yarn.sh</br> 

*查看yarn web
http://10.0.153.129:8088/


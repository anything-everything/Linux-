## 1、hadoop完全分布式安装

### 1、jdk环境安装

### 2、hadoop环境安装

#### 1、hadoop安装

#### 2、hadoop修改配置文件

​	需要修改的配置文件如下，下面将分别对每个文件进行说明`core-site.xml	hadoop-env.sh	yarn-env.sh	mapred-env.sh	yarn-site.xml	slaves	hdfs-site.xml`



​	`core-site.xml`文件内容

```
<configuration>
<property>
   <name>fs.defaultFS</name>
   <value>hdfs://master:9000</value>
</property>
<property>
   <name>hadoop.tmp.dir</name>
   <value>/usr/local/hadoop/tmp</value>
</property>
</configuration>
```



​	`hadoop-env.sh`文件内容

```
export JAVA_HOME=/usr/java/jdk1.7.0_80
```



​	`yarn-env.sh`文件内容

```
export HADOOP_YARN_USER=${HADOOP_YARN_USER:-yarn}

# resolve links - $0 may be a softlink
export YARN_CONF_DIR="${YARN_CONF_DIR:-$HADOOP_YARN_HOME/conf}"

# some Java parameters
# export JAVA_HOME=/home/y/libexec/jdk1.6.0/
if [ "$JAVA_HOME" != "" ]; then
  #echo "run java in $JAVA_HOME"
  JAVA_HOME=/usr/java/jdk1.7.0_80
fi
  
if [ "$JAVA_HOME" = "" ]; then
  echo "Error: JAVA_HOME is not set."
  exit 1
```



​	`mapred-site.xml`文件是从`mapred-site.xml.template`中复制出来的

```
cp mapred-site.xml.template mapred-site.xml


<configuration>
<property>                <name>mapreduce.framework.name</name>
<value>yarn</value>
</property>
</configuration>
```



​	`yarn-site.xml`文件

```
<configuration>
<!-- Site specific YARN configuration properties -->
<property>
                <name>yarn.resourcemanager.hostname</name>
                <value>master</value>
        </property>
        <property>
                <name>yarn.nodemanager.aux-services</name>
                <value>mapreduce_shuffle</value>
        </property>
</configuration>

```





​	`slaves`文件

```
slave1
slave2
slave3
```



​	`hdfs-site.xml`文件

```
<configuration>
       <property>
                <name>dfs.namenode.secondary.http-address</name>
               <value>master:9001</value>
       </property>
     <property>
             <name>dfs.namenode.name.dir</name>
             <value>file:/usr/hadoop/dfs/name</value>
       </property>
      <property>
              <name>dfs.datanode.data.dir</name>
              <value>file:/usr/hadoop/dfs/data</value>
       </property>
       <property>
               <name>dfs.replication</name>
               <value>3</value>
        </property>
        <property>
                 <name>dfs.webhdfs.enabled</name>
                  <value>true</value>
         </property>
</configuration>
```



### 3、集群克隆


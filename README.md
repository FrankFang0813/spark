# spark

*下載SPARK
```js
若下載的是hadoop3.x以上,要下載支援的版本
網址https://archive.apache.org/dist/spark/
```

*解壓縮
```js
tar zxvf xxxxxxxxx
```

*設置SPARK_HOME和PATH

```js
vim ~/.bashrc 

貼上 例如:
export SPARK_HOME=/home/spark/spark-2.4.5-bin-hadoop2.7
export PATH=$SPARK_HOME/bin:$PATH
export PYSPARK_PYTHON=python

# use ipython as the interactive shell
export PYSPARK_DRIVER_PYTHON=ipython

# use jupyter as the interactive shell
#export PYSPARK_DRIVER_PYTHON=jupyter 
#export PYSPARK_DRIVER_PYTHON_OPTS=notebook

source ~/.bashrc
```

*設置spark-env.sh和slaves

```js
vim spark-env.sh

貼上 例如:
export SPARK_DIST_CLASSPATH=$(/usr/local/hadoop/bin/hadoop classpath)

export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export PATH=$JAVA_HOME/bin:$PATH

export SPARK_MASTER_IP=192.168.1.175
export SPARK_MASTER_PORT=7077
export SPARK_MASTER_HOST=192.168.1.175
export SPARK_LOCAL_IP=192.168.1.175
export SPARK_EXECUTOR_MEMORY=1024m
export SPARK_MASTER_WEBUI_PORT=8080

export HADOOP_HOME=/usr/local/hadoop
export PATH=$HADOOP_HOME/bin:$PATH

export HADOOP_CONF_DIR=$HADOOP_HOME/etc/hadoop

export SCALA_HOME=/usr/local/scala-2.12.11
export PATH=$SCALA_HOME/bin:$PATH

export ANACONDA_HOME=/home/test/anaconda3
export PATH=$ANACONDA_HOME/bin:$PATH

export SPARK_HOME=/home/test/spark
export PATH=$SPARK_HOME/bin:$PATH


vim slaves
刪除localhost
加上主機名及其他slave
```

*開啟spark
```js
spark/sbin 裡面 執行start-all.sh
然後pyspark --master spark://主機名:7077進入spark
查看是否開啟http:主機名:8080
```




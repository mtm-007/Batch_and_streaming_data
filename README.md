## Spark Installation on a linux 

#### Installing Java
Download OpenJDK 11 or Oracle JDK 11 (It's important that the version is 11 - spark requires 8 or 11)

for linux use OpenJDK

Download it (e.g. to ~/spark):

wget https://download.java.net/java/GA/jdk11/9/GPL/openjdk-11.0.2_linux-x64_bin.tar.gz

Unpack it:
tar xzfv openjdk-11.0.2_linux-x64_bin.tar.gz

define JAVA_HOME and add it to PATH:

export JAVA_HOME="${HOME}/spark/jdk-11.0.2" 
export PATH="${JAVA_HOME}/bin:${PATH}" 


##### Installing Spark
Download Spark. Use 3.3.2 version:

wget https://archive.apache.org/dist/spark/spark-3.3.2/spark-3.3.2-bin-hadoop3.tgz

Unpack:
tar xzfv spark-3.3.2-bin-hadoop3.tgz

Add it to PATH:

export SPARK_HOME="${HOME}/spark/spark-3.3.2-bin-hadoop3" 
export PATH="${SPARK_HOME}/bin:${PATH}" 

## ADD those to .bashrc 
```
export JAVA_HOME="${HOME}/spark/jdk-11.0.2"
export PATH="${JAVA_HOME}/bin:${PATH}"

export SPARK_HOME="${HOME}/spark/spark-3.3.2-bin-hadoop3"
export PATH="${SPARK_HOME}/bin:${PATH}"

export PYTHONPATH="${SPARK_HOME}/python/:$PYTHONPATH"
export PYTHONPATH="${SPARK_HOME}/python/lib/py4j-0.10.9.5-src.zip:$PYTHONPATH"
```

#### TO RUN SPARK CLUSTER 
```
- insructions can be followed from this docs [https://spark.apache.org/docs/3.5.3/spark-standalone.html]
- got the the directory where spark is installed, where the (echo $SPARK_HOME) is located, then run this bash script: ./sbin/start-master.sh
- it will be on port:8080 not port:4040
- get the URL, replace the (local[*])
- TO ADD EXCUTORS run: ./sbin/start-worker.sh <master-spark-URL>  # change worker to slave in some versions
- to the stop the spark cluster
    run:./sbin/stop-master.sh ...to stop the master node
    run:./sbin/stop-worker.sh ...to stop the excutor or slave
```
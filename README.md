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
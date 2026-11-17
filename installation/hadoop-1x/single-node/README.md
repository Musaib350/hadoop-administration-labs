
# Hadoop 1.2.1 – Single Node Installation

## 1. Overview
Installation of Apache Hadoop 1.2.1 in pseudo-distributed mode on a single Linux node.

## 2. Environment
- Hadoop: 1.2.1
- Java: OpenJDK 8
- Operating System: Ubuntu
- Deployment: Single Node

## 3. Prerequisites
- Java installed
- SSH installed and configured
- Linux user with sudo privileges

## 4. SSH Configuration

Commands executed:

```bash
ssh-keygen
cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
ssh localhost
```

## 5. Java Installation

```bash
sudo apt update
sudo apt-get install openjdk-8-jdk -y
```

## 6. Hadoop Download and Installation

```bash
cd ~
wget https://archive.apache.org/dist/hadoop/common/hadoop-1.2.1/hadoop-1.2.1.tar.gz

tar -xzvf hadoop-1.2.1.tar.gz

sudo mv hadoop-1.2.1 /usr/local/hadoop
```

## 7. Environment Variables

Edit:

```bash
vi ~/.bashrc
```

Add:

```bash
export HADOOP_PREFIX=/usr/local/hadoop
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export PATH=$PATH:$HADOOP_PREFIX/bin:$JAVA_HOME/bin
```

Apply:

```bash
source ~/.bashrc
```

## 8. Hadoop Environment Configuration

Edit:

```bash
vi /usr/local/hadoop/conf/hadoop-env.sh
```

Configure:

```bash
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export HADOOP_OPTS="-Djava.net.preferIPv4Stack=true"
```

## 9. Hadoop XML Configuration

### core-site.xml

```bash
vi /usr/local/hadoop/conf/core-site.xml
```

```xml
<configuration>
    <property>
        <name>fs.default.name</name>
        <value>hdfs://localhost:9000</value>
    </property>

    <property>
        <name>hadoop.tmp.dir</name>
        <value>/usr/local/hadoop/tmp</value>
    </property>
</configuration>
```

### hdfs-site.xml

```xml
<configuration>
    <property>
        <name>dfs.replication</name>
        <value>1</value>
    </property>
</configuration>
```

### mapred-site.xml

```xml
<configuration>
    <property>
        <name>mapred.job.tracker</name>
        <value>localhost:9001</value>
    </property>
</configuration>
```

## 10. Temporary Directory

```bash
mkdir -p /usr/local/hadoop/tmp
```

Ensure the Hadoop installation directory is writable by the user running Hadoop.

## 11. Format NameNode

```bash
hadoop namenode -format
```

**Important:** Run this only during initial cluster setup on a fresh NameNode storage directory.

## 12. Start Hadoop Services

```bash
start-all.sh
```

## 13. Cluster Verification

```bash
jps
hadoop dfsadmin -report
hadoop dfsadmin -safemode get
hadoop fsck /
hadoop fs -ls /
```

### Expected Daemons

- NameNode
- DataNode
- SecondaryNameNode
- JobTracker
- TaskTracker


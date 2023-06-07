# Download Hadoop
download
[hadoop](https://hadoop.apache.org/)
```
wget https://dlcdn.apache.org/hadoop/common/hadoop-3.3.5/hadoop-3.3.5.tar.gz
```
Run the following command
```
brew install wget
```
After the installation is complete, you should be able to use the wget command without any issues. Test it by running:
```
wget --version
```
untar hadoop 3
```
tar -zxvf hadoop-3.3.5.tar.gz
```
```nano ~/.bash_profile```
```
export JAVA_HOME="/Library/Java/JavaVirtualMachines/jdk-20.jdk/Contents/Home"
export PATH=$PATH:$JAVA_HOME/bin

export HADOOP_HOME=/Users/imranchaush/hadoop-3.3.5
export PATH=$PATH:$HADOOP_HOME/bin:$HADOOP_HOME/sbin
```

configet .zprofile
```
nano ~/.zprofile
```
copy pest content in .zprofile ``` ALSO CHECK YOUR HOME AND REPLACE THAT ONE WITH YOUR PATH```
```
export HADOOP_HOME=/Users/imranchaush/hadoop-3.3.5/ 
export HADOOP_INSTALL=$HADOOP_HOME 
export HADOOP_MAPRED_HOME=$HADOOP_HOME 
export HADOOP_COMMON_HOME=$HADOOP_HOME 
export HADOOP_HDFS_HOME=$HADOOP_HOME export YARN_HOME=$HADOOP_HOME 
export HADOOP_COMMON_LIB_NATIVE_DIR=$HADOOP_HOME/lib/native 
export PATH=$PATH:$HADOOP_HOME/sbin:$HADOOP_HOME/bin 
export HADOOP_OPTS="-Djava.library.path=$HADOOP_HOME/lib/nativ"
```
update .zprofile content
```
source ~/.zprofile
```
### 5 File need to configer
hadoop-env.sh
```uncoment an pest this line```
```
export JAVA_HOME="/Library/Java/JavaVirtualMachines/jdk-20.jdk/Contents/Home"
```
yarn-site.xml
```
  <property>
    <name>yarn.nodemanager.aux-services</name>
    <value>mapreduce_shuffle</value>
  </property>
  <property>
    <name>yarn.nodemanager.aux-services.mapreduce.shuffle.class</name>
    <value>org.apache.hadoop.mapred.ShuffleHandler</value>
  </property>
  <property>
    <name>yarn.resourcemanager.hostname</name>
    <value>127.0.0.1</value>
  </property>
  <property>
    <name>yarn.acl.enable</name>
    <value>0</value>
  </property>
  <property>
    <name>yarn.nodemanager.env-whitelist</name>   
    <value>JAVA_HOME,HADOOP_COMMON_HOME,HADOOP_HDFS_HOME,HADOOP_CONF_DIR,CLASSPATH_PERPEND_DISTCACHE,HADOOP_YARN_HOME,HADOOP_MAPRED_HOME</value>
  </property>
```

mapred-site.xml
```
  <property> 
    <name>mapreduce.framework.name</name> 
    <value>yarn</value> 
  </property> 
```

hdfs-site.xml
```
<property>
      <name>dfs.data.dir</name>
      <value>/Users/imranchaush/hdfs/namenode</value>
  </property>
  <property>
      <name>dfs.data.dir</name>
      <value>/Users/imranchaush/hdfs/datanode</value>
  </property>
  <property>
      <name>dfs.replication</name>
      <value>1</value>
  </property>
```

core-site.xml
```
<property>
        <name>hadoop.tmp.dir</name>
        <value>/Users/imranchaush/hdfs/tmp/</value>
    </property>
    <property>
        <name>fs.default.name</name>
        <value>hdfs://127.0.0.1:9000</value>
    </property>
```
hdfs namenode -format

```
hdfs namenode -format
```

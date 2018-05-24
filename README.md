# bigdata
the hadoop, spark conf


run on yarn with jdbc support

spark-submit \
 --master yarn \
 --deploy-mode client \
 --conf spark.sql.hive.thriftServer.singleSession=true \
 --class org.apache.carbondata.spark.thriftserver.CarbonThriftServer \
 ./jars/apache-carbondata-1.3.1-bin-spark2.2.1-hadoop2.7.2.jar \
 hdfs://master:9000/data/carbondata

for config
`
 ./hdp-configuration-utils.py -c 8 -m 32 -d 4 -k False
 
 Using cores=8 memory=32GB disks=4 hbase=False
 
 Profile: cores=8 memory=31744MB reserved=1GB usableMem=31GB disks=4
 
 Num Container=8
 
 Container Ram=3584MB
 
 Used Ram=28GB
 
 Unused Ram=1GB
 
 ***** mapred-site.xml *****
 
 mapreduce.map.memory.mb=3584
 
 mapreduce.map.java.opts=-Xmx2560m
 
 mapreduce.reduce.memory.mb=3584
 
 mapreduce.reduce.java.opts=-Xmx2560m
 
 mapreduce.task.io.sort.mb=1280
 
 ***** yarn-site.xml *****
 
 
 yarn.scheduler.minimum-allocation-mb=3584
 
 yarn.scheduler.maximum-allocation-mb=28672
 
 yarn.nodemanager.resource.memory-mb=28672
 
 yarn.app.mapreduce.am.resource.mb=3584
 
 yarn.app.mapreduce.am.command-opts=-Xmx2560m
 
 ***** tez-site.xml *****
 
 tez.am.resource.memory.mb=3584
 
 tez.am.java.opts=-Xmx2560m
 
 ***** hive-site.xml *****
 hive.tez.container.size=3584
 
 hive.tez.java.opts=-Xmx2560m
 
 hive.auto.convert.join.noconditionaltask.size=805306000
`

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


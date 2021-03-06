g++ -std=c++11 -o rocksdbtest.cpp rocksdbtest -lpthread -lrocksdb

```
  - Linux/MacOS
  cd ..
      cd kafka/bin/
  1, open zookeeper:
   ./zookeeper-server-start.sh ../config/zookeeper.properties
  2, open kafka
    ./kafka-server-start.sh ../config/server.properties 
  3 Create topic 
   ./kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
   ./kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test123
   ./kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test456
  4, check topics
   ./kafka-topics.sh --list --zookeeper localhost:2181 
  5, create logs
    ./kafka-console-producer.sh  --broker-list localhost:9092 --topic test
  6, consumer logs
    ./kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning

```

```
  - Windows---
  cd D:\kafka-l\kafka_2.12-2.4.0\bin\windows
      cd kafka/bin/
  1, open zookeeper:
   ./zookeeper-server-start.bat ../../config/zookeeper.properties
  2, open kafka
    ./kafka-server-start.bat ../../config/server.properties 
  3 Create topic 
   ./kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test

  4, check topics
   ./kafka-topics.sh --list --zookeeper localhost:2181 
  5, create logs
    ./kafka-console-producer.bat  --broker-list localhost:9092 --topic test
  6, consumer logs
    ./kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic test --from-beginning

```


```
  cd ..
      cd kafka/bin/windows
  1, open zookeeper:
   ./zookeeper-server-start.bat ../../config/zookeeper.properties
  2, open kafka
    ./kafka-server-start.bat ../../config/server.properties 
  3 Create topic 
   ./kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
   ./kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test123
   ./kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test456
  4, check topics
   ./kafka-topics.bat --list --zookeeper localhost:2181 
  5, create logs
    ./kafka-console-producer.bat  --broker-list localhost:9092 --topic test
  6, consumer logs
    ./kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic test --from-beginning

  7, kafka-console-consumer --bootstrap-server localhost:9092 --topic some-topic --formatter kafka.tools.DefaultMessageFormatter --property print.timestamp=true --property print.key=true --property print.value=true
  8, ./kafka-console-producer.bat  --broker-list localhost:9092 --topic test  --property parse.key=true --property key.separator=*
```
build 
cl kafka-cosume.cpp D:\3rdLib\libs\rdkafka++.lib
cl kafka-consumer_sqlite.cpp  D:\3rdLib\libs\rdkafka++.lib  D:\3rdLib\libs\sqlite3.lib
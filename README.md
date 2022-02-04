## Start Zookeeper  
```sh
#Start the ZooKeeper service
# Note: Soon, ZooKeeper will no longer be required by Apache Kafka.
$ bin/zookeeper-server-start.sh config/zookeeper.properties
```


## Start Broker 
```sh
# Start the Kafka broker service
$ bin/kafka-server-start.sh config/server.properties  
```


## Create/Describe Topic 
```sh
# Create Topic
$ bin/kafka-topics.sh --create --topic demo-kafka --bootstrap-server localhost:9092 --replication-factor 1 --partitions 3 
# Describe Topic
$ bin/kafka-topics.sh --describe --topic demo-kafka --bootstrap-server localhost:9092
```


## Start Console Producer 
```sh
# Start the Kafka broker service
$ bin/kafka-console-producer.sh --topic demo-kafka --bootstrap-server localhost:9092
```


## Start Console Consumer 
```sh
# Start the Simple Consumer
$ bin/kafka-console-consumer.sh --topic demo-kafka --from-beginning --bootstrap-server localhost:9092 --property print.timestamp=true --property print.key=true --property print.partition=true --property print.offset=true
```


## Start Console Consumer with Consumer Group
```sh 
# Start the Consumer Group
$ bin/kafka-console-consumer.sh --bootstrap-server localhost:9092  --topic demo-kafka  --consumer-property group.id=demo-group --from-beginning --property print.timestamp=true --property print.key=true --property print.partition=true --property print.offset=true
```

## List Consumer Group
```sh 
# List Consumer Group
$ bin/kafka-consumer-groups.sh  --list --bootstrap-server localhost:9092
```

## Describe Consumer Group
```sh 
# Describe Consumer Group
$ bin/kafka-consumer-groups.sh  --bootstrap-server localhost:9092  --describe  --group demo-kafka --timeout 50000
```

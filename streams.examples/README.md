# Kafka hello world

## Run Kafka
- get Kafka: https://kafka.apache.org/quickstart
- start Kafka
    - bin/zookeeper-server-start.sh config/zookeeper.properties
    - bin/kafka-server-start.sh config/server.properties
- create topics to store events
    - bin/kafka-topics.sh --create --topic streams-plaintext-input --bootstrap-server localhost:9092
    - bin/kafka-topics.sh --create --topic streams-pipe-output --bootstrap-server localhost:9092

## Run Java program (Pipe)
- mvn clean package
- mvn exec:java -Dexec.mainClass=myapps.Pipe

## Producer
- Takes words and puts them into input stream
-  bin/kafka-console-producer.sh --topic streams-plaintext-input --bootstrap-server localhost:9092

## Consumer
- Receives input from Pipe
- bin/kafka-console-consumer.sh --topic streams-pipe-output --from-beginning --bootstrap-server localhost:9092

Kafka-kstream-test
==================


### Issue
    code works with `org.springframework.cloud:spring-cloud-stream-binder-kstream` and Kafka 0.10.1.1
    but not with `org.springframework.cloud:spring-cloud-stream-binder-kstream11:1.3.0.RELEASE` and Kafka 0.11.0.1

### How to reproduce
```bash
# start kafka 0.11.0.1
docker-compose up
# or start kafka 0.11.0.1
docker-compose -f docker-compose-11.yml up
```

```bash
gradle bootRun
```

```bash
docker-compose exec kafka bash
kafka-topics.sh --list --zookeeper zookeeper:2181
kafka-console-producer.sh --broker-list kafka:9092 --topic words
```

```bash
docker-compose exec kafka bash
kafka-console-consumer.sh --bootstrap-server kafka:9092 --topic counts --from-beginning --property print.key=true
```




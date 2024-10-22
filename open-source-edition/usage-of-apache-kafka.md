# Usage of Apache Kafka

Ylem uses Apache Kafka to exchange messages for processing pipelines and tasks. By default Ylem already comes with the pre-configured **Apache Kafka** container, however, you might already have an Apache Kafka cluster in your infrastructure and might want to reuse it.

In this case, you need to take the following steps:

### 1. Create Apache Kafka topics

To be able to work correctly, Ylem requires the following Apache Kafka topics to be created:

* task\_runs
* task\_runs\_load\_balanced
* task\_run\_results
* query\_task\_run\_results
* notification\_task\_run\_results

### 2. Remove the Apache Kafka container from docker-compose.yml

Open `docker-compose.yml` in the root folder, and remove or comment out the [following lines](https://github.com/ylem-co/ylem-installer/blob/main/docker-compose.yml#L156-L187) to exclude it from the network.

Also don't forget to remove [these](https://github.com/ylem-co/ylem-installer/blob/main/docker-compose.yml#L57-L59) and [these](https://github.com/ylem-co/ylem-installer/blob/main/docker-compose.yml#L28-L30) dependency checks.

### 3. Add your Apache Kafka host to the .env parameters

Open `.env` and replace the following value with your Kafka host:

```bash
YLEM_KAFKA_BOOTSTRAP_SERVERS=ylem_kafka_broker:39092
```

Now if you run `docker compose up` and everything is set up correctly Ylem should be able to work with your own Kafka cluster.



```
ksql-datagen schema=./01_location_event.avro format=AVRO key=who maxInterval=5000 iterations=10000 topic=LOCATION_EVENT > /dev/null &
```

```
curl -X PUT \
  /api/kafka-connect-1/connectors/06_sink_jdbc/config \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -d '{
  "connector.class": "io.confluent.connect.jdbc.JdbcSinkConnector",
  "connection.password": "password",
  "auto.evolve": "true",
  "connection.user": "postgres",
  "tasks.max": "1",
  "topics": "LOCATION_EVENT",
  "auto.create": "true",
  "connection.url": "jdbc:postgresql://postgres:5432/postgres",
  "insert.mode": "insert"
}'
```


SET 'auto.offset.reset'='earliest';

ksql-datagen schema=./datagen/01_location_event.avro format=AVRO key=who maxInterval=5000 iterations=10000 topic=LOCATION_EVENT

-33.766852,151.167412
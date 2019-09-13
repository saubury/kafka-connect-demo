


```
export KAFKA_CONNECT=localhost:8083
curl ${KAFKA_CONNECT}/connector-plugins | jq '.[].class'
```

# Setup Database
```
cat scripts/go-demo.sql | docker-compose exec -T sqlserver bash -c '/opt/mssql-tools/bin/sqlcmd -U sa -P Password!'
```

# Simple JDBC SOurce
```
curl -k -s -S -X PUT -H "Accept: application/json" -H "Content-Type: application/json" --data @./source_jdbc.json http://localhost:8083/connectors/source_jdbc/config
```



https://repo1.maven.org/maven2/io/debezium/debezium-connector-sqlserver/0.9.5.Final/debezium-connector-sqlserver-0.9.5.Final-plugin.tar.gz





curl -k -s -S -X PUT -H "Accept: application/json" -H "Content-Type: application/json" --data @./register-sqlserver.json http://localhost:8083/connectors/06_sink_jdbc/config



/usr/share/java/kafka-connect-jdbc
/usr/share/java/kafka-connect-jdbc/kafka-connect-jdbc-5.3.0.jar
/usr/share/java/kafka-connect-jdbc/sqlite-jdbc-3.25.2.jar
/usr/share/java/kafka-connect-jdbc/postgresql-9.4-1206-jdbc41.jar
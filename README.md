## Kafkademo

#### This is a spring boot service

All packages are in com.frodo.  
All configuration is in application.properties

Apache Kafka producer. It produces messages of type UserCreatedEvent when new users are inserted into a database.

Topic name is user.created. No messages are allowed on the topic that does  not follow this contract.
All Apache Kafka config is in KafkaProducerConfig

```sh
syntax = "proto3";

package user.event;

message UserCreatedEvent {
  string username = 1;
  string firstname = 2;
  string lastname = 3;
  string email = 4;
  int64 createdat = 5; // Unix timestamp
}
```

### The database
The posgresql testdb database. It has only one table called person. The persons are stored in this table.


```sh
testdb=# \dt
          List of relations
 Schema |  Name   | Type  |  Owner
--------+---------+-------+----------
 public | person  | table | postgres
}
```

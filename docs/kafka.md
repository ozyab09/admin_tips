## Increase replica count

Create the follow file:

```
cat brockers.json
{
    "version":1,
    "partitions":[
        {"topic":"YOUR_TOPIC_NAME","partition":0,"replicas":[2,3,4]},
        {"topic":"YOUR_TOPIC_NAME","partition":1,"replicas":[1,3,4]},
        {"topic":"YOUR_TOPIC_NAME","partition":2,"replicas":[1,2,4]},
        {"topic":"YOUR_TOPIC_NAME","partition":3,"replicas":[1,2,3]},
        {"topic":"YOUR_TOPIC_NAME","partition":4,"replicas":[2,3,4]},
        {"topic":"YOUR_TOPIC_NAME","partition":5,"replicas":[1,3,4]},
        {"topic":"YOUR_TOPIC_NAME","partition":6,"replicas":[1,2,4]},
        {"topic":"YOUR_TOPIC_NAME","partition":7,"replicas":[1,2,3]},
        {"topic":"YOUR_TOPIC_NAME","partition":8,"replicas":[2,3,4]},
        {"topic":"YOUR_TOPIC_NAME","partition":9,"replicas":[1,3,4]},
        {"topic":"YOUR_TOPIC_NAME","partition":10,"replicas":[1,2,4]},
        {"topic":"YOUR_TOPIC_NAME","partition":11,"replicas":[1,2,3]},
        {"topic":"YOUR_TOPIC_NAME","partition":12,"replicas":[2,3,4]},
        {"topic":"YOUR_TOPIC_NAME","partition":13,"replicas":[1,3,4]},
        {"topic":"YOUR_TOPIC_NAME","partition":14,"replicas":[1,2,4]},
        {"topic":"YOUR_TOPIC_NAME","partition":15,"replicas":[1,2,3]}
    ]
}
```

```
kafka-reassign-partitions --zookeeper localhost:2181 --reassignment-json-file brockers.json --execute
```

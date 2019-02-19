## Increase replica count

Create the foolow file:

```
cat brockers.json
{
    "version":1,
    "partitions":[
        {"topic":"full-log","partition":0,"replicas":[2,3,4]},
        {"topic":"full-log","partition":1,"replicas":[1,3,4]},
        {"topic":"full-log","partition":2,"replicas":[1,2,4]},
        {"topic":"full-log","partition":3,"replicas":[1,2,3]},
        {"topic":"full-log","partition":4,"replicas":[2,3,4]},
        {"topic":"full-log","partition":5,"replicas":[1,3,4]},
        {"topic":"full-log","partition":6,"replicas":[1,2,4]},
        {"topic":"full-log","partition":7,"replicas":[1,2,3]},
        {"topic":"full-log","partition":8,"replicas":[2,3,4]},
        {"topic":"full-log","partition":9,"replicas":[1,3,4]},
        {"topic":"full-log","partition":10,"replicas":[1,2,4]},
        {"topic":"full-log","partition":11,"replicas":[1,2,3]},
        {"topic":"full-log","partition":12,"replicas":[2,3,4]},
        {"topic":"full-log","partition":13,"replicas":[1,3,4]},
        {"topic":"full-log","partition":14,"replicas":[1,2,4]},
        {"topic":"full-log","partition":15,"replicas":[1,2,3]}
    ]
}
```

```
kafka-reassign-partitions --zookeeper localhost:2181 --reassignment-json-file brockers.json --execute
```

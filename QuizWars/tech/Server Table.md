#quizwars  #server

### Default ports table

| **Name**           | HTTP | TCP   | gRPC  | WebSocket |
| :----------------- | ---- | ----- | ----- | --------- |
| api-gateway        | 8080 | 8081  | 8082  | 8083      |
| consul             | 8555 |       | 8502  |           |
| users-servcie      |      |       | 21001 |           |
| users-postgres     |      | 15432 |       |           |
| questions-service  |      |       | 22001 |           |
| questions-postgres |      | 15433 |       |           |
| questions-redis    |      | 16379 |       |           |

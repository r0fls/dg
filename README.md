# Docker compose configuration that runs a Galera cluster

## Usage

From within the directory:

```sh
docker-compose up -d --build
```

Verify there are 3 nodes:

```sh
$ sudo docker exec -ti dg_node1_1 mysql -e 'show status like "wsrep_cluster_size"'
+--------------------+-------+
| Variable_name      | Value |
+--------------------+-------+
| wsrep_cluster_size |     3 |
+--------------------+-------+
```


Note this needs to be further adapted to work with nodes on different hosts, which is discussed at www.galeracluster.com [here]
(http://galeracluster.com/2015/05/getting-started-galera-with-docker-part-2-2/).

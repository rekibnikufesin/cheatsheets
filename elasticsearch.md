cluster health:
<server>:9200/_cat/health?v

list of nodes and health:
<server>:9200/_cat/nodes?v

list all indexes:
<server>:9200/_cat/indices?v

search all:
curl -XGET http://10.250.2.241:9200/logstash-2014.11.27/_search?pretty=true&q={'matchAll':{''}}


redis:
redis-cli

LLEN logstash —> length of the log stash queue

curl -XPUT localhost:9200/_cluster/settings -d '{
                "transient" : {
                    "cluster.routing.allocation.enable" : "none"
                }
        }'


curl -XPUT localhost:9200/_cluster/settings -d '{
                "transient" : {
                    "cluster.routing.allocation.enable" : "all"
                }
        }'

curl -XPUT localhost:9200/_cluster/settings -d '{
  "transient" :{
      "cluster.routing.allocation.exclude._ip" : ""
   }
}'
curl -XPUT localhost:9200/_cluster/settings -d '{
  "transient" :{
      "cluster.routing.allocation.include._ip" : ""
   }
}'

curl -XGET 'http://10.250.2.242:9200/_nodes/10.250.2.82/stats/jvm'

sudo mdadm --create /dev/md0 --level=0 --raid-devices=2 /dev/xvdf /dev/xvdg
sudo mkfs -t ext4 /dev/md0

curl -XPOST -d '{ "commands" : [ { "allocate" : { "index" : "logstash-2014.11.20", "shard" : 0, "node" : "elasticsearch-data01", "allow_primary": true } } ] }' http://10.250.2.242:9200/_cluster/reroute?pretty

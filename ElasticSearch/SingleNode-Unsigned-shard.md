Frist find the unsigned index

curl -XGET localhost:9200/_cat/shards?h=index,shard,prirep,state,unassigned.reason | grep UNASSIGNED

Set replicas to 0 for this index.

curl -XPUT "localhost:9200/INDEXNAME/_settings?pretty" -H 'Content-Type: application/json
' -d' { "number_of_replicas": 0 }'
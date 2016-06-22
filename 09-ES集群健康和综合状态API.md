###  集群健康API

curl http://118.192.138.88:9200/_cluster/health?pretty
'''
  "cluster_name" : "elasticsearch",
  "status" : "yellow",
  "timed_out" : false,
  "number_of_nodes" : 1,
  "number_of_data_nodes" : 1,
  "active_primary_shards" : 30,
  "active_shards" : 30,
  "relocating_shards" : 0,
  "initializing_shards" : 0,
  "unassigned_shards" : 30,
  "delayed_unassigned_shards" : 0,
  "number_of_pending_tasks" : 0,
  "number_of_in_flight_fetch" : 0,
  "task_max_waiting_in_queue_millis" : 0,
  "active_shards_percent_as_number" : 50.0
}
'''
***
最重要的一条信息就是集群的状态信息。在上面的例子中可以看到集群处于黄色状态。
为什么是黄色？
    

ElasticSearch总是假定当前节点是集群的一部分，这意味着，索引被分成了不同的部分，即分片（shard），并可能被分配到一些节点上。除此之外ES可以创建这些分片的副本(replica)来处理更多的请求和保持数据一致性。
    

当ES能够根据配置分配所有分片和副本时，集群是可以全面投入使用的。此时是绿色状态。
   
  
黄色状态是表示主分片已经分配完成，已经做好处理请求的准备，但是某些(也可能是所有)副本尚未完成分配。
  
  
最后一个状态是红色状态，意味着ES集群目前尚未准备就绪，其中至少有一个主分片没有准备好。
   
   
当只有一个节点却同时有多个副本时，ES很明显处于黄色状态，因为没有其他节点来放置这些副本。

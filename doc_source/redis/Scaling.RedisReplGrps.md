# Scaling Redis \(Cluster Mode Disabled\) clusters with replica nodes<a name="Scaling.RedisReplGrps"></a>

A Redis cluster with replica nodes \(called *replication group* in the API/CLI\) provides high availability via replication that has Multi\-AZ with automatic failover enabled\. A cluster with replica nodes is a logical collection of up to six Redis clusters where one node, the Primary, is able to serve both read and write requests\. All the other nodes in the cluster are read\-only replicas of the Primary\. Data written to the Primary is asynchronously replicated to all the read replicas in the cluster\. Because Redis \(cluster mode disabled\) does not support partitioning your data across multiple clusters, each node in a Redis \(cluster mode disabled\) replication group contains the entire cache dataset\. Redis \(cluster mode enabled\) clusters support partitioning your data across up to 500 shards\.

To change the data capacity of your cluster you must scale it up to a larger node type, or down to a smaller node type\.

To change the read capacity of your cluster, add more read replicas, up to a maximum of 5, or remove read replicas\.

The ElastiCache scaling up process is designed to make a best effort to retain your existing data and requires successful Redis replication\. For Redis clusters with replicas, we recommend that sufficient memory be made available to Redis\. 

**Related Topics**
+ [High availability using replication groups](Replication.md)
+ [Replication: Redis \(Cluster Mode Disabled\) vs\. Redis \(Cluster Mode Enabled\)](Replication.Redis-RedisCluster.md)
+ [Minimizing downtime in ElastiCache for Redis with Multi\-AZ](AutoFailover.md)
+ [Ensuring that you have enough memory to create a Redis snapshot](BestPractices.BGSAVE.md)

**Topics**
+ [Scaling up Redis clusters with replicas](Scaling.RedisReplGrps.ScaleUp.md)
+ [Scaling down Redis clusters with replicas](Scaling.RedisReplGrps.ScaleDown.md)
+ [Increasing read capacity](Scaling.RedisReplGrps.ScaleOut.md)
+ [Decreasing read capacity](Scaling.RedisReplGrps.ScaleIn.md)
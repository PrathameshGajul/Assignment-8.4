Q1.Explain the difference between FIFO and Capacity scheduler.
Q2.Explain the difference between FIFO and Fair scheduler.
Q3.Explain the difference between Capacity and Fair scheduler.
Ans:
-In the real world the resources are limited and on a busy cluster, an application will often need to wait to have some of its requests fulfilled.
-It is the job of the YARN scheduler to allocate resources to applications according to some defined policy.
-Three schedulers are available in YARN:
1)FIFO Scheduler
2)Capacity Scheduler
3)Fair Scheduler

The difference between the three types of schedulers are:

FIFO Scheduler:
-The FIFO Scheduler places applications in a queue and runs them in the order of submission (first in, first out).
-Requests for the first application in the queue are allocated first; once its requests have been satisfied, the next application in the queue is served, and so on.
-The FIFO Scheduler has the merit of being simple to understand and not needing any configuration, but it’s not suitable for shared clusters.
-Large applications will use all the resources in a cluster, so each application has to wait its turn. On a shared cluster, it is better to use the Capacity Scheduler or the Fair Scheduler.

Capacity Scheduler:
-With the Capacity Scheduler, a separate dedicated queue allows the small job to start as soon as it is submitted.
-This is at the cost of overall cluster utilization since the queue capacity is reserved for jobs in that queue.
-If queues are not designed or used properly, some queues may be overloaded while some may be underutilised.
-Large job finishes late when compared with using the FIFO Scheduler.

Fair Scheduler:
-With the Fair Scheduler, there is no need to reserve a set amount of capacity,since it will dynamically balance resources between all running jobs.
-Just after the first (large) job starts, it is the only job running, so it gets all the resources in the cluster.
-When the second (small) job starts, it is allocated half of the cluster resources,so that each job is using its fair share of resources.
-After the small job completes and no longer requires resources, the large job goes back to using the full cluster capacity again.
-The overall effect is both high cluster utilization and timely small job completion.

Q4.What are the limitations of hadoop 1.x and how they were overcome in hadoop 2.x.
Ans:
-Hadoop 1.x has the following Limitations/Drawbacks:
1)It is not suitable for Real-time Data Processing.
2)It is only suitable for Batch Processing of Huge amount of Data, which is already in Hadoop System.
3)It is not suitable for Data Streaming.
4)It supports upto 4000 Nodes per Cluster.
5)It runs only Map/Reduce jobs.
6)It supports only one Name Node and One Namespace per Cluster.
7)It does not support Horizontal Scalability.
8)It does not support Multi-tenancy Support.
9)It supports only one Name Node and One Namespace per Cluster.
10)It has a single component : JobTracker to perform many activities like Resource Management, Job Scheduling, Job Monitoring, Re scheduling Jobs etc.JobTracker is the single point of failure.

-The major benefits of Hadoop 2.x are:
1)Nodes limitation(4000 to unlimited)
2)Single point of failure
3)JobTracker Bottleneck
4)High availability
5)MapReduce slots are changed from static to dynamic
6)Supports interactive and graph iterative algorithms
7)It allows other applications to integrate with HDFS
8)High Scalability and supports Horizontal scalability
9)Improved cluster utilization
10)Supports multiple namespaces





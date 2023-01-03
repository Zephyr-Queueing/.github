# Zeyphr

Zephyr referes to a larger queueing system which models the following properties:
- Multiple queues are used to encode different service levels
- Polling from the system is effectively "batch" based where a modular distribution model is used to encode the way in which the batch is broken up (i.e. how much from each queuing level)
- Queing in the system is asynchrnous such that batches can be "leased" by a worker in a non-blocking fashion such that individual workers do not block each other as much as possible

The distribution model we are evaluating applies a fast and effective weight rebalancing algorithm based on queuing input to the system. Weights are then rebalanced modestly to best maintain system stability and better keep SLAs for the different service levels. The algorithm allows the system to mitigate workload allocation inefficiency caused by unusual traffic patterns.

Evaluation is completed on CloudLab with a 4 node topology (1 Quartz server, 3 Worker Nodes), for setup and experimentation we have a Zephyr-Queueing-Bench profile that specifies x86 machines and the needed topology. Each worker node is able to scale up by running multiple Isopod instances concurrently which can be specified through the launch script. We scale out by increasing the number of Isopod worker nodes. In a datacenter setting, applications often want to scale up and/or scale out, so in evaluating performance for Zephyr queuing we can capture the scalability improvments around queue rebalancing.

## Components

- Quartz: Weighted Priority Queue + Load Generation + Multithreaded Polling Server
- Isopod: Queue Worker Instance
- Quartz-Model: Shared Message Model
- Experiment: Results including data, parsing script, graphs, and result paper

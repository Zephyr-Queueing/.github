# Zeyphr

Zephyr applies a fast and efficient weight rebalancing algorithm ("Zephyr") to an asynchronous weighted priority queue to mitigate workload allocation inefficiency caused by traffic patterns.

Experimentation is completed on CloudLab with a 4 node topology (1 Quartz server, 3 Worker Nodes), for setup and experimentation we have a Zephyr-Queueing-Bench profile that specifies x86 machines and the needed topology. Each worker node is able to scale up by running multiple Isopod instances concurrently which can be specified through the launch script. We scale out by increasing the number of Isopod worker nodes. In a datacenter setting, applications often want to scale up and/or scale out, so in evaluating performance for Zephyr queuing we can capture the scalability improvments around queue rebalancing.

## Components

- Quartz: Weighted Priority Queue + Load Generation + Multithreaded Polling Server
- Isopod: Queue Worker Instance
- Quartz-Model: Shared Message Model
- Experiment: Results including data, parsing script, graphs, and result paper

# Zeyphr

Zephyr applies a fast and efficient weight rebalancing algorithm ("Zephyr") to an asynchronous weighted priority queue to mitigate workload starvation caused by bursty traffic patterns.

Experimentation is completed on CloudLab with a 4 node topology (1 Quartz server, 3 Isopod worker nodes), for setup and experimentation we have a Zephyr-Queueing-Bench profile that specifies x86 machines and the needed topology. Each worker node is able to scale up by running multiple Isopod instances concurrently. We scale out by increasing the number of Isopod worker nodes (maximum 3 nodes). In a datacenter setting for applications, scaling up and scaling out is a critical component of evaluating performance of the Zephyr queueing model.

## Components

- Quartz: Weighted Priority Queue + Load Generation + Multithreaded Polling Server
- Isopod: Queue Worker Instance
- Quartz-Model: Shared Message Model

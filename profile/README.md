# Zeyphr

Our research applies a fast and efficient weight rebalancing algorithm ("Zephyr") to an asynchronous weighted priority queue to mitigate workload starvation caused by bursty traffic patterns.

Experimentation is completed on CloudLab, in which worker instances are distributed across both threads and machines to mimic a datacenter environment.

## Components

- Quartz: Weighted Priority Queue + Load Generation + Multithreaded Polling Server
- Isopod: Queue Worker Instance
- Quartz-Model: Shared Message Model

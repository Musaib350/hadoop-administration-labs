# Hadoop Administration Labs

A hands-on collection of Apache Hadoop administration labs, infrastructure experiments, configuration exercises, and troubleshooting scenarios.

This repository focuses on understanding, deploying, administering, and troubleshooting distributed Hadoop environments from an infrastructure and operations perspective.

## Objectives

- Understand Hadoop architecture and distributed storage.
- Deploy and manage multi-node Hadoop clusters.
- Configure and administer HDFS.
- Implement HDFS High Availability.
- Understand YARN architecture and resource management.
- Configure Capacity Scheduler and Fair Scheduler.
- Investigate cluster health and service failures.
- Perform practical troubleshooting and root cause analysis.
- Develop operational scripts for Hadoop administration.

## Technology Stack

| Technology | Area |
|---|---|
| Apache Hadoop | Distributed processing and storage |
| HDFS | Distributed file system |
| YARN | Resource management |
| ZooKeeper | Coordination and HA |
| Linux | Infrastructure administration |
| Bash | Operational automation |
| Java | Hadoop ecosystem fundamentals |

## Repository Structure

```text
hadoop-administration-labs/
│
├── architecture/
├── installation/
├── hdfs/
├── yarn/
├── high-availability/
├── troubleshooting/
├── experiments/
├── scripts/
└── README.md
```

## Lab Categories

### 1. Cluster Deployment
- Single-node Hadoop deployment
- Multi-node cluster configuration
- Hadoop configuration files
- Cluster service management

### 2. HDFS Administration
- NameNode and DataNode management
- Block replication
- Heartbeats and block reports
- Safe mode operations
- HDFS High Availability
- Namespace and storage management

### 3. YARN Administration
- ResourceManager and NodeManager
- Application lifecycle
- Scheduler configuration
- Capacity Scheduler
- Fair Scheduler
- Queue management and preemption

### 4. High Availability
- Active and Standby NameNodes
- ZooKeeper integration
- JournalNodes
- Automatic failover
- HA troubleshooting

### 5. Troubleshooting
- DataNode heartbeat failures
- Corrupt and under-replicated blocks
- NameNode safe mode issues
- YARN application failures
- NodeManager connectivity issues
- Disk space and resource-related incidents

### 6. Experiments
- Scheduler comparisons
- Replication factor experiments
- Failure simulation
- Configuration tuning
- Cluster behaviour analysis

## Documentation Standards

Each major lab aims to include:

1. Objective and architecture
2. Prerequisites
3. Configuration files
4. Step-by-step implementation
5. Commands and explanations
6. Validation and expected output
7. Troubleshooting scenarios
8. Observations and conclusions

## Philosophy

The objective is not simply to learn Hadoop commands, but to understand how distributed data infrastructure operates, how failures affect the cluster, and how administrators investigate and resolve operational problems.

**Learning by building. Learning by breaking. Learning by troubleshooting.**

---

*This repository is actively evolving as new labs, experiments, and documentation are added.*

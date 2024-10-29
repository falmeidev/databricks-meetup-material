## Creating the Cluster

- **Cluster**: A set of nodes (computers) working together as a single entity. It consists of a **master node** (driver) and **worker nodes** (slaves):
  - **Driver nodes**: Responsible for coordinating workers and managing parallel task execution.
  
- **Cluster Types**:
  - **Multi-node cluster**: Multiple workers.
  - **Single-node cluster**: No workers; Spark jobs run only on the driver node.

- **Databricks Runtime**: A virtual machine image that includes pre-installed libraries with specific versions of Spark, Scala, and other tools.

- **Photon**: A vectorized query engine developed in C++ to enhance Spark performance.
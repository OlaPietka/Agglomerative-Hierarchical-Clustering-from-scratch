# AgglomerativeHierarchicalClusterFromScratching
Agglomerative hierarchical clustering algorithm from scratch (i.e. without advance libraries such as Numpy, Pandas, Scikit-learn, etc.)

## Algorithm
During the clustering process, we iteratively aggregate the most similar two clusters, until there are $K$ clusters left. For initialization, each data point forms its own cluster.

## Cluster similarity measures
The similarity of two clusters $C_i, C_j$ is determined by a distance measure.

### Single link
$$D(C_i , C_j) = min\{d(v_p , v_q) | v_p \in C_i , v_q \in C_j\}$$

### Complete_link
$$D(C_i , C_j) = max\{d(v_p , v_q) | v_p \in C_i , v_q \in C_j\}$$

### Average link
$$D(C_i , C_j) = mean\{d(v_p , v_q) | v_p \in C_i , v_q \in C_j\}$$

The smaller the distance is, the more similar the two clusters are.
In the equations $d()$, is a distance measure between two data points, i.e. Euclidean distance, defined by:
$$d(p , q) =\sqrt{\sum_{i}^{} (p_i - p_j)^2}$$
where $p_i, q_i$ are dimensions of $p, q$

## Sample usage
```
python main.py -d sample_input.txt -k 4 -m 0
```

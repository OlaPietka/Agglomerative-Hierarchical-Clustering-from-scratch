# AgglomerativeHierarchicalClusterFromScratching
Agglomerative hierarchical clustering algorithm from scratch (i.e. without advance libraries such as Numpy, Pandas, Scikit-learn, etc.)

## Algorithm
During the clustering process, we iteratively aggregate the most similar two clusters, until there are $K$ clusters left. For initialization, each data point forms its own cluster.

## Cluster similarity measures
The similarity of two clusters $C_i, C_j$ is determined by a distance measure.

### Single link
![equation](https://latex.codecogs.com/svg.image?%5Cinline%20%5Cbg%7Bblue%7D%7B%5Ccolor%7BOrange%7D%20D(C_i%20,%20C_j)%20=%20min%5C%7Bd(v_p%20,%20v_q)%20%7C%20v_p%20%5Cin%20C_i%20,%20v_q%20%5Cin%20C_j%5C%7D%7D)

### Complete_link
![equation](https://latex.codecogs.com/svg.image?%5Cinline%20%5Cbg%7Bblue%7D%7B%5Ccolor%7BOrange%7D%20D(C_i%20,%20C_j)%20=%20max%5C%7Bd(v_p%20,%20v_q)%20%7C%20v_p%20%5Cin%20C_i%20,%20v_q%20%5Cin%20C_j%5C%7D%7D)

### Average link
![equation](https://latex.codecogs.com/svg.image?%5Cinline%20%5Cbg%7Bblue%7D%7B%5Ccolor%7BOrange%7D%20D(C_i%20,%20C_j)%20=%20mean%5C%7Bd(v_p%20,%20v_q)%20%7C%20v_p%20%5Cin%20C_i%20,%20v_q%20%5Cin%20C_j%5C%7D%7D)

The smaller the distance is, the more similar the two clusters are.
In the equations `d()`, is a distance measure between two data points, i.e. Euclidean distance, defined by:
![equation](https://latex.codecogs.com/svg.image?%5Cinline%20%5Cbg%7Bblue%7D%7B%5Ccolor%7BOrange%7D%20d(p%20,%20q)%20=%5Csqrt%7B%5Csum_%7Bi%7D%5E%7B%7D%20(p_i%20-%20p_j)%5E2%7D%7D)
where `p_i`, `q_i` are dimensions of `p`, `q`

## Sample usage
```
python main.py -d sample_input.txt -k 4 -m 0
```

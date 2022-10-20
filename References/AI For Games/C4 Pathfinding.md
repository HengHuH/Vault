2022-10-18, 18:45
Status: #reference
Tags: #game #AI

---

# C4 Pathfinding

Pathfinding algorithms use a type of graph called a directed non-negative weighted graph. 

4.2 Dijstra
Algorithm:
    Open List, records all the nodes it has seen, but that haven't had their own iteration yet.
    Close List, track of those nodes that have been processed
    Start，Open List contains only the start  node (with zero cost-so-far), and the close list is empty
    At each iteration, the algorithm choose the node from the open list that has the smallest cost-so-far. The processed node is then remove from the open list and placed on the closed list.
    The basic Dijkstar algorithm terminates when the open list is empty: it has considered every node in the graph that be reached from the start node , and they are all on the closed list.
    For pathfinding, we are only intrested in reaching the goal node, howerver, so we can stop earlier. The algorithm should terminate when the goal node is the smallest node in the open list.
    In practice, the rule is open broken. The first route found to the goal is very often the shortest, and even when there is a shorter route, it is usually only a tiny amount longger. For this reason, many developers implement their path finding algorithms to terminate as soon as the goal node is seen, rather than waiting for it to be selected from the open list.
    Retrieving the Path. The final stage is to retrieve the path.

DS：Simple List, Pathfinding List, Graph
图中节点数 n, 每个节点连接的节点数的平均数 m
Time: O(nm)
Memory: O(nm)

4.3 A-star
The Algorithm:
    A-start works in iterations. At each iteration it considers one node of the graph and follows its outgoing connections. The node (called the current node) is chosen using a selection algorithm similar to Dijkstra, but with the significant difference of the heuristic.
    Open List
    Close List
    c(n) = g(n) + h(n)

    Terminating the Algorithm. In many implementations, A-star terminates when the goal node is the smallest node on the open list. It will not guarantee that the shortest route has been found.We can do this by requiring that the algorithm only terminates when the node is the open list with the smallest cost-so-far has a cost-so-far value greater than the cost of the path we found to the goal. Then and only then can we guarantee that no future path will be found that forms a shortcut.

DS: Pathfinding List, Priority Queues, Priority Heaps, Bucketed Priority Queues
l, the number of nodes whose total estimated-path-cost is less than that of the goal.  l < n
T: O(lm)
M: O(lm)
Node array A-star

A-star with a zero heuristic is the pathfinding version of Dijkstra.

Node Arry A-star

Choosing a Heuristic,  if the heuristic is too low, so that it underestimates the actual path length, A-star takes longer to run. If the heuristic is too high, so that it overestimates the actual path length, A-star may not return the best path.

Euclidean Distance. Euclidean distance is always either accurate or an uderestimate.
Cluster Heuristic.

![[ai_for_games_4_1.png]]

4.4 World Representations

Quantization and Localization. Quantization convert locations in the game into nodes in graph. Localization concert nodes in the plan back into game world locations so that it can move correctly.

Generation. Dividing up a continuous space in to regions and connections for pathfinding.

Validity. It is important to understand the validity properties of graphs created by each division scheme; at the very least it has a major impact on the types of character movement algorithm that can be used.

4.4.1 Tile Graph

Usefulness: vast number of tiles. Characters following the plan will look strange.

4.4.2 Dirichlet Domains

A Dirichlet domain, also refered to as a Voronoi polygon （泰森多边形，又叫冯洛诺伊图）。

Position are quantized by finding the characteristic point that is closest.
The localization of a node is given by the position of the characteristic point that forms the domain.
Validity: Dirichlet domains produce invalid graphs.
Usefulness: Dirichlet domains are very widely used. They have the advantage of being very easy to program and easy to change. It is possible to rapidly change the structure of the pathfinding graph in a level editing program without having to change any level geometry.

4.4.3 Points of Visibility
It can be shown that the optimal path through any 2D environment will always have inflection point at convex vertices in the environment.
We'd recommend looking at navigation meshs instead.

4.4.4 Navigation Meshes
Tile-based graphs, Dirichet domans, and point of visibility are all usefull division schemes to have in your toolbox, but the majority of modern games use navigation meshes for pathfinding.

4.5 Improving on A-star

4.6 Hierarchical Pathfinding

4.7 Other Ideas in Pathfinding
Open Goal Pathfinding. It is rare for game AI to use multiple goals at a great distance from ont another.
Dynamic pathfinding. Dynamic pathfinding is an intreresting modification to the pathfinding algorithm that allows the pathfinder to only recalculate the parts of the plan that may have changed. The dynamic version of A-star is D-star. While it dramaticlay reduce the time required to pathfind in an  uncertain environment.

IDA* -- Iterative Deepening A-star, starts with a "cut-off" value, a total path length beyond which it will stop searching.

SMA* -- Simplified Memory-Bounded A-star

4.8 Continuous Time Pathfinding

4.9 Movement Planning

Just like pathfinding, movement planning uses a graph representation. Connections in the graph represent valid animations; they lead to nodes representing the state of the character after the animation is complete.

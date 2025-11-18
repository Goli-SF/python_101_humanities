---
title: "Analyzing Network Data"
teaching: 180
exercises: 12
---

:::::::::::::::::::::::::::::::::::::: questions 
- What are networks in the sense that we mean in network analysis?
- What is the structure of a network like and what kind of data can be treated as network data?
- What is the difference between network analysis and network visualization?
- When is it meaningful to perform network anaylsis and network visualization?
::::::::::::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::: objectives
- Learn the basics of network science and network analysis. 
- Learn about the structure of network data. 
- Learn to visualize networks. 
::::::::::::::::::::::::::::::::::::::::::::::::

## 1. Basics of Network Analysis

### What are Network Science and Network Analysis?

**Network Science** is an interdisciplinary field that studies complex networks, which are 
structures comprised of interconnected nodes (or vertices) and edges (or links). 
These networks can represent various real-world systems such as social networks 
(for example on social media), transportation networks, biological networks, 
and more. The aim of network science is to understand the topological structure of networks 
and the relationships that can be discovered within them.

**Network Analysis** refers to the methods and techniques used to study and evaluate  
networks. It involves identifying patterns, measuring node importance, analyzing connectivity, 
and understanding the underlying structure and function of the network. 

### When and With Which Type of Data is Network Analysis Useful?

Network analysis is particularly useful when the data can be represented as relationships or 
interactions between entities. Any type of data with this quality can be transformed into network
data. Network data is nothing but a tabular dataset with at least two columns: a `source` column and 
a `target` column. Each of these columns contains the names of the entities that are connected to 
each other in the network. Other columns can contain more information about the connection between
`source` and `target`, including the weight of this connection (identifying how strong it is) or its
type (for example, whether it is a connection between a human and a work of art, or one between 
two humans). 

### Major Types of Networks

There are many different network types. Familiarity with them helps you decide in the future, 
when working with your own data, what network type your data can be converted to optimally analyze
its different features. 

Some important network types include: 

**1. Directed vs. Undirected Networks**

- Directed Networks: In these networks, the edges have a direction, indicating a one-way 
relationship between nodes. For example, in a citation network, if Paper A cites Paper B, 
the link goes from A to B but not necessarily in the reverse direction.

- Undirected Networks: Here, the edges do not have a direction, representing a symmetric 
relationship. An example would be a friendship network where two people are friends with 
each other, and the relationship is mutual.

**2. Weighted vs. Unweighted Networks**

- Weighted Networks: In weighted networks, edges have weights assigned to them, indicating 
the strength or capacity of the relationship. For instance, in a transportation network, 
the weights could represent distances or travel times.

- Unweighted Networks: These networks have edges that are simply present or absent, with no 
additional information about the strength of connections. An example is a simple social 
network where the only consideration is whether or not a connection exists.

**3. Bipartite Networks**

Bipartite networks consist of two distinct sets of nodes, and edges only connect nodes from 
different sets. An example is a movie recommendation system, where one set consists of users 
and the other set consists of movies.

**4. Homogeneous vs. Heterogeneous Networks**

- Homogeneous Networks: These networks consist of nodes of the same type. An example is a 
social network where all nodes represent people.

- Heterogeneous Networks: In these networks, nodes can represent different types of entities. 
For instance, a scientific citation network can include papers, authors, and journals as 
different types of nodes.

## 2. Visualizing Network Data

<span style="color:red">WE ARE HERE. Everything below should be edited and complemented. </span>

``` python
import pandas as pd
from pyvis.network import Network

data_url='https://raw.githubusercontent.com/HERMES-DKZ/python_101_humanities/main/episodes/data/influence_network.csv'
influence_df = pd.read_csv(data_url)

# Step 2: Create a PyVis network
net = Network(directed=True, height='1000px', width='100%')

# Step 3: Add nodes
all_nodes = set(influence_df['source']).union(set(df['target']))

for node in all_nodes:
    color = 'orangered' if node in ['Karl Marx', 'Georg Wilhelm Friedrich Hegel', 
                                    'Immanuel Kant', 'Benedictus de Spinoza', 
                                    'René Descartes', 'Plato', 'Friedrich Nietzsche', 
                                    'Aristotle'] else 'slategrey'
    net.add_node(node, label=node, color=color)

# Step 4: Add edges
for _, row in influence_df.iterrows():
    net.add_edge(row['source'], row['target'], color='darkseagreen', arrows='to')

# Step 5: Generate and save the network visualization
net.save_graph("influence_network.html")
print("FINISHED! Network saved as 'influence_network.html'.")
```

![](fig/output_19.png)


:::::::::::::::::::::::::::::::::::::::: keypoints
- Understand the use cases of network analysis. 
- Visualize networks using the Python library Pyvis.

::::::::::::::::::::::::::::::::::::::::::::::::::



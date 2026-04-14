We have three files containing merger trees from cosmological N-body simulations. The files represent a training, validation, and testing set. The files are located in

- /mnt/ceph/users/fvillaescusa/CosmoBench/CAMELS-SAM/trees/CS_tree_train.pt
- /mnt/ceph/users/fvillaescusa/CosmoBench/CAMELS-SAM/trees/CS_tree_val.pt
- /mnt/ceph/users/fvillaescusa/CosmoBench/CAMELS-SAM/trees/CS_tree_test.pt

The data is stored in PyTorch Geometric format, and can be read as this:

```python
import torch
f_tree = '/mnt/ceph/users/fvillaescusa/CosmoBench/CAMELS-SAM/trees/CS_tree_val.pt'
trainset = torch.load(f_tree, weights_only=False)
```

trainset is now a collection of 5099 PyTorch Geometric graphs. For instance, trainset[0] represents the first merger tree and contains the data in this format:
Data(x=[382, 4], edge_index=[2, 381], edge_attr=[381, 1], y=[1, 2], num_nodes=382, lh_id=100, mask_main=[93], node_halo_id=[382, 1])

The training set contains 14997 merger trees, while the validation and testing set contain 5099 and 4900, respectively.

x represents the node features. There are 4 properties: the first property is log10(mass), the second is log10(concentration), the third one is log10(Vmax), and the fourth one is the scale factor. The scale factor ranges from 0 (beginning of the universe) to 1 (current time). The mass goes from 10 to 15. Each node represents a dark matter halo and is characterized by the four values mentioned above.

y is the value of the cosmological parameters, Omega_m and sigma_8. Omega_m ranges from 0.1 to 0.5, while sigma_8 goes from 0.6 to 1.0.

For both node and graph features, you may want to normalize each feature to have mean 0. 

The merger trees come from N-body simulations. For each simulation, there are 25 different merger trees chosen randomly. All merger trees from the same simulation will have the same value of the cosmological parameters, i.e. the same values of y.

Please come up with an interesting idea to carry out with this data. Make sure the above data is used for the task. Do not create dummy data. For your analysis, do not use the lh_id, mask_main, and node_halo_id information stored in the merger trees as those fields represent dummy information. Since data is large and complex, we recommend that you first write and test the code on subset of the data instead of writing code to analyze all data. This is because you may make mistakes and running the codes on the full data is expensive. If the code you write works for a subset of the data, modify it to be used with the whole data.

Note that PyTorch and PyTorch Geometric are already installed. You have access to a node that has 10 cpus and 1 gpu. Please make lots of plots to illustrate your findings.
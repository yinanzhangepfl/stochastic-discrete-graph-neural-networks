# stochastic-discrete-graph-neural-networks
Yinan Zhang, Beril Besbinar

## Overview
The code in this directory is implemented for my semester project "Multi-graph classifcation with discrete stochastic graph neural networks" at LTS4, EPFL. In this study, we are interested in classifying cancerous patients represented by a a bag of cell-graphs constructed from mIHC data. Yet, each multi-graph  bag not only contains discriminative graphs useful for classification, but also redundant graphs whose characteristics are shared among all or most entities in the dataset. In order to solve this problem, we propose an algorithm for jointly learning graph embedding and graph sampling. Our framework introduces stochastic layers with discrete random variables into traditional graph neural networks. Experiments results show that this algorithm is effective no matter one graph or multiple graphs need to be selected.

## Dataset
We create two synthetic datasets corresponding to the scenario of single-graph selection and multi-graph selection respectively.  
An example from dataset A:
![](gv1.png)
An example from dataset B:
![](gv2.png)

## Structure 
Models:  
diff_pool6_max.py: for pre-training, using max aggregator  
diff_pool6_avg.py: for pre-training, using mean aggregator  
gumbel_softmax.py: for joint training  

Data-Generation.ipynb: generate dataset A and B corresponding to single-graph selection and multi-graph selection respectively  
Dataset-Characteristics: basic statistics for multi-graph bags    
GraphEmbedding.ipynb: visualize pre-trainined graph embeddings  
PatientClassification-pretrain.ipynb: pretrain graph embedding and classifcation layers  
PatientClassification-joint.ipynb: jointly learning graph embedding and graph sampling  
Plot-LogSoftmax-avg.ipynb, Plot-LogSoftmax-max.ipynb: pre-training results  
Plot-LogSoftmax-gumbel-datasetA.ipynb: joint learning results in the scenario of single-graph selection  
Plot-LogSoftmax-gumbel-datasetB.ipynb: joint learning results in the scenario of multi-graph selection

## Conclusion
Either in the scenario of single-graph selection or multi-graph selection, our proposed algorithm shows satisfactory classification and sampling accuracy. For future work, we could figure out other permutation-invariant methods to aggregate sampled graphs to reduce information loss. Moreover，we can improve the sampling method to avoid selecting the same graph multiple times.


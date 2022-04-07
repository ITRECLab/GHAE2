
# Requirements

- Anaconda3 (python 3.6)
- Pytopyrch 1.3.1
- gensim  3.6.0
- numpy


Run
------------
    step1. 1_Get_go_information.py: getting go information for each PPI network from go_slim_mapping.tab.txt.
    step2. 2_Node_embedding: generating vector representations for each protein based on two matrixes for a PPI network.
    step3. 3_Update_linking_weight.py: updating the weight of each edge in a PPI network based on calculating cosin similarity with vector representations.
    step4. 4_cluster_core_attachment.py: generating complexes based on the structure of core and attachments.
    step5. 5_Compare_performance.py: compare the preformance of GANE with other classic methods based on different evaluation metrices.
# 2_Node_embedding Easy Run

```
cd ./model/code/
python train.py
```
This module is responsible for generating the embedding of protein nodes

You may change the dataset by modifying the variable "dataset = biogrid'" in the top of the code "train.py" or use arguments (see train.py). 


# Prepare for your own dataset

The following files are required:

    ./model/data/YourData/
        ---- YourData.cites                // the PPI network adjcencies
        ---- YourData.content.text         // the features of discription
        ---- YourData.content.F       // the features of F GO attributes
        ---- YourData.content.P        // the features of P GO attributes
        ---- train.map                     // the index of the training node
        ---- vali.map                      // the index of the validation nodes
        ---- test.map                      // the index of the testing nodes



You can see the example in ./2_Node_embedding/model/data





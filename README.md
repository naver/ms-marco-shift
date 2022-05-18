# Toward A Fine-Grained Analysis of Distribution Shifts in MSMARCO (MS-Shift) [(arxiv)](https://arxiv.org/abs/2205.02870)

*Simon Lupart* and *Stéphane Clinchant*

## Abstract

Recent IR approaches based on Pretrained Language Models (PLM) have now largely outperformed their predecessors on a variety of IR tasks. However, what happens to learned word representations with distribution shifts remains unclear. Recently, the BEIR benchmark was introduced to assess the performance of neural rankers in zero-shot settings and revealed deficiencies for several models. In complement to BEIR, we propose to control \textit{explicitly} distribution shifts. We selected different query subsets leading to different distribution shifts: short versus long queries, wh-words types of queries and 5 topic-based clusters. Then, we benchmarked state of the art neural rankers such as dense Bi-Encoder, SPLADE and ColBERT under these different training and test conditions. Our study demonstrates that it is possible to design distribution shift experiments within the MSMARCO collection, and that the query subsets we selected constitute an additional benchmark to better study factors of generalization for various models.

## Repository description
This repository contains all data files required to reproduced the experiments made in our work, splitted in the two TRAIN/EVAL folders. In addition, we also included an example notebook with cluster vizualisation.
### TRAIN/EVAL :open_file_folder:
- `TRAIN/queries_clustering.tsv` is the repartitions of queries in each clusters. 
```
Format is the following:
{query, topic_cluster, topic_train, whword_cluster, whword_train, length_cluster, length_train}
```
where `topic_cluster` is in the range [0-4]+[5] for all 'others' queries; `whword_cluster` in the range [0-2]+[3] {0:{what, definition}, 1:{how}, 2:{who, when, where, which}, 3:'others'}; `length_cluster` in the range [0-1] (0:short, 1:long). We also included the `train` columns to specify on which queries to train on.

- `EVAL` contains the evaluation `qrel.json` and `queries.tsv` using the usual MS MARCO format.

### Visualization of the clusters :telescope:
- In `example/shift_visualization.ipynb` we included scripts to display the PCA and T-sne of the clusters, together with the computation of similarities between clusters.


## Cite
Please cite our work as:
```
@misc{https://doi.org/10.48550/arxiv.2205.02870,
  doi = {10.48550/ARXIV.2205.02870},
  url = {https://arxiv.org/abs/2205.02870},
  author = {Lupart, Simon and Clinchant, Stéphane},
  keywords = {Information Retrieval (cs.IR), FOS: Computer and information sciences, FOS: Computer and information sciences},
  title = {Toward A Fine-Grained Analysis of Distribution Shifts in MSMARCO},
  publisher = {arXiv},
  year = {2022},
  copyright = {Creative Commons Attribution Non Commercial Share Alike 4.0 International}
}
```

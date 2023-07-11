# KI-QFS
This repository contains codes and KI-QFS dataset described in the paper "Tackling Query-Focused Summarization as A Knowledge-Intensive Task: A Pilot Study". The paper is accepted by [GenIR@SIGIR 2023](https://coda.io/@sigir/gen-ir/accepted-papers-17) workshop.


## Updates

- [x] data description
- [ ] relevance annotation
- [ ] codes


## Data Description

The dataset is based on DUC 2005-2007 datasets in [NIST](https://www-nlpir.nist.gov/projects/duc/data.html). Please ask for their data access before using our dataset. The dataset is located in `dataset/`. Please refer to the [paper](paper/kiqfs.pdf) for more details of the dataset.

### Data Structure

We repurpose the DUC datasets for a knowledge-intensive task, spliting them into input-output pairs and a knowledge corpus. <br>
For the pairs, we also divide them into train, validation, and test splits, which are `kiqfs_pairs_train/val/test.jsonl`. For each `*.jsonl`. The data format is:

```python
{
    'id': 'D301I', # original id for each cluster on DUC Datasets
    'query': 'Nobel prizes are awarded each year for achievement...',
    'summaries': ['s1', 's2', ..., 'sn'] # a list of summaries
}
```

For knowledge corpora, we consider three alternatives: 

<ul>
    <li>Internal corpus</li>
    <li>External corpus</li>
    <li>Augmented corpus</li>
</ul>

The Internal corpus is `kiqfs_internal_knowledge.json`, which only contain documents from the DUC datasets. The data format is:

```python
{
    'D301I': [{'title': 'FT 02 NOV 94...', 'text': 'CRIME WITHOUT FRONTIERS By...'}, ...] # a list of documents in the cluster  D301I,
    ... # all clusters
}
```

For external corpus, we use Wikipedia dump `kilt_w100_title.tsv` from [KILT Benchmark](https://github.com/facebookresearch/KILT/tree/main/kilt/retrievers#DPR). Please follow their instructions to download the data. <br>
We also provide processed version of internal corpus `kiqfs_internal_w100_title.tsv`, which has the same data format with `kilt_w100_title.tsv`. <br>
For augmented corpus, we simply combine previous two corpora to form it.


## Relevance Annotation

TODO


## License
KI-QFS is MIT licensed. See the [LICENSE](LICENSE) file for details.
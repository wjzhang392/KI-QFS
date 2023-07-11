# KI-QFS
The reposity contain KI-QFS codes and dataset described in the paper "Tackling Query-Focused Summarization as A Knowledge-Intensive Task: A Pilot Study". The paper is accepted by [GenIR@SIGIR 2023 workshop](https://coda.io/@sigir/gen-ir/accepted-papers-17).


## Updates

- [x] Release datasets
- [ ] Release relevance annotation
- [ ] Release codes


## KI-QFS Data Descirption

The dataset is based on [DUC 2005-2007](https://www-nlpir.nist.gov/projects/duc/data.html). Please ask for the data access before using our dataset. 

### Data Structure

The dataset repurpose the DUC datasets into a knowledge-intensive dataset, which are divided into query-summary paris and knowledge corpus. Please refer to the [paper](paper/kiqfs.pdf) for more information. <br>
For the former, we split the pairs into train, validation, and test split, which are `kiqfs_pairs_train.jsonl`, `kiqfs_pairs_val.jsonl`, and `kiqfs_pairs_test.jsonl`. For each `*.jsonl`, the data format is:
```python
{
    'id': 'D301I', # original id for each cluster on DUC Datasets
    'query': 'Nobel prizes are awarded each year for achievement...',
    'summaries': ['s1', 's2', ..., 'sn'] # a list of summaries
}
```

For the latter, we consider three knowledge corpora, including internal, external, and argumented corpora. Internal corpus is `kiqfs_internal_knowledge.json`, in which the data format is:

```python
{
    'D301I': [{'title': }] # ,
    ...
}

```
For external corpus, we leverage Wikipedia dump `kilt_w100_title.tsv` in [KILT Benchmark](https://github.com/facebookresearch/KILT/tree/main/kilt/retrievers#DPR). Please follow the instructions of KILT to download the corpus.
Besides, we also provide processed version of internal corpus `kiqfs_internal_w100_title.tsv`, which has the same data format with `kilt_w100_title.tsv`.


### KI-QFS relevant annotation

TODO





## License
KI-QFS is MIT licensed. See the [LICENSE](LICENSE) file for details.
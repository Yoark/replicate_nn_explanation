# Attention is not not Explanation (**replication**) by Zijiao Yang

Code for replication of the EMNLP 2019 paper *[Attention is not not Explanation](https://www.aclweb.org/anthology/D19-1002/)* by Wiegreffe & Pinter.

*[Attention is not Explanation](https://arxiv.org/abs/1902.10186)*. is related.



This code is based on two repos: [Wiegreffe & Pinter](https://github.com/sarahwie/attention),  [Jain & Wallace](https://github.com/successar/AttentionExplanation)



Dependencies
--------------
Please refer to the installation instructions for the repository provided by [Jain & Wallace](https://github.com/successar/AttentionExplanation). The same dependencies are used.
Also, make sure to export the meta-directory into which you clone `attention` to your PYTHONPATH in order for the imports to work correctly. For example, if the path to the cloned directory is `/home/users/attention/`, then run `export PYTHONPATH='/home/users'`.

Data Preprocessing
--------------
Please perform the preprocessing instructions provided by Jain & Wallace [here](https://github.com/successar/AttentionExplanation/tree/master/preprocess). We replicated these instructions for the `SST`, `IMDb`, `AgNews`, and `20News` datasets.

Running Baselines
--------------
I replicate the reported baselines in Wiegreffe & pinter, Table 2 by running the following commands:
- `./run_baselines.sh [AgNews, 20News_sports, imdb, sst]`

Freezing the Attention Distribution (Section 3.2)
--------------

- `./run_frozen_attention.sh [AgNews, 20News_sports, imdb, st]`

## Guiding simpler Models (Section 3.4)

* `python -W ignore train_and_run_experiments_bc.py --dataset [some dataset] --data_dir . --output_dir [path/to/save/model] --attention pre-loaded --gold_label_dir [path/to/saved/model/with/attentions] --encoder average`

Running Adversarial Model Experiments (Section 4)
--------------
- `./run_adversarial.sh [AgNews, 20News_sports, imdb, sst] [lambda_value] [path/to/saved/model/with/gold/attentions/and/predictions]`

Remaining Todos
--------------
- Fix the bug for variance baseline **section 3.3**

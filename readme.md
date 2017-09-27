# cross_domain_embedding emnlp 2017

To run the cre.c, you need to compile it using any C compiler first.

Then:

1). learn word embeddings from source domain using word2vec. A binary file will be generated.

2). generate a similarity score file. One line per word in '$word$ $score$' format. The word should appear in both the source and the target domain. The score must be a positive real number.

3). run the cre program. Note that the size parameter (dimension of embeddings) should match the dimension of the embeddings from 1).

Sample:

```
./cre -train estweet.txt -model vec_enwik9.bin -similarity sim.txt -output estweet_enwik9_10.bin -size 50 -window 5 -binary 1 -lambda 10 -threads 2
```


Please cite the following if you refer to our paper:

```
@InProceedings{yang-lu-zheng:2017:EMNLP2017,
  author    = {Yang, Wei  and  Lu, Wei  and  Zheng, Vincent},
  title     = {A Simple Regularization-based Algorithm for Learning Cross-Domain Word Embeddings},
  booktitle = {Proceedings of the 2017 Conference on Empirical Methods in Natural Language Processing},
  month     = {September},
  year      = {2017},
  address   = {Copenhagen, Denmark},
  publisher = {Association for Computational Linguistics},
  pages     = {2888--2894},
  abstract  = {Learning word embeddings has received a significant amount of attention
	recently. Often, word embeddings are learned in an unsupervised manner from a
	large collection of text. The genre of the text typically plays an important
	role in the effectiveness of the resulting embeddings. How to effectively train
	word embedding models using data from different domains remains a problem that
	is less explored. In this paper, we present a simple yet effective method for
	learning word embeddings based on text from different domains. We demonstrate
	the effectiveness of our approach through extensive experiments on various
	down-stream NLP tasks.},
  url       = {https://www.aclweb.org/anthology/D17-1311}
}
```

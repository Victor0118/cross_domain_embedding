# cross_domain_embedding emnlp 2017

To run the cre.c, you need to compile it using any C compiler first.

Then:

1). Learn word embeddings from source domain using word2vec toolkit (https://code.google.com/archive/p/word2vec/). Add -bin argument to generate binary output format.

2). Generate a similarity score file. One line per word in '$word$ $score$' format. The word should appear in both the source and the target domain. The score must be a positive real number. The score file in the paper is generated through word frequency from corpus of two domains.

3). Run the cre program. Note that the size parameter (dimension of embeddings) should match the dimension of the embeddings from step 1).

Sample:

```
./cre -train <target_corpus_file.txt> -model <binary_embedding.bin> -similarity <similarity_score.txt> -output <output_name.bin> -size 50 -window 5 -binary 1 -lambda 10 -threads 20
```


Please cite the following paper:

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
  url       = {https://www.aclweb.org/anthology/D17-1311}
}
```

Contact w85yang@uwaterloo.ca if you have further question on the code.

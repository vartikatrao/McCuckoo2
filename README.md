# McCuckoo2
A simple interpretation and implementation of Multi-Copy Cuckoo hashing but using counting bloom filters and linear probing in stash. 

This was made as part of a research project on hashing based on the following paper:
[D. Li, R. Du, Z. Liu, T. Yang and B. Cui, "Multi-copy Cuckoo Hashing," 2019 IEEE 35th International Conference on Data Engineering (ICDE), Macao, China, 2019, pp. 1226-1237, doi: 10.1109/ICDE.2019.00112.](https://ieeexplore.ieee.org/document/8731423)

## Introduction
Cuckoo Hashing is a technique for implementing a hash table. Unlike most other hash tables, it achieves constant time worst-case complexity for lookups. However, insertion might lead to cycles that are tough to break out of and causes computation of the hash function multiple times. These problems can be handled using Multi-copy cuckoo hashing. 

Multi-Copy Cuckoo Hashing inserts copies of keys into multiple hash tables simultaneously, so when multiple candidate buckets are available, it is not necessary to randomly select a candidate bucket when inserting. This improves lookup time. It is a proactive approach unlike cuckoo hashing which is more reactive. However, the probability of rehashing stays the same; hence, an additional stash is used to store keys to temporarily delay the need for rehashing. 

![image](https://user-images.githubusercontent.com/100116788/219965908-36558337-6907-467b-be19-c0d92ad62447.png)

# Information Retrieval  

## Phase 1: Query answerer using simple inverted indexes  

In this phase, tokenization and specific Persian normalization were developed in the following order:  

- Tokenization --> tokenize()  
- Normalization  
    - equalize_chars()  
    - delete_pishvand()  
    - root_of_verbs()  
    - del_stop_w()  
    - del_punctuations()  
    - mokasar()  
    - del_pasvand()  
- Building inverted indexes  
- Answering single and multi word queries (not in a ranked display) by outputting the relative link.  

## Phase 2: Ranked query answerer using tf-idf, heap, and Champion lists  

This phase contains the implementation of some famous efficiency boosting techniques in NLP. The developed methods respectively are:  

- Building Weighted Inverted Index using tf-idf vector representation, resulting from the following equation:  

![tf-idf equation](tf-idf-equation.png?raw=true)  

Where ft,d stands for the number of repetitions of word t in document d, and nt is the number of documents in which the word t has appeared.   
- Employing Index elimination technique to reduce the occupied space.  
- Similarity calculation using cosine-sim through the following equation:  

![tf-idf equation](cosine-sim-equation.png?raw=true)  

- Building tf based Champion lists  
- Outputting K-top results using max-heap  

## Phase 3: Optimizing the retrieval system with the assistance of K-means clustering and KNN classification.  

When the volume of our data increases, we need to apply more efficient methods to exceed the time and space limitations, using the following algorithms:  

- K-means: we cluster the documents through this algorithm with k = 10 and 30 iterations. Responding to a query is by first computing the similarity of the query to the centroids, choosing the highest one, and then finding the responses in that cluster.  

- KNN: Using this algorithm, we implement a classification system with 5 categories including "health", "politics", "sports", "culture",and "economy". This engine labels the documents and sets k to 5. The input query format should be as follows:  

```
cat:<cat> <query>

For example: 
cat:health کرونا
```


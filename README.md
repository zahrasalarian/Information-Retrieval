# Information Retrieval  

## Phase 1: Query answerer using simple inverted indexes  

In this phase, tokenization and specific persian normalization were developed in the following order:  

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

This phase contains the implementation of some famous efficiancy boosting technics in NLP. The methodes were developed respectively:  

- Building Weighted Inverted Index using tf-idf vector representation, resulting from the following equation:  

![tf-idf equation](tf-idf-equation.png?raw=true)  

where ft,d stands for number of repetitions of word t in document d, and nt is the number of documents in which the word t has been appeared.  
- Employing Index elimination technique to reduce the occupied space.  
- Similarity calculation using cosine-sim through the following equation:  

![tf-idf equation](cosine-sim-equation.png?raw=true)  

- Building tf based Champion lists  
- Outputting K-top results using max-heap  
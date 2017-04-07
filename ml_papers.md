# NLP
### Question Pair
- __Duplicate Question Detection using Online Learning__, Siu Project Report
	- He uses online Latent Dirichlet Allocation(topic modelling), Word2Vec embeddings(instead of bag of words he sums),Latent Semantic Indexing( SVD applied to bag-of-words). Before those: tokenizer,stop-words removal,stemming.
    - He evaluates the duplicates with cosine similarity.
    - Uses random forest to train, gets 80% recall, which is not informative alone. You can label everything true and get 100%.

- __Towards Generalizable Sentence Embeddings__ , Eleni et.al.
    + They start from Skipthougt idea, which is the application of skip-gram to sentences. It could be next paper to read and they conbine it with sentence embeddings. They want to improve on this by including some supervised information to the embeddings.
    + They refer 'BOW AutoEncoder' model(Lauly et al, 2014) and 'RNN AE' model (Zhu et. al.). So what they do basically train these models with SNLI dataset(Bowman et al, 2015) and finetune each embedding: 'RNN AE', 'BOW AE', 'Skipthougts'. 
    + They show that finetuned versions work better in classification setting like in (MR,SUBJ,TREC). There are more experiment, but the paper is a bit hard to follow. 
    + Their results agree with Hill et al.(2016) saying BOW(bag of words)models perform better in general, espcially in similarity tasks. But they argue that this is not necesarrily a sign of good embedding. They propose an example method at the end of the paper and say that the finetuned versions look better. 
    + They believe that supervised tasks are not a good measure of embedding quality.

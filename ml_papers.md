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
    
- __Language Modeling with Gated Convolutional Networks__, Yann Dauphin, Facebook AI
    + Gated convolutional networks are both more efficient and accurate(perplexity) then RNN-based previous state of art models.
    + Gated units help the gradient pass through stages ontouched and helps the training. Adaptive softmax is used.
    + Google bilion dataset, wikitest 103 are the datasets and models are evaluated with perplexity.
    + They used only one GPU and trained it for two weeks and got better results then LSTM trained in 32 GPU's for 3 weeks.
    + In the experiments they show that
        * GLU is better then other activation mechanisms like Tanh,Relu,GTU.
        * Non-linearity like GLU helps model a lot (compare to Linear,Bilinear).
        * Network depth makes the result better.
        * Context size around 20-30 is enough for good results. You don't need unlimited context like we have in LSTM's
        * Gradient clipping and weight normalization makes the training considerably faster.
    + Convolutional networks are better to parallize compare to RNN and have a better responsiveness than RNN's.

- __Double Backpropagation__, Yann Lecun, Bell Labs
    + Double backpropagation is a method enforces input gradient to be smaller in time and improves generalization.
    + A very simple network with architecture 2-2-2 is used to motivate the algorithm. After forward-backward pass, a second loss is calculated at inut gradients enforces it to be zero. And then this new loss is backpropagated in the second part.
    + The algorithm is basically forward pass-backward pass(don't update)- forward at upper network-backward(all together)- update weights using both backward updates. 
    + Giving double learning rate to the second backprop result in better generalization error.

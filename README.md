# Unsupervised_Sentiment_Analysis


- Motivation: Negative and positive words usually are surrounded by similar words. 

- Data Preprocessing: After cleaning the text data, I used gensim’s implementation of word2vec algorithm with CBOW architecture to preprocess each sentence. 

- Clustering: I utilized K-Means to cluster each word into 5 categories(Very positive, positive, neutral, negative, very negative) and found out the coordinates of each centroids. Since each word can be assigned with a sentiment score based on the cluster to which they belong (Very positive = 5, positive = 4, neutral = 3, negative = 2, very negative = 1), I multiplied this score by how close they were to their cluster to weigh how potentially positive/negative they are. In this case, I was able to create a dictionary where each word had it’s own weighted sentiment score. 

- Word Vectorization: Introducing TfidfVectorizer, it is possible to take the word frequency into account for each sentence, thus increasing positive/negative signal associated with words that are highly specific for given sentence in comparison to whole corpus. Finally, all words in every sentence were on one hand replaced with their tfidf scores, and on the other with their corresponding weighted sentiment scores.

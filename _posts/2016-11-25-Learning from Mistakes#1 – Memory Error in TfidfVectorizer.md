I was trying to extract n-gram features from a large dataset and got a memory error. I was using TfIdfVectorizer of scikit-learn. And the error was from the large sparse matrix. I was not surprised as I was not sure if my 32GB ram is enough for around 1 million documents. However, I solved the error by the following steps.

1. I changed the min_df parameter to 0.2. Here is the explanation of min_df parameter in scikit-learn.\\
*min_df* : float in range [0.0, 1.0] or int, default=1.\\
When building the vocabulary ignore terms that have a document frequency strictly lower than the given threshold. This value is also called cut-off in the literature. If float, the parameter represents a proportion of documents, integer absolute counts. This parameter is ignored if vocabulary is not None.
So by changing this, I am limiting the size of the vocabulary. That helps to reduce the memory size.

2. I used Regexptokenizer and Porter stemmer to tokenize and stem the words. Stemming reduces the variation of words. So it greatly helps to reduce the vocabulary size.

After doing these 2 little fixes, I got rid of the memory error 🙂 Basic problem was to reduce the vocabulary size. By the way, I was removing the stop words and lower casing from earlier.

 

_Learning from Mistakes is a series where I will post the little challenges I face during my experiments and how I fix them. I hope someone in this world is facing the same problem and my goal is to help them._
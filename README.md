
<H2>Backoff</H2>


The provided code implements a **Backoff Language Model**, which is used to estimate the probabilities of word sequences (n-grams) in natural language processing. Here’s a concise explanation of how the code works:

1. **Class Definition**: 
   - The `BackoffLanguageModel` class is initialized with a parameter $$ n $$ that specifies the maximum order of n-grams (e.g., unigrams, bigrams, trigrams). It uses a `defaultdict` to store counts of n-grams.

2. **Training the Model**:
   - The `train` method processes input sentences, splitting each sentence into tokens (words) and generating n-grams of orders from 1 to $$ n $$. It counts the occurrences of each n-gram and stores them in the `ngrams` dictionary.

3. **Calculating Probabilities**:
   - The `backoff_probability` method computes the probability of a given n-gram. If the n-gram exists, its probability is calculated as the ratio of its count to the total count of n-grams of that order.
   - If the n-gram is not found, the method backs off to lower-order n-grams by removing the first word and checking for their counts, applying a scaling factor (0.4) if found. If no valid n-gram is found, it returns zero probability.

4. **Example Usage**:
   - The model is trained with three example sentences, and then it calculates and prints probabilities for specific trigrams, bigrams, and unigrams.

This model helps handle situations where certain n-grams may not have been observed during training, making it useful for language modeling tasks where data may be sparse.






<img width="1440" alt="Screenshot 1403-08-25 at 20 47 10" src="https://github.com/user-attachments/assets/5003fe7f-8234-4db0-8893-a6d62d0869c3">


---

<H2>Stupid Backoff</H2>

The provided code implements a language model called **Stupid Backoff**, which is used to estimate the probabilities of word sequences (n-grams) in natural language processing. 

1. **Class Definition**: 
   - The class `StupidBackoffLanguageModel` is defined with a parameter $$ n $$ (the maximum n-gram order) and uses a dictionary to store counts of n-grams.

2. **Model Training**:
   - The `train` method takes input sentences, splits them into various n-grams (from unigrams to n-grams of order $$ n $$), and records the counts of each n-gram.

3. **Probability Calculation**:
   - The `stupid_backoff_probability` method calculates the probability of a specific n-gram. If the n-gram exists, its probability is computed as the ratio of its count to the total count of similar n-grams.
   - If the n-gram is not found, the model backs off to lower-order n-grams (using a fixed scaling factor of 0.4) and continues this process down to unigrams.

4. **Example Usage**:
   - In the example section, the model is trained with three sentences, and then it calculates and prints the probabilities for specific trigrams, bigrams, and unigrams.

This model is appreciated for its simplicity and efficiency in natural language processing applications, especially in scenarios where data is sparse.


<img width="1440" alt="Screenshot 1403-08-25 at 20 48 26" src="https://github.com/user-attachments/assets/746cdffa-c5e3-4889-bcd1-c4bbf2956ac6">


---

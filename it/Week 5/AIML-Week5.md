## Natural Language Processing (NLP)

Natural Language Processing (NLP) is a branch of Artificial Intelligence (AI) that focuses on the interaction between computers and human (natural) languages. The ultimate goal of NLP is to enable computers to understand, interpret, generate, and respond to human language in a valuable and meaningful way.

## NLP Working

[Input Text]
     ↓
[Text Preprocessing]
     ↓
[Feature Extraction]
     ↓
[Modeling using ML/DL Algorithms]
     ↓
[Output: Classification / Translation / Sentiment etc.]

### Input Text
Input Text refers to any human-generated natural language data that is given to a computer system to analyze or understand.

This can include:
Sentences
Paragraphs
Conversations
Tweets, Emails, Reviews, News articles, etc.
These inputs are raw and unstructured, meaning they don’t follow any strict format like a spreadsheet or database. NLP systems aim to make sense of this unstructured text.

Example:
Let’s say you’re building an NLP model to detect sentiment from movie reviews.
Input Text: “The movie was incredibly boring and way too long.”
At this stage, the machine:
1. Has no understanding of whether this is positive or negative.
2. Treats it as a sequence of characters or a blob of text.
That’s why we move on to preprocessing next — to convert it into something the machine can work with.

### Text Preprocessing
Text preprocessing in Machine Learning refers to the series of steps
used to clean, transform, and standardize raw textual data so it can
be effectively used by machine learning algorithms.

**Steps in Text Preprocessing:**

→ Lowercasing
→ Removing Punctuation
→ Removing Stop Words
→ Removing Emojis
→ Spelling Corrections
→ Chat Words
→ Removing the Accents
→ Removing Html tags and Urls
→ Removing Digits
→ Removing Extra Whitespaces
→ Tokenization
→ Stemming
→ Lemmatization

![image](https://github.com/user-attachments/assets/a4145b80-2059-44de-a5e0-e88c79139a21)

**1. Lowercasing**
→ Converts all characters to lowercase to avoid treating “Machine”
and “machine” as different words.
→ Lowercasing is the process of converting all characters in text to
lowercase.
→ It ensures consistency and prevents the model from treating the
same words in different cases as different entities

**2. Removing Punctuation and Special Characters**
→ Cleans up symbols that don’t add meaning.
It is removed because:
1. Reduce noise in text.
2. Decrease feature space by eliminating irrelevant tokens.
3. Helps machine learning models focus on meaningful patterns

**3. Removing Stopwords**
→ Removes common words that don’t add much value (like “is”,
“the”, “and”).
→ Stopwords are commonly used words in a language that carry
minimal or no semantic meaning on their own and are usually
filtered out before processing natural language data.
→ Examples in English: “is”, “the”, “and”, “in”, “of”, “on”, “to”, “with”

**4. Emojis**
→ Detects, replaces, or removes emojis from text.

**5. Spelling Corrections**
Automatically corrects misspelled words in a string.
Spelling Correction refers to the process of identifying and
correcting misspelled words in text. It’s essential in:
→ Text preprocessing (for chatbots, NLP models)
→ Search engines (query correction)
→ Spell-checkers in writing tools

**6. Removing the Accents**
→ Accents are special marks added to letters in many languages
(especially French, Spanish, German, etc.) to change pronunciation
or meaning.
→ Standardizing text across languages
→ Preparing data for search, matching, or tokenization
→ Avoiding duplication (e.g., résumé and resume treated separately)

**7. Removing Extra Whitespaces**
Why Remove Extra Whitespaces?
Extra spaces (like tabs, newlines, multiple spaces) can:
→ Mislead tokenizers, word counters, and vectorizers
→ Affect string matching
→ Waste memory or cause inconsistent text formatting

**8. Tokenization**
Tokenization is the process of breaking down text into smaller
units, called tokens. These tokens can be:
→ Words (word-level tokenization)
→ Sentences (sentence-level tokenization)
→ Subwords or characters (for deep learning)
It converts raw text into a structure that can be analyzed or
modeled.
Why Tokenization Matters?
-> Enables word frequency analysis
-> Required for vectorization (Bag of Words, TF-IDF, word
embeddings)
-> Essential for text classification, NER, POS tagging, and more
-> Prepares text for deep learning models like RNNs or Transformers

![image](https://github.com/user-attachments/assets/5a4594a1-1933-4764-835c-5ef1ef00aef6)


**9. Stemming**
Stemming is the process of converting words into their base form / root word by removing the suffixes.
We have 3 types of stemmers
a. Porter stemmer
b. Lancaster stemmer
c. Snowball stemmer

→ Porter stemmer is used for English language only. And the output
of with Porter stemmer is smooth. (ex : comes → come )
→ Lancaster stemmer is used for English language only. And the
output of with Lancaster stemmer is aggressive. (ex : comes → com )
→ Snowball stemmer is used for Multiple languages. And the output
of with Snowball stemmer is aggressive.

Why Use Stemming?
→ Normalize words with similar meanings
→ Improve efficiency in text classification, sentiment analysis, and
information retrieval
→ Reduces data sparsity in traditional models (e.g., Bag-of-Words,
TF-IDF)


**10. Lemmatization**
→ Lemmatization is the process of reducing a word to its base or
dictionary form, called a lemma, using linguistic knowledge (like
grammar and vocabulary).
→ Unlike stemming, lemmatization returns valid words.
→ Lemmatization helps in reducing the dimensionality.

Why Use Lemmatization?
→ Normalizes words for better text analysis
→ Reduces dimensionality (especially in vectorized models)
→ Improves search, classification, and clustering
→ Preferred over stemming when accuracy matters

![image](https://github.com/user-attachments/assets/82bbabfc-8813-4462-bfe3-9694b1c7072b)

**Text Preprocessing Libraries**

![image](https://github.com/user-attachments/assets/d99e653b-65a5-4142-a63a-807b66f7012e)

## TRANSFORMERS

Transformers are a type of neural network architecture, The key innovation of the transformer architecture is the use of self-attention mechanisms, which allow the model to focus on different parts of the input sequence at different times during processing.
The transformer architecture has been used to develop several state-of-the-art models for NLP tasks, including GPT, BERT, and T5.

**Transformer Architecture:**

![image](https://github.com/user-attachments/assets/5d131396-26c9-4dd6-aa64-5390646fe51d)

The transformer architecture consists of a series of encoder and decoder layers. Each layer has a similar structure, consisting of several sublayers, as shown in the figure above.
The encoder layers are responsible for processing the input sequence and producing a series of hidden representations.
The decoder layers take these hidden representations as input and produce an output sequence.

**Self-Attention Mechanism**
The key innovation of the transformer architecture is the use of self-attention mechanisms. Self-attention allows the model to focus on different parts of the input sequence at different times during processing.
Self-attention works by computing a weighted sum of the input sequence, where the weights are determined by a set of learned parameters. These weights reflect the importance of each element of the input sequence to the current processing step.
In the transformer architecture, self-attention is computed using three matrices: the query matrix, the key matrix, and the value matrix. These matrices are learned during training and are used to compute the weights for each element of the input sequence.

**Multi-Head Attention**
The transformer architecture also uses a technique called multi-head attention to improve the effectiveness of the self-attention mechanism.
Multi-head attention involves computing multiple sets of queries, keys, and values in parallel, and then concatenating the results. This allows the model to attend to different parts of the input sequence in different ways, which can improve its ability to capture complex relationships within the sequence.

**Positional Encoding**
The transformer architecture also includes a technique called positional encoding, which allows the model to incorporate information about the position of each element within the input sequence.
Positional encoding involves adding a set of learned vectors to the input sequence, where each vector corresponds to a specific position within the sequence. This allows the model to differentiate between elements that are in different positions within the sequence.

**GPT**
GPT (Generative Pre-trained Transformer) is a language model that was introduced by OpenAI in 2018. It uses the transformer architecture to generate text, and has achieved state-of-the-art results on several natural language generation tasks.

-> Pre-training
GPT is pre-trained on a large corpus of text data, using a technique called unsupervised pre-training. During pre-training, the model learns to predict the next word in a sentence, given the preceding words. This task is known as masked language modeling.

-> Fine-tuning
After pre-training, the GPT model can be fine-tuned on a specific downstream task, such as language translation or sentiment analysis. Fine-tuning involves updating the learned parameters of the model to optimize its performance on the task at hand.

Here is an example of how to use the GPT-2 model in Python, using the Hugging Face Transformers library:
```
from transformers import pipeline, set_seed

generator = pipeline('text-generation', model='gpt2')

set_seed(42)
generated_text = generator('Hello, how are', max_length=30, num_return_sequences=5)

for i, sample_output in enumerate(generated_text):
    print(f"{i+1}. {sample_output['generated_text']}")
```

This code uses the Hugging Face Transformers library to create a GPT-2 text generation pipeline. It then generates five samples of text starting with the prompt “Hello, how are” and prints the results.

**BERT**
BERT (Bidirectional Encoder Representations from Transformers) is a language model that was introduced by Google in 2018. It uses the transformer architecture to perform a variety of natural language processing tasks, such as question answering and sentiment analysis.

-> Pre-training
BERT is also pre-trained on a large corpus of text data, but it uses a different pre-training task than GPT. Instead of masked language modeling, BERT is pre-trained on a task called next sentence prediction. In this task, the model learns to predict whether two input sentences are consecutive in the original text corpus.

-> Fine-tuning
Like GPT, BERT can also be fine-tuned on specific downstream tasks. However, because BERT is a bidirectional model, it requires a slightly different fine-tuning approach than GPT.

When fine-tuning BERT, the model is typically trained on a labeled dataset for the downstream task, such as a dataset of question-answer pairs for question answering. The input to the model is a concatenation of the question and answer, separated by a special token called [SEP]. The model then produces a prediction for the answer based on the input question.

Here is an example of how to use the BERT model in Python, using the Hugging Face Transformers library:

```
from transformers import pipeline

question_answerer = pipeline('question-answering', model='bert-large-uncased-whole-word-masking-finetuned-squad')

context = "The quick brown fox jumps over the lazy dog. This sentence contains the answer to the question."

question = "What is the answer to the question?"

result = question_answerer(question=question, context=context)

print(f"Question: {question}")
print(f"Answer: {result['answer']}")
```






















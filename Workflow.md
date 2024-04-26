# Defining the libraries to work with
# Getting texts from PDFs
The documents gathered from the Prevention Web database are in PDF format. The texts are extracted by iterating every page of each document. 
However, this format sometimes creates problems in extraction because page formats (e.g. how texts are aligned, are there any pictures, etc.) differ.
# Preprocessing and vectorization
**Preparing text processing pipeline**

The pipeline starts with standardizing and cleaning the extarcted text. Then, tokenization takes place. Stopwords, non-alphabetic tokens, tokens involving digits, and tokens that are only one character are defined and removed after. Finally, lemmatization takes place.

(!) The stopwords may change according to the content and format of texts. Therefore, there is a need for defining custom list of stopwords. However, some of the stopwords still exist in the final result. 

**Iteration function**

Iteration function goes through each document & page and applies the preprocessing pipeline. Then, the preprocessed text is stored in a dictionary named docs. Each document is given a unique name (e.g., doc1, doc2, ...) based on the length of the dictionary. The preprocessed text is stored as a list under the document name. 

**Creating token dictionary**

Each token in the sublist of doc dictionary is iterated and assigned unique IDs. 

**Creating a Bag-of-Words (BoW) representations**

BoW representations are created to represent unique token (word) in the vocabulary, the frequency of occurrence of that token in the document. Thus, inputs for LDA would be defined. 

**Document term matrix**

DTM is created to provide a structured representation of the text data.

**N-grams**

Before going into LDA, n-grams were created to make sense of the collocations, syntactic patterns, and grammatical structures that structure the context.

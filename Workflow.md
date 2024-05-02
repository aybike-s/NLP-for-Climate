**(!) sign indicates current issues**

# Getting texts from PDFs
The documents gathered from the Prevention Web database are in PDF format. The texts are extracted by iterating every page of each document. 
However, this format sometimes creates problems in extraction because page formats (e.g. how texts are aligned, are there any pictures, etc.) differ.
# Preprocessing and vectorization
**Preparing text processing pipeline**

The pipeline starts with standardizing and cleaning the extarcted text. Then, tokenization takes place. Stopwords, non-alphabetic tokens, tokens involving digits, and tokens that are only one character are defined and removed after. Finally, lemmatization takes place.

(!) The stopwords may change according to the content and format of texts. Therefore, there is a need for defining custom list of stopwords. However, some of the stopwords still exist in the final result. 

(!) Some compound words are displayed as two or more seprate words.

(!) Token lists are at different lengths due to non-standardized structure of the dataset. 

**Iteration function**

Iteration function goes through each document & page and applies the preprocessing pipeline. Then, the preprocessed text is stored in a dictionary named docs. Each document is given a unique name (e.g., doc1, doc2, ...) based on the length of the dictionary. The preprocessed text is stored as a list under the document name. 

**Creating token dictionary**

Each token in the sublist of doc dictionary is iterated and assigned unique IDs. 

**Creating a Bag-of-Words (BoW) representations**

BoW representations are created to represent unique token (word) in the vocabulary, the frequency of occurrence of that token in the document. Thus, inputs for LDA would be defined. 

**Document term matrix**

DTM is created to provide a structured representation of the text data.

**N-grams**

Before going into LDA, n-grams were created to make sense of the collocations, syntactic patterns, and grammatical structures that structure the context. An n-gram model involving 3 words was defined to have a better understanding regarding the context that these words establish. 

**LDA model**

An LDA model was established to identify major categories. 

(!) In the n-grams model, it is possible to observe some relationships. For example, according to this result "('escalate', 'bushfire', 'heat') ('bushfire', 'heat', 'drought')" it is possible to observe the relationship between heat, drought, and bushfire which can be categorized under the "environmental impacts of heat waves". However, this relationship does not exist in the LDA model.

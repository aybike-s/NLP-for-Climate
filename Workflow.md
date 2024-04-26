# Defining the libraries to work with
# Getting texts from PDFs
The documents gathered from the Prevention Web database are in PDF format. The texts are extracted by iterating every page of each document. 
However, this format sometimes creates problems in extraction because page formats (e.g. how texts are aligned, are there any pictures, etc.) differ.
# Preprocessing and vectorization
*Preparing text processing pipeline*

The pipeline starts with standardizing and cleaning the extarcted text. Then, tokenization takes place. Stopwords, non-alphabetic tokens, tokens involving digits, and tokens that are only one character are defined and removed after. Finally, lemmatization takes place.

(!) The stopwords may change according to the content and format of texts. Therefore, there is a need for defining custom list of stopwords. However, some of the stopwords still exist in the final result. 

*Iteration function*

Iteration function goes through each document & page and applies the preprocessing pipeline. Then, the preprocessed text is stored in a dictionary named docs. Each document is given a unique name (e.g., doc1, doc2, ...) based on the length of the dictionary. The preprocessed text is stored as a list under the document name. 

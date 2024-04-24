# NLP-for-Climate
This is a project developed for the course "Automated Text Processing for Social Sciences" taught by Ali Hürriyetoğlu

# Problem statement
As the increasing heat patterns in the world become hazard and disaster events, actions or policies are needed to protect lives, livelihoods, and assets. However, heat waves and ways to prevent their socio-economic-ecological-demographic effects are often neglected by the public and policymakers. Therefore, there is a need for more research and “documentation” (ENBEL, 2023), especially regarding the actions to prevent harm and damage. So, the visibility of heat wave mitigation actions, plans, and policies must be enhanced to increase awareness among decision-makers, provide guidance, and propose policy solutions. 

# Research objective
This study will first establish a corpus from the “documents and publications” related to heat wave hazard.  Then, the Latent Dirichlet Allocation (LDA) technique will be utilized on this corpus to identify the impacts of heat waves, actions for mitigation & adaptation including their location, and vulnerable groups. The study will use the coherence score to evaluate the relevance of the topics. 

The main research questions that will guide this objective are:
1. How to establish a corpus using documents aiming to mitigate the impacts of heat waves?
2. How to identify the topics/characteristics from the documents?
3. How can these documents inform the development of comprehensive heat wave mitigation strategies for policymakers?

# Details on the research framework
*Gathering documents & establishing corpus*
The documents for the corpus will be gathered from the Prevention Web database which includes reports, research articles, discussion papers, policy briefs, policy recommendations, guidelines, reviews, technical notes, briefings, etc. published by government agencies, universities, multilateral organizations, NGOs, etc. around the world. The reason behind selecting this database is that it is official by being a product of the United Nations Office for Disaster Risk Reduction (UNDRR) and includes official documents from diverse sources. 

Within the database, documents exist in the “Documents and Publications => Hazard => Heat wave” section. The section involves 584 PDF documents published between 2024-2007. The documents to be included within the corpus may be fewer because some documents are corrupt or lost even though their nametag still exist.

*Preprocessing*
The preprocessing is the most important and time-consuming step. Within this process punctuation, numbers, and stop words will be removed. Incoherent pieces of words specific to the PDF documents within the corpus will also be removed. All letters will be lowercase and stemming will be conducted (Denng, 2018).  

*Training*
Document Term-Matrix will be prepared to provide a structured representation of the text data and observe the frequency count of each term. Since there are more than 100 documents, this can be done in several batches (e.g. each batch consisting of 50 documents). The Gensim library will be used to train the LDA model on the document-term matrix. 

Hyperparameters such as the number of topics, alpha, beta, and iterations will be tuned to experiment with the interpretability of the topics, document-topic density, topic-word density, and model convergence.

Identified impacts from the documents will be assigned to the relevant topics (or categories). Based on the identified impacts and their categories, a list of potential interventions to address these impacts will be identified. Then, interventions will be matched with the corresponding impacts or categories they address. Finally, vulnerable groups will be identified.

*Identifying topics*
The identification of topics and features via LDA will be completed in several steps. Each step will represent the layers of the research. 

The impacts of the heat waves constitute the first layer. The impacts will be collected under the broader categories (or topics) of environment, health, education, etc. This step is important in organizing and summarizing the impacts for a comprehensive view. 

The interventions  will constitute the second layer and be identified and matched with impacts. The location of the interventions will also be identified. Third, the vulnerable groups will constitute the third layer and be identified to understand which groups are more at risk. 

*Evaluation*
The coherence score will be used to evaluate the quality of the topics used to form the layers of this study in several layers:
1. To evaluate the interpretability of the topics to understand how close the words are semantically related and conceptually coherent
2. Measure the quality of the LDA model

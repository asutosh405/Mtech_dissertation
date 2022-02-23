# Extraction and Analysis of Market Events using Data Analysis and Knowledge Graphs
Project Carried out as part of my Dissertation for Mtech programme- 2019-2021

This is the code repository for the project

Companies part of S&P500 Index was chosen for the experiment.

10K filings were extracted from EDGAR database and stored locally in the system.
Time range was chosen as 2016-2021.

Focus area in the Filings is Business Understanding (Item1) and Risk Factors (Item1A) sections only.

Extracts were pulled for around 156 companies for training and another 50 companies for test dataset.

Below are the notebooks listed as per sequence for the complete project.

1. Notebook **read_filing_extracts.ipynb** has the code to read the extracts per line and convert the data into a dataframe along with the file metadata.

2. Notebook **Extract-S&P500_from_Wiki.ipynb** has the code to extract list of companies from S&P500 and corresponding metadata.

3. Notebook **event_word_synonyms.ipynb** had the code for generating similar words or synonyms for the market event terms. This uses a pre-trained embedding GoogleNews-vectors-negative300.bin.gz. Top 20 similar words for each of the events are generated.

4. Notebook **sentence_embedding** has the code to create target labels for the sentences generated as part of the read_filing_extracts.ipynb notebook. This leverages sentence transformers to create sentence embedders from the filing sentence corpus. The similar words are then looked up in the sentences by using cosine similarity. Dataframe outputs with target labels are generated for each of the marketq events.

5. Notebook **Exploratory_analysis_and_ML_model_v2.ipynb** has the code to explore the datasets generated from thr previous steps. Duplicate sentences are dropped from each of the datasets of market events. Duplicate sentences are also dropped from the concatenated dataset of all the 3 market events. Data analysis is done to explore the distribution of data across sectors and companies. Dataset is imbalances across labels for the 3 market events. 
 4 types of ML models are tried out and the evaluation metrics are captured. logistic Regression, SVC, Random Forest, MultinomialNB.
 
 6. Notebook **model_building_bert_v2.ipynb** has the code for the deep learning classifier model. Albert model from the bert family of models is tried and model evaluation results are captured.

7. Notebook **model_building_bert_distilbert_v2.ipynb** has the code the deep learning classifier model, Distilbert model from the bert family of models and model evaluation metrics are captured.


The test dataset with pedicted labels are then loaded into neo4j graph database to explore the relations between companies, events and the year of occurance. This gives us a very good interactive interface to visual interact with the data.


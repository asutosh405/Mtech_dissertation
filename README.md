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

3. Notebook **sentence_embedding**


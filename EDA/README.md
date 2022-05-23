# EDA

In this section, we perform Exploratory Data Analysis on our dataset.

EDA process includes: 

ingesting data

preprocessing and cleaning data to prepare for further analysis

Data Visualization

Progress report:
Successfully ingested data from 'metadata.csv' into pandas dataframe. 
No of records: 316061

'pdf_json_files' contains full text articles. This full text will be used in future to train our models and for topic modelling.
We use fields from 'metadata.csv' file to further ingest data from 'pdf_json_files'. Since the size of files was huge, for now we include 1000 articles in our dataframe.
Example of an article with length = 32585
![image](https://user-images.githubusercontent.com/95871147/154870395-99e8203d-fc7a-441a-95b5-0dfa02908e2d.png)

## Results
TOP 20 WORDS


![Top20words_Spacy_final](https://user-images.githubusercontent.com/95871147/169723654-6b7a9a8c-f016-4a29-9a13-75c902f70821.png)

IMPORTANCE OF TOPIC KEYWORDS


![spacy_topicwise_importance](https://user-images.githubusercontent.com/95871147/169723708-4a16d45f-907d-4793-bb88-f827b193698b.png)


LDA

![SPACY_LDA](https://user-images.githubusercontent.com/95871147/169723722-c08a3d42-311e-4662-a91f-b21036cb9ad1.png)





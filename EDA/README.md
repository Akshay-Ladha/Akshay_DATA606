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
![image](https://user-images.githubusercontent.com/95871147/169723616-28d84a3d-4742-4952-8d0f-e78e4ca39a03.png)



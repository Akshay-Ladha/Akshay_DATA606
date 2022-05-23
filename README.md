# Summarizing Covid-19 research articles
## Issue of Interest
Since COVID-19 started to spread in March 2020, it has become an unavoidable topic. The pandemic has changed the way of the world. There are lot of grey areas that needs to be touched upon to understand the impact of pandemic. Previously I have done projects related to Covid-19 tweets sentiment analysis and finding a correlation between Covid-19 and Baltimore crime data. I wish to continue working on a project that is related to the pandemic and dig deeper into the topic of pandemic and the impact it has on the world.
## Why is this issue important?
There have been different phases of the covid-19 pandemic such as rise of delta variant, vaccine booster, emergence of Omicron variant etc. Each phase had different impact on people. As such, the sentiment of people towards pandemic keeps changing. Since the beginning of pandemic lot of research articles have been published and it is hard for people for common people to stay up to date with the latest development in Covid-19 pandemic. Reading so many long articles is time consuming and not practical. Through this project I hope to provide a tool that will summarize the articles in minimal words and analyze the sentiments in the articles and help common people to stay up to date with development of the pandemic. 
## Dataset
Dataset has been obtained from 
https://ai2-semanticscholar-cord-19.s3-us-west-2.amazonaws.com/historical_releases.html

CORD-19 is a corpus of academic papers about COVID-19 and related coronavirus research. It's curated and maintained by the Semantic Scholar team at the Allen Institute for AI to support text mining and NLP research.

CORD-19 is released weekly. Each version of the corpus is tagged with a date stamp (e.g., 2020-02-07). Releases looks like:
![image](https://user-images.githubusercontent.com/95871147/153780062-40e8a9e4-e564-4055-94aa-4e492366a762.png)


 
First release: 020-03-13

Latest release: 2022-02-07

Size of the dataset: 15 GB

The files in each version are:

•	changelog: A text file summarizing changes between this and the previous version.

•	cord_19_embeddings.tar.gz: A collection of precomputed SPECTER document embeddings for each CORD-19 paper

•	document_parses.tar.gz: A collection of JSON files that contain full text parses of a subset of CORD-19 papers

•	metadata.csv: Metadata for all CORD-19 papers.

When document_parses.tar.gz is decompressed, it has two folders containing articles in JSON format. 

Metadata.csv file has the following columns:

•	cord_uid: A str-valued field that assigns a unique identifier to each CORD-19 paper.

•	sha: A List[str]-valued field that is the SHA1 of all PDFs associated with the CORD-19 paper. Most papers will have either zero or one value here (since we either have a PDF or we don't), but some papers will have multiple. 

•	source_x: A List[str]-valued field that is the names of sources from which we received this paper. Also semicolon-separated. 

•	title: A str-valued field for the paper title.

•	doi: A str-valued field for the paper DOI.

•	pmcid: A str-valued field for the paper's ID on PubMed Central. Should begin with PMC followed by an integer.

•	pubmed_id: An int-valued field for the paper's ID on PubMed.

•	license: A str-valued field with the most permissive license we've found associated with this paper. Possible values include: 'cc0', 'hybrid-oa', 'els-covid', 'no-cc', 'cc-by-nc-sa', 'cc-by', 'gold-oa', 'biorxiv', 'green-oa', 'bronze-oa', 'cc-by-nc', 'medrxiv', 'cc-by-nd', 'arxiv', 'unk', 'cc-by-sa', 'cc-by-nc-nd'.

•	abstract: A str-valued field for the paper's abstract.

•	publish_time: A str-valued field for the published date of the paper. This is in yyyy-mm-dd format. 

•	authors: A List[str]-valued field for the authors of the paper. Each author name is in Last, First Middle format and semicolon separated.

•	journal: A str-valued field for the paper journal. Strings are not normalized (e.g. BMJ and British Medical Journal can both exist). Empty string if unknown.

•	mag_id: Deprecated, but originally an int-valued field for the paper as represented in the Microsoft Academic Graph.

•	who_covidence_id: A str-valued field for the ID assigned by the WHO for this paper. Format looks like #72306.

•	arxiv_id: A str-valued field for the arXiv ID of this paper.

•	pdf_json_files: A List[str]-valued field containing paths from the root of the current data dump version to the parses of the paper PDFs into JSON format. Multiple paths are semicolon-separated. Example: document_parses/pdf_json/4eb6e165ee705e2ae2a24ed2d4e67da42831ff4a.json; document_parses/pdf_json/d4f0247db5e916c20eae3f6d772e8572eb828236.json

•	pmc_json_files: A List[str]-valued field. Same as above but corresponding to the full text XML files downloaded from PMC, parsed into the same JSON format as above.

•	url: A List[str]-valued field containing all URLs associated with this paper. Semicolon-separated.

•	s2_id: A str-valued field containing the Semantic Scholar ID for this paper. Can be used with the Semantic Scholar API 

## Unit of Analysis
Unit of Analysis here are the articles. No of observations are no articles which are around 338,451.

## EDA Results

You can find EDA results on the following link

https://github.com/Akshay-Ladha/Akshay_DATA606/blob/main/EDA/README.md


## Models
I will be using NLP to preprocess the data and create corpus of articles.

Latent Dirichlet Allocation (LDA) will be used for topic modelling as a part of Exploratory Data analysis (EDA). By using LDA for topic modelling I will be able to learn more about the topic to which article is more related to. For example, if the article is related more to politics, economy etc. One of the advantages of using LDA as compared to other models is that one does not need to specify topics in advance, topics will be inferred without prior input. Finally, pyLDAvis will be used to visualize the LDA results. pyLDAvis is a python library for interactive topic model visualization.


Deep learning techniques will be used to train models. I am considering T5, BERT and GPT-2 models for training purpose using training dataset for summarization. Depending on the trials and results, one of the above three models will be finalized. To evaluate the performance of the models I will be using Recall-Oriented Understudy for Gisting Evaluation (ROUGE). ROUGE is used measure the accuracy of language-based sequence when dealing with language summarization. 

For sentiment analysis, I will make use of NLTK library and use VADER for sentiment analysis. 

As an ambitious goal I intend to use Streamlit to provide a UI for the project.
## Intended Outcome
Users will be able to get summarization of any given covid-19 related article and the analysis of the sentiment of that article. 
## References
1) https://github.com/allenai/cord19
2) https://ai2-semanticscholar-cord-19.s3-us-west-2.amazonaws.com/historical_releases.html
3) http://cs230.stanford.edu/projects_spring_2020/reports/38954132.pdf

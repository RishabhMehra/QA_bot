# QA_bot
A Question Answer Bot over PDF Medical data


Approach : 

# 1. Fine Tune QA Model
    a. Generated Data from PDF on by annotating in the manner of Question, Context, Answer.
    b. Feed Data for Fine Tuning Model.
    c. Model Used : 
          i. deepset/roberta-base-squad2
          ii. distilbert-base-cased-distilled-squad
	
Model unable to give generalized outcomes, needed context vector, added Document retrieval approach.

![Retrival_Flow](https://github.com/RishabhMehra/QA_bot/blob/main/Information_retrival.jpeg?raw=true)

# 2. Information Retrieval Pipeline 
    a. Split PDF Document into smaller chunks
    b. Generate Embedding vectors of the documents.
    c. Store the Embeddings
    d. Generate Embeddings of Query
    e. Compare query with Vector DB for a most similar chunk
    f. Use Text Generation over Model to form an answer for the query.
    g. Model Used(QA)
        i. Roberta-base-squad2
        ii. Roberta-base-squad2-covid
    h. Text Generative
        i. GPT2
        ii. tiiuae/falcon-7b-instruct
        iii. databricks/dolly-v2-12b


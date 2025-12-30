# **APPLICATION OF TEXT MINING AND CLASSIFICATION MODELS TO EXTRACT MEANINGFUL INFORMATION FROM CUSTOMER REVIEWS**

## **Abstract**
In today's society, e-commerce has led the way in the purchase and sale of goods. The reputation of e-commerce platforms depends on the ratings and reviews given by customers. Understanding the meaning behind texts through text mining techniques such as topic modelling can be used to only automatically extract information and themes from textual data but also create labelled dataset for the application of supervised algorithms to accurately train models for sentiment analysis purposes. This paper leverages LDA, a text mining technique within topic modelling to turn an unsupervised problem by labelling the sourced Amazon reviews based on the best topic coherence score, into a supervised problem for sentiment analysis. By using TF-IDF with SVM, MLP and Logistic Regression, all models performed well, with scores of AUC/Accuracy being 0.91/0.78, 0.93/0.71 & 0.91/0.76 respectively. Moreover, by using glove-wiki-gigaword-300 word embeddings with same models, MLP outperformed BiLSTM and transfer learning approach with DistilBERT, having AUC/Accuracy scores of 0.97/0.89, whereas BiLSTM and DistilBERT with Data Normalisation approach had AUC/Accuracy scores of 0.97/0.88 and 0.94/0.80 respectively. Moreover, by using DistilBERT embeddings with SVM, LR & MLP, there are also significant boost in performance when compared to the use of TF-IDF.
This thesis has 44 figures, 22 tables, 25 references.
Keywords - NLP, Text Mining, Topic Modelling, Sentiment Analysis, Transfer Learning, Customer Reviews, E-Commerce. 

## **How the Project is Structured**
The contents of the artefacts are in two phases; **Experimentation & Modelling**, and **Model Deployment**.
The following are regarding Experimentation & Modelling;

### **DATA**
This contained the following;
- **final_filtered_annotated_reviews:** Filtered topic annotated data in which bad_reviews were removed
- **topic_data:** The fully annotated topics of the corpus

### **TOPIC_MODEL**
This contains the LDA model which contains the following
- **lda_model_bigrams_umass:** The LDA code
- **saved_models:**  The LDA saved model
- **results:** Results of the model
### **SUPERVISED_MODELS**
This contains the analytics done on the filtered final_filtered_annotated_reviews.csv file before running the supervised models. 
Model Metrics are saved in the model_metrics folder as an excel file.

For TF-IDF text representation refer to the following folders;
- mlp
- svm
- glm_logistic
For word embeddings refer to the following folders;
- svm_word_embeddings
- mlp_word_embeddings
- logistic-word-embeddings
  
For use of DistilBERT embeddings with ML models refer to the following
- svm_distil_bert_embeddings
- mlp_distil_bert_embeddings
- logistic_distil_bert_embeddings
  
For the use of DistilBERT transfer learning refer to the following;
- distilbert_uncased
- cleaned_data_distilbert_base_uncased (DistilBERT with data normalisation)
### **MODEL DEPLOYMENT**
Please refer to the following [link](https://github.com/daniau23/dbs_final_year_project_deployment)

## **Summary of Results**
### **AUC**
|Rank | Model| AUC|
|--|--|--|
|1|MLP with Glove-Wiki-Gigaword-300 Embedding|0.97
|1|SVM with Glove-Wiki-Gigaword-300 Embedding|0.97
|1|LR with Glove-Wiki-Gigaword-300 Embedding|0.97
|1|BiLSTM with Glove-Wiki-Gigaword-300 Embedding|0.97
|2|LR with DistilBERT Embedding|0.96
|2|MLP with DistilBERT Embedding|0.96
|3|SVM with DistilBERT Embedding|0.95
|3|		DistilBERT with Data Normalisation |0.95
|4|DistilBERT without Data Normalisation |0.94
|5|MLP with TF-IDF|0.93
|6|SVM with TF-IDF|0.91
|7|LR with TF-IDF|0.91
|8|LSTM with Glove-Wiki-Gigaword-300 Embedding|0.5

### **Accuracy**
|Rank | Model| Accuracy|
|--|--|--|
|1|MLP with Glove-Wiki-Gigaword-300 Embedding|0.89
|2|SVM with Glove-Wiki-Gigaword-300 Embedding|0.88
|2|BiLSTM with Glove-Wiki-Gigaword-300 Embedding|0.88
|3|LR with Glove-Wiki-Gigaword-300 Embedding|0.87
|3|MLP with DistilBERT Embedding|0.87
|4|LR with DistilBERT Embedding|0.85
|4|SVM with DistilBERT Embedding|0.85
|5|DistilBERT with Data Normalisation|0.83
|6|DistilBERT without Data Normalisation|0.80
|7|SVM with TF-IDF|0.78
|8|LR with TF-IDF|0.76
|9|MLP with TF-IDF|0.71
|10|LSTM with Glove-Wiki-Gigaword-300 Embedding|0.40

### **F1-Score (Macro)**
|Rank | Model| F1-Score (Macro)|
|--|--|--|
|1|LR with TF-IDF|0.96
|2|MLP with Glove-Wiki-Gigaword-300 Embedding|0.89
|3|SVM with Glove-Wiki-Gigaword-300 Embedding|0.88
|3|BiLSTM with Glove-Wiki-Gigaword-300 Embedding|0.88
|4|LR with Glove-Wiki-Gigaword-300 Embedding|0.87
|5|MLP with DistilBERT Embedding|0.86
|6|SVM with DistilBERT Embedding|0.84
|6|LR with DistilBERT Embedding|0.84
|7|DistilBERT with Data Normalisation|0.82
|8|DistilBERT without Data Normalisation|0.77
|8|SVM with TF-IDF|0.77
|9|MLP with TF-IDF|0.71
|10|LSTM with Glove-Wiki-Gigaword-300 Embedding|0.19

### **Training Runtime (s)**
|Rank | Model| Training Runtime (s)|
|--|--|--|
|1|LR with Glove-Wiki-Gigaword-300 Embedding|2
|2|SVM with Glove-Wiki-Gigaword-300 Embedding|5
|3|LR with TF-IDF|9
|4|LR with DistilBERT Embedding|14
|5|SVM with DistilBERT Embedding|16
|6|SVM with TF-IDF|19
|7|MLP with Glove-Wiki-Gigaword-300 Embedding|22
|8|MLP with DistilBERT Embedding|59
|9|DistilBERT with Data Normalisation|133
|10|LSTM with Glove-Wiki-Gigaword-300 Embedding|278
|11|BiLSTM with Glove-Wiki-Gigaword-300 Embedding|642
|12|MLP with TF-IDF|1854
|13|DistilBERT without Data Normalisation|2719

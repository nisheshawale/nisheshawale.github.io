---
layout: page
title: Plagiarism Detection
description: Plagiarism detection in electronic texts as well as programming assignments.
img: assets/img/plagiarism_detection.png
importance: 1
category: Academic
---

This was my major project during my undergraduate degree. It was performed under the supervision of [Professor Shashidhar Ram Joshi](https://scholar.google.com/citations?user=S1dL69sAAAAJ&hl=en). It has two parts.

1. **Plagiarism detection in programming assignments**

    Plagiarism detection system for assignments in C and C++ was developed. First, the assignments were tokenized and preprocessed to compute the relevant features. Then, the xgboost model was trained to classify whether the pair of assignments were plagiarised or not. The dataset of assignment pair was created from the collection of assignment found [online](https://ieee-dataport.org/open-access/programming-homework-dataset-plagiarism-detection). Different machine learning models were tested and xgboost model performed best in our case. This project was also published in the journal and the link is given below.

    Paper: [Plagiarism Detection in Programming Assignments using Machine Learning](https://www.irojournals.com/aicn/V2/I3/05.pdf)

2. **Plagiarism detection in electronic text assignments**

    To find the relevant documents from a collection of documents to a particular assignment, BM25 algorithm was used. For example, BM25 algorithm helped to find 10 relevant documents from a collection of 100 documents to a particular query document. After finding the relevant document, text similarity was computed on more granular level. For this, the texts in the document were broken down into sentences and sentence BERT was used to compute its embeddings. Then, the BERT embeddings of the sentences of two documents were used to compute the similarity value. For faster similarity search, FAISS index was used. After finding the related texts in the two documents, post processing was done to merged the adjacent sentences in the document.

This paper was also presented on the 6<sup>th</sup> Intenational Workshop on Effective Engineering Education at National Institute of Technology in Japan.

Slides: [6<sup>th</sup> IWEEE](/assets/pdf/major_project_slides.pdf)  
Github repo: [plagiarism-detection-in-assignments](https://github.com/nisheshawale/plagiarism-detection-in-assignments)

**Technologies used:** Scikit-learn, Xgboost, BERT, FAISS, React, Firebase, NodeJS, Heroku and AWS

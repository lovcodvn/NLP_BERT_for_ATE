# NLP: Aspect Term Extraction (ATE)

## Project Description
This project aims to solve the Subtask 1 of SemEval 2014 Task 4 - Aspect Based Sentiment Analysis

Sentiment analysis is increasingly viewed as a vital task both from an academic and a commercial standpoint. The majority of existing evaluations in Sentiment Analysis (SA) are aimed at evaluating the overall polarity of a sentence, paragraph, or text span. In contrast, this task will provide evaluation for detecting aspects and the sentiment expressed towards each aspect.

Subtask 1: Aspect term extraction
Given a set of sentences with pre-identified entities (e.g., restaurants), identify the aspect terms present in the sentences.

An aspect term names a particular aspect of the target entity (e.g., "I liked the service and the staff, but not the food”, “The food was nothing much, but I loved the staff”).

## Methodology 

To solve the Aspect Term Extraction (ATE) task, in this project, we'll explore 3 approaches:

- The first approach is simply dictionary-based. In this approach, we will use the aspect term in our training dataset to create a dictionary of aspect terms. Then, we'll use that dictionary to look up the terms in the valid dataset
- The second approach is using Word2Vec with a convolutional model. Let's see if word representation can do a better job. The word reprentation we'll use is from "Glove.6B.300d.txt".
- The third approach is based on pretrained models, which have achieved SOTA performance on many NLP tasks. The pretrain model we'll mainly explore is BERT.

## Data
The dataset I used in this task is SemEval 2014. For some reason, the original test dataset I found doesn't contain labels. Thus, I used the original training data and split it into two, one for training and the other for validing. I used the validing dataset to measure my models' performances.

## Model result:
- Approach 1: Recall: 46.15%,  Precision: 49.07%,  F1 Score: 47.57% 

This result surprised me since I had expected the F1-Score is around only 20%. Since this approach is dictionary-based, the performance is entirely dependent on the comprehensiveness of our dictionary. As the dictionary is created based on the training data, we couldn't expect the dictionary can be representative of our data. Nevetheless, the dictionary-based result is even higher than that in my second approach. 
- Approach 2: Recall: 36.25%,  Preision: 40.15%,  F1 Score: 38.1% 

- Approach 3: Recall: 84%,  Precision: 85%, F1 Score: 84%. Sigificantly better result compared to those of the first two. This is achieved by using pretrained model BERT. 


# References
- SemEval 2014 Task 4 - Aspect Based Sentiment Analysis: https://www.aclweb.org/portal/content/semeval-2014-task-4-aspect-based-sentiment-analysis
- Group 1's Project, Natural Language Processing, Class of Apr 2022, Singapore Management University
- Qi, P., Dozat, T., Zhang, Y., & Manning, C. D. (2019). Universal dependency parsing from scratch. arXiv preprintarXiv:1901.10457.
- Zhuang, L., Jing, F., & Zhu, X. Y.(2006, November). Movie review mining and summarization. In Proceedings of the 15thACM international conference on Information and knowledge management (pp. 43-50).
- Qiu, G., Liu, B., Bu, J., & Chen, C.(2011). Opinion word expansion and target extraction through double propagation. Computational linguistics, 37(1), 9-27.
- Smeaton, A. F., Kelledy, F., &O'Donnell, R. (1995). TREC-4 experiments at Dublin City University: Thresholding posting lists, query expansion with WordNet and POS tagging of Spanish. Harman [6], 373-389.
- Popescu, A. M., & Etzioni, O.(2007). Extracting product features and opinions from reviews. In Natural language processing and text mining (pp. 9-28).Springer, London.
- Shu, L., Liu, B., Xu, H., & Kim, A.(2016). Supervised Opinion Aspect Extraction by Exploiting Past Extraction Results. arXivpreprint arXiv:1612.07940.


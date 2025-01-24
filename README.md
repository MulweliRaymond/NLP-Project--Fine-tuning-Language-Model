# From Baseline to Fine-Tuned: Improving Sentiment Classification in Swahili with AfriBERTa
This repository contains the implementation and findings from the study "From Baseline to Fine-Tuned: Improving Sentiment Classification in Swahili with AfriBERTa." The project investigates the use of the AfriBERTa pre-trained model for Swahili sentiment classification, comparing baseline performance with a fine-tuned version on Swahili datasets.

## Introduction
Transformer-based models like AfriBERTa have revolutionized natural language processing (NLP), offering significant advancements in sentiment analysis, translation, and more. However, African languages like Swahili remain underrepresented in NLP. This project focuses on fine-tuning AfriBERTa for Swahili sentiment classification tasks to address this gap.

## Objectives
* Assess the performance of AfriBERTa on a Swahili sentiment classification task in its baseline (pre-trained) form.
* Fine-tune AfriBERTa on a Swahili corpus and evaluate its performance.
* Explore attention maps to understand how the model processes Swahili text.

## Datasets
Swahili General Dataset for Fine-Tuning:

* Source: Leipzig Corpora Collection.
* Content: ~100,000 text samples from Swahili Wikipedia, filtered to 5,244 sentences with >200 words.
* Swahili Tweets Dataset for Sentiment Classification:

* Source: Hugging Face Dataset.
* Content: 2,263 labeled tweets with sentiments classified as:
Negative: 10.6%
Neutral: 59.2%
Positive: 30.2%
Binary classification task: Positive vs. Negative.

## Methodology
### Preprocessing:

* Removed non-alphabetic characters, URLs, and excess whitespace.
* Lowercased text for consistency.
* Tokenized using the AfriBERTa tokenizer, optimized for African languages.
### Model Selection:
AfriBERTa_small: A smaller variant of AfriBERTa optimized for resource-constrained setups, pre-trained on 11 African languages, including Swahili.
Fine-Tuning:

* Task: Masked Language Modeling (MLM) on the general Swahili dataset.
* Hyperparameters:
* Learning rate: 0.00003
* Batch size: 8
* Epochs: 10
* Optimizer: AdamW
* Masking probability: 0.15
### Classification Task:

* Task: Binary sentiment classification on Swahili tweets.
* Data split: Training (60%), Validation (20%), Testing (20%).

### Hyperparameters:
* Learning rate: 0.00001
* Batch size: 16
* Epochs: 5
* Optimizer: AdamW
### Evaluation Metrics:

* Accuracy
* Precision
* Recall
* F1 Score

## Results
### Masked Language Model (MLM):
Training and validation loss decreased consistently, showing effective learning without overfitting.
Classification Task:

### Baseline Model:
* Accuracy: 83%
* F1 Score: 0.89
### Fine-Tuned Model:
* Accuracy: 87%
* F1 Score: 0.92
Fine-tuning improved recall, highlighting better generalization and sensitivity.
### Attention Maps:

Both baseline and fine-tuned models exhibited similar attention patterns, focusing on token dependencies.

## Conclusion
Fine-tuning AfriBERTa on a Swahili-specific corpus enhances its performance in sentiment classification tasks, particularly in handling nuanced linguistic features. While the improvement over the baseline was modest, the study demonstrates the value of language-specific adaptation in underrepresented languages.

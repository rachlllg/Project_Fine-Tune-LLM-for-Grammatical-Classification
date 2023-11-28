# Project_Fine-Tune-LLM-for-Grammatical-Classification

Refer to the project page on my website for detailed discussion on the project, including steps performed to process and clean the dataset and model reults evaluation.

Project page: https://rachlllg.github.io/project/2023-Fine_Tune_LLM_for_Grammatical_Classification/

## Background:
This is one part of the final project for the Natural Language Processing class in my Masters in Data Science program. The original project involved three team members including myself, for the showcase here, I have only presented the work I have done, unless noted otherwise.

In the overall final project, the fine-tuned Grammatical Acceptability Classifier (GAC) model is used in the downstream task to score the input sentences. This project page only focuses on the GAC model, a separate project page is dedicated to the remainder of the overall final project.

All work was done in Google Colab, with Python as the programming language. Due to the volume of weights in the RoBERTa model, a T4 GPU (that came with the free version of Google Colab) was used during fine-tuning. Notable Python packages used:
- standard: numpy, pandas
- modeling: tensorflow, transformers
- visualization: matplotlib, seaborn

## Dataset:
The dataset obtained from the CoLA website. The in_domain train contains 8551 instances of grammatical and ungrammatical sentence, while the in_domain dev contains 527 and the out_domain dev conatains 516 instances respectively. The dataset comes in raw text form as well as tokenized form (tokenized from the NLTK tokenizer), to ensure maximum compatability with the RoBERTa model, we used the raw text and tokenized using RobertaTokenizer instead of directly using the tokenized dataset out of the box.

Source: <https://nyu-mll.github.io/CoLA/>

## Model:
To create comparative results as the original RoBERTa paper, the same training and validation sets were used during training. Listed below are the experiments conducted.
- CLS token vs pooling of Last_Hidden_State
- Number of layers to unfreeze
- Size of classification layer
- RoBERTa-Large vs RoBERTa-base
- Grammatical threshold

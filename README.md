Status:
=======

- Error analysis completed for multiway attention model and RoBERTa (base) model ([link](https://drive.google.com/open?id=1w4ERfxi4kN9f_DqFKnrp77pqYgjc6rIS))

- Please check out [AdityaGovardhan/transformer](https://github.com/AdityaGovardhan/transformers) GitHub repository for modifications related to RoBERTa.

- random baseline model provided by [Allen AI](https://leaderboard.allenai.org/cosmosqa/submissions/public) is setup, ran and tested ([Google Colab link](https://colab.research.google.com/drive/12ufgKApJTgajMzcasmyYMRwxWrCe-ws5))

- [Lifu Huang et al.](https://wilburone.github.io/cosmos/)'s multiway attention model is setup, ran and tested ([Google Colab link](https://colab.research.google.com/drive/1_FDdq9upg6n3voJoIrG7NhjsYYid8yyH))

- [RoBERTa baseline model](https://huggingface.co/transformers/model_doc/roberta.html) setup, ran and tested ([Google Colab link](https://colab.research.google.com/drive/1TL8QsMCY2zog_KYjiVbyi3WN5l_r-uAA))

- RoBERTa (large) and BERT (large) models explored, efforts discarded due to memory issues

- Grid search performed on RoBERTa (base) model to obtain optimal baseline parameters, accuracy improved from 65.92% to 68.87%, [this Google Sheets doc](https://docs.google.com/spreadsheets/d/1bdNsVs3AJ3kZa8Dq0DejZ7PLRKJ7zqhmEhOXEZ7eFhA/edit?usp=sharing) has the results of grid search

- SocialIQA approach TODO

- Semi-supervised approach TODO

- Knowledge graph approach TODO

- Summarization approach TODO

___

Individual Efforts:
-------------------

- Kunal :
1. Trying to run cosmosqa_wilburOne on asu agave. Current status is that the cluster is not picking up my job.
2. Attempting to run the Roberta model on CoLAB.
3. Setting up a framework for performing error analysis on the test and validation datasets.
4. Phase 1 report.
5. Performed Error Analysis on 15 samples from 1000-1500 in the Validation set data
6. Finetuning roberta-base model on SocialIQA dataset for incorporating social knowledge.
7. Increased performance by finetuning on SocialIQA dataset on roberta-base from 65.92% to 67.75%. Let's call this model roberta_social_iqa.
8. Finetuned and generated a performance of 66.2 roberta_social_iqa on the COSMOS_QA to boost performance. [Google Colab](https://colab.research.google.com/drive/1QMJVB5Pf24d3x8A5OAuB4Xo7UVN3ngk-?authuser=2)

- Jay : 
1. Was able to run the cosmosqa_wilburOne on my local CPU machine (without GPUs), but since the training + evaluation with huge datasize shall take time, trying to host the process on either Google Colab/Cloud Shell - but facing issues with installing Nvidia/Apex and few other version conflicts.
2. Also, trying to read the [https://arxiv.org/pdf/1904.01172.pdf] paper in order to come up with model tweaks for error analysis.
3. Now running the cosmosqa_wilburOne process on my [Google Colab](https://colab.research.google.com/drive/1JKLkB238zHKXNNdGA9H2kCXhAVTXCrjb#scrollTo=Cvv7loTb2SC0) account with varying values of batch-sizes, epochs and train_examples (training data)
4. The updatesd results with different parameters are being stored in the results/ folder and to be later used for error analysis purposes.
5. Recorded a maximum accuracy of 60.77 using this model, with set hyper-parameters (train_examples=5000, epochs=2, lr=3e-5, batchsize=12)
6. Did and Error analysis for 15 samples out of the results/b12l3e-5ep2.txt for the multi-way attention model, and the inferences on produced errors are visible here as different [sheets](https://docs.google.com/spreadsheets/u/1/d/1a_8sPE_fVxywv4R6Ao9ueT2aHLBynscceYnhePdmHEc/edit#gid=62726107)
7. Preliminary results and conclusions are well documented in /COSMOS_QA__Phase_1_Report_CSE_576.pdf
8. Currently working on implementing the semi-supervised approach for multiple choice question answering task as defined here in the paper - [Improving Language Understanding
by Generative Pre-Training](https://cdn.openai.com/research-covers/language-unsupervised/language_understanding_paper.pdf) by OpenAI on the [official CosmosQA dataset](https://github.com/wilburOne/cosmosqa/tree/master/data/)
9. The script to run the code, results and model details for this approach are stored in the folder Semi-Supervised Approach.

- Aditya :
1. Random baseline model provided by Allen AI setup, ran and tested on [Google Colab](https://colab.research.google.com/drive/12ufgKApJTgajMzcasmyYMRwxWrCe-ws5)
2. Tried running cosmosqa_wilburOne on Windows + GPU setup, but couldn't proceed further since 'apex' library by NVIDIA has limited support for CUDA in Windows.
3. Tried running cosmosqa_wilburOne on Windows Subsystem for Linux (WSL), couldn't proceed further since WSL doesn't have GPU access
4. Multiway Attention model ran successfully on [Google Colab](https://colab.research.google.com/drive/1_FDdq9upg6n3voJoIrG7NhjsYYid8yyH), debugged issues along with Jay and Kunal
5. RoBERTa baseline model ran successfully on [Google Colab](https://colab.research.google.com/drive/1TL8QsMCY2zog_KYjiVbyi3WN5l_r-uAA), debugged issues along with Vasishta and Suryanshu
6. Error Analysis for multiway attention model
7. Phase 1 Report
8. Performed Grid Search on roberta baseline model to improve model accuracy from 65.92% to 68.87%
9. Modified trasformers code to disable checkpoint saving and ran RoBERTa-large successfully

- Vasishta : 
1. Evaluating the use of Amazon Web Service GPU instances K80 P2.xlarge to run cosmosqa_wilburOne for the project along
2. Setup and running roBERTa on Google Colab.
3. Debugged roBERTa backward compatibilty issue - "KeyError: 'token_type_ids'".
4. Tried older roBERTa model to bypass the token type embedding layer issue.
5. Phase 1 Report.
6. Performed Error Analysis on 19 samples from 2000-2500 in the Validation set data
7. Co-ordinated in roberta-base grid search to improve accuracy by about 3%
8. Established Kaggle platform python notebook to mitigate Google Colab issues like idle timeout and 12 hour limit
9. Explored use of bert-large to improve accuracy

- Suryanshu :
1. Went through the CosmosQA paper and forum "http://jalammar.github.io/illustrated-bert/" to get some idea about normal BERT working. Also going trying to go through GPT2 paper as it has been used to improve the performance of cosmosQA.
2. Initially, was trying to run the project(cosmosqa_wilburOne) on my windows system but didnt succeed due to failure in installing apex module correctly.
3. Installed Ubuntu as dual boot. Tried running cosmosqa_wilburOne. Had issues with cuda installation initially but later, could install apex, cuda and was able to acees GPU computes on my system. Currently, having issues with GPU memory consumption by cuda. 
4. Able to run pre trained RoBERTa base and large model on [Google colab](https://colab.research.google.com/drive/1CpaWpCoeEzmKle0XHsVnVLy5iDlG9Y9D) but on commonsense dataset. Still trying to modify it to make it evaluate against Cosmos QA dataset, which hpefully would result in better prediction.
5. Modified RoBERTa baseline model to output evaluation result with all details such as predicted and expected labels.
6. Error analysis for both Cosmos QA baseline mode as well RoBERTa baseline model.
7. Phase 1 report.

___

Running cosmosqa_baseline:
--------------------------
- This random baseline model is provided by [Allen AI](https://leaderboard.allenai.org/cosmosqa/submissions/public) for demonstrating input and output of data
- [Google Colab link](https://colab.research.google.com/drive/12ufgKApJTgajMzcasmyYMRwxWrCe-ws5)

___

Running cosmosqa_wilburOne:
---------------------------
- This multiway attention model is provided by [Lifu Huang et al.](https://wilburone.github.io/cosmos/)
- [Google Colab link](https://colab.research.google.com/drive/1_FDdq9upg6n3voJoIrG7NhjsYYid8yyH)

___

Running RoBERTa base:
---------------------
- This RoBERTa base model is provided by [huggingface](https://huggingface.co/transformers/model_doc/roberta.html)
- [Google Colab link](https://colab.research.google.com/drive/1TL8QsMCY2zog_KYjiVbyi3WN5l_r-uAA)

___

Grid Search:
------------

Results:

| Model | Gradient Accumulation Step | Number of Epochs | Learning Rate | Maximum Sequence Length | Batch Size | Accuracy |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| roberta-base | 1 | 3 | 5 e-5 | 64  | 64 | 64.95% |
| roberta-base | 2 | 3 | 5 e-5 | 64  | 64 | 64.05% |
| roberta-base | 1 | 3 | 5 e-5 | 128 | 16 | 60.26% |
| roberta-base | 2 | 3 | 5 e-5 | 128 | 16 | 66.36% |
| roberta-base | 3 | 3 | 5 e-5 | 128 | 16 | 67.63% |
| roberta-base | 4 | 3 | 5 e-5 | 128 | 16 | 65.72% |
| roberta-base | 5 | 3 | 5 e-5 | 128 | 16 | 63.98% |
| roberta-base | 3 | 4 | 5 e-5 | 128 | 16 | 68.24% |
| roberta-base | 3 | 5 | 5 e-5 | 128 | 16 | 67.70% |
| roberta-base | 3 | 3 | 5 e-5 | 192 | 16 | 67.20% |
| roberta-base | 4 | 3 | 5 e-5 | 192 | 16 | 65.69% |
| roberta-base | 3 | 4 | 5 e-5 | 192 | 16 | 68.67% |
| roberta-base | 3 | 5 | 5 e-5 | 192 | 16 | 68.87% |
| roberta-base | 3 | 6 | 5 e-5 | 192 | 16 | 65.92% |

Other Models:
-------------

Results:

| Model | Gradient Accumulation Step | Number of Epochs | Learning Rate | Maximum Sequence Length | Batch Size | Accuracy |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| bert-base-uncased | 1 | 3 | 5 e-5 | 128 | 32 | 60.63% |
| bert-large-uncased | 2 | 3 | 5 e-5 | 64 | 12 | 25.09% |


Running RoBERTa-Base Uncased (Sem-Supervised Approach):
-------------------------------------------------------
- Semi-Supervised approach for multiple choice question answering task as defined here in the paper - [Improving Language Understanding
by Generative Pre-Training](https://cdn.openai.com/research-covers/language-unsupervised/language_understanding_paper.pdf) by OpenAI on the [official CosmosQA dataset](https://github.com/wilburOne/cosmosqa/tree/master/data/)
- [Google Colab Link](https://colab.research.google.com/drive/1E6rILWpl5rjAp-ModE9u0PlUhbv0N59c)

Results:

| Model | Gradient Accumulation Step | Number of Epochs | Learning Rate | Maximum Sequence Length | Batch Size | Accuracy |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| roberta-base | 2 | 3 | 5 e-5 | 80 | 16 | 62.479 |
| roberta-base | 3 | 4 | 5 e-5 | 80 | 64 | 67.2 |
| roberta-base-uncased | 3 | 3 | 2 e-5 | 100 | 8 | 61.13 |

Running External Knowledge Infusion (SocialIQA Dataset):
--------------------------------------------------------

- TODO Google Colab Link

Results:

| Model | Gradient Accumulation Step | Number of Epochs | Learning Rate | Maximum Sequence Length | Batch Size | Accuracy |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| roberta-base + finetuned on SocialIQA | 3 | 6 | 5.00E-05 | 192 | 16 | 67.75 |
| roberta-base + finetuned on SocialIQA + COSMOS finetuned | 3 | 6 | 5.00E-05 | 192 | 16 | 66.2 |

Running Context Summarization:
------------------------------

- TODO Google Colab Link

Results:

| Model | Gradient Accumulation Step | Number of Epochs | Learning Rate | Maximum Sequence Length | Batch Size | Accuracy |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| roberta-base + sumarization + COSMOS | 3 | 5 | 5.00E-05 | 192 | 16 | 63.31 |
| roberta-base + context + summarization + COSMOS | 3 | 5 | 5.00E-05 | 192 | 16 | 67.57 |
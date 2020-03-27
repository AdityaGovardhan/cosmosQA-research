Status:
=======

- Error analysis completed for multiway attention model and RoBERTa (base) model ([link](https://www.google.com))

- Please check out [AdityaGovardhan/transformer](https://github.com/AdityaGovardhan/transformers) GitHub repository for modifications related to RoBERTa.

- random baseline model provided by [Allen AI](https://leaderboard.allenai.org/cosmosqa/submissions/public) is setup, ran and tested ([Google Colab link](https://colab.research.google.com/drive/12ufgKApJTgajMzcasmyYMRwxWrCe-ws5))

- [Lifu Huang et al.](https://wilburone.github.io/cosmos/)'s multiway attention model is setup, ran and tested ([Google Colab link](https://colab.research.google.com/drive/1_FDdq9upg6n3voJoIrG7NhjsYYid8yyH))

- [RoBERTa baseline model](https://huggingface.co/transformers/model_doc/roberta.html) setup, ran and tested ([Google Colab link](https://colab.research.google.com/drive/1TL8QsMCY2zog_KYjiVbyi3WN5l_r-uAA))

___

Individual Efforts:
-------------------

- Kunal : 
1. Trying to run cosmosqa_wilburOne on asu agave. Current status is that the cluster is not picking up my job. 
2. Attempting to run the Roberta model on CoLAB.
3. Setting up a framework for performing error analysis on the test and validation datasets.
4. Phase 1 report.
5. Performed Error Analysis on 15 samples from 1000-1500 in the Validation set data

- Jay : 

1. Was able to run the cosmosqa_wilburOne on my local CPU machine (without GPUs), but since the training + evaluation with huge datasize shall take time, trying to host the process on either Google Colab/Cloud Shell - but facing issues with installing Nvidia/Apex and few other version conflicts. 
2. Also, trying to read the [https://arxiv.org/pdf/1904.01172.pdf] paper in order to come up with model tweaks for error analysis.
3. Now running the cosmosqa_wilburOne process on my [Google Colab](https://colab.research.google.com/drive/1JKLkB238zHKXNNdGA9H2kCXhAVTXCrjb#scrollTo=Cvv7loTb2SC0) account with varying values of batch-sizes, epochs and train_examples (training data)
4. The updates results with different parameters are being stored in the results/ folder and to be later used for error analysis purposes.

- Aditya :
1. Random baseline model provided by Allen AI setup, ran and tested on [Google Colab](https://colab.research.google.com/drive/12ufgKApJTgajMzcasmyYMRwxWrCe-ws5)
2. Tried running cosmosqa_wilburOne on Windows + GPU setup, but couldn't proceed further since 'apex' library by NVIDIA has limited support for CUDA in Windows.
3. Tried running cosmosqa_wilburOne on Windows Subsystem for Linux (WSL), couldn't proceed further since WSL doesn't have GPU access
4. Multiway Attention model ran successfully on [Google Colab](https://colab.research.google.com/drive/1_FDdq9upg6n3voJoIrG7NhjsYYid8yyH), debugged issues along with Jay and Kunal
5. RoBERTa baseline model ran successfully on [Google Colab](https://colab.research.google.com/drive/1TL8QsMCY2zog_KYjiVbyi3WN5l_r-uAA), debugged issues along with Vasishta and Suryanshu
6. Error Analysis for multiway attention model
7. Report

- Vasishta : 
1. Evaluating the use of Amazon Web Service GPU instances K80 P2.xlarge to run cosmosqa_wilburOne for the project along
2. Setup and running roBERTa on Google Colab.
3. Debugged roBERTa backward compatibilty issue - "KeyError: 'token_type_ids'".
4. Tried older roBERTa model to bypass the token type embedding layer issue.
5. Phase 1 Report.
6. Performed Error Analysis on 19 samples from 2000-2500 in the Validation set data


- Suryanshu :
1. Went through the CosmosQA paper and forum "http://jalammar.github.io/illustrated-bert/" to get some idea about normal BERT working. Also going trying to go through GPT2 paper as it has been used to improve the performance of cosmosQA.
2. Initially, was trying to run the project(cosmosqa_wilburOne) on my windows system but didnt succeed due to failure in installing apex module correctly.
3. Installed Ubuntu as dual boot. Tried running cosmosqa_wilburOne. Had issues with cuda installation initially but later, could install apex, cuda and was able to acees GPU computes on my system. Currently, having issues with GPU memory consumption by cuda. 

___

Running cosmosqa_baseline:
--------------------------
- This random baseline model is provided by [Allen AI](https://leaderboard.allenai.org/cosmosqa/submissions/public) for demonstrating input and output of data.
- [Google Colab link](https://colab.research.google.com/drive/12ufgKApJTgajMzcasmyYMRwxWrCe-ws5)

___

Running cosmosqa_wilburOne:
---------------------------
- This multiway attention model is provided by [Lifu Huang et al.](https://wilburone.github.io/cosmos/).
- [Google Colab link](https://colab.research.google.com/drive/1_FDdq9upg6n3voJoIrG7NhjsYYid8yyH)

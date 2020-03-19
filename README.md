Status:
=======

- random baseline model provided by Allen AI setup, ran and tested

- wilburOne's baseline model setup in progress

- research paper reading in progress

___

Individual Efforts:
=======

- Kunal : Trying to run cosmosqa_wilburOne on asu agave. Current status is that the cluster is not picking up my job. 

- Jay : Was able to run the cosmosqa_wilburOne on my local CPU machine (without GPUs), but since the training + evaluation with huge datasize shall take time, trying to host the process on either Google Colab/Cloud Shell - but facing issues with installing Nvidia/Apex and few other version conflicts. 
Also, trying to read the [https://arxiv.org/pdf/1904.01172.pdf] paper in order to come up with model tweaks for error analysis.

- Aditya :
1. random baseline model provided by Allen AI setup, ran and tested
2. Tried running cosmosqa_wilburOne on Windows + GPU setup, but couldn't proceed further since 'apex' library by NVIDIA has limited support for CUDA in Windows.
3. Tried running cosmosqa_wilburOne on Windows Subsystem for Linux (WSL), couldn't proceed further since WSL doesn't have GPU access
4. Currently debugging running cosmosqa_wilburOne on [Google Colab](https://colab.research.google.com/drive/1sQ61kjP3AB1fxOCj_vJfIXnHn_X1CF9D).

- Vasishta : Evaluating the use of Amazon Web Service GPU instances K80 P2.xlarge to run cosmosqa_wilburOne for the project along with Aditya. Trying to understand the project in hand better.

- Suryanshu :
1. Went through the CosmosQA paper and forum "http://jalammar.github.io/illustrated-bert/" to get some idea about normal BERT working. Also going trying to go through GPT2 paper as it has been used to improve the performance of cosmosQA.
2. Initially, was trying to run the project(cosmosqa_wilburOne) on my windows system but didnt succeed due to failure in installing apex module correctly.
3. Installed Ubuntu as dual boot. Tried running cosmosqa_wilburOne. Had issues with cuda installation initially but later, could install apex, cuda and was able to acees GPU computes on my system. Currently, having issues with GPU memory consumption by cuda. 

___

Running cosmosqa_baseline:
--------------------------
- This random baseline is provided by [Allen AI](https://leaderboard.allenai.org/cosmosqa/submissions/public) for demonstrating input and output of data.
- [Google Colab link](blablbla.com)





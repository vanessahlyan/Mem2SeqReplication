# Mem2SeqReplication
This repo is for the Replication project in the Advanced Language Processing Class at Yale University in Fall 2020. I am replicated the paper "Mem2Seq: Effectively Incorporating Knowledge Bases into End-to-End Task-Oriented Dialog Systems" by Madotto et al., published in ACL 2018. (http://aclweb.org/anthology/P18-1136)

## To run experiments
Below are two sample commands to train the VanillaSeqToSeq model and Mem2Seq model respectively. Make sure to specify the decoder that you'd like to run (eg. VanillaSeqToSeq), number of layers in the model, the batch size, the dataset (babi or kvr), and the task (1 to 6 for babi, blank for kvr)

# python3 main_train.py -lr=0.0001 -layer=1 -hdd=256 -dr=0.1 -dec=VanillaSeqToSeq -bsz=16 -ds=babi -t=1

To test a model's performance, run a command like the following. Make sure to specify the decoder that you're evaluating on, the relative path to the trained model, batch size, dataset, and task number. 

# python3 main_test.py --dec=Mem2Seq -path="save/mem2seq-KVR/HDD512BSZ16DR0.4L3lr0.001Mem2Seq8.44" -bsz=16 -ds=kvr -t=


## Dataset
The /data folder has two subfolders, one for the KVR dataset and one called /dialog-bABI-tasks. Tasks 1-5 in the latter repo corresponds to tasks 1-5 for the bAbI dialog tasks, whereas task 6 is for the DSTC2 task. 

## Utils
The /utils folder contains script to import and batch the data for each dataset.

## Models
The /models folder contains the implementation of the 3 baseline models in addition to Mem2Seq.

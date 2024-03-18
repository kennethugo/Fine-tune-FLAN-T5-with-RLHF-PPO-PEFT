# Fine-tune FLAN-T5 with Reinforcement Learning with Human Feedback, Proximal policy optimzation (PPO) and PEFT-LoRA
This repository provides a detailed guide on fine-tuning a large language model with Reinforcement Learning with Human Feedback (RLHF), Leveraging Meta AI's hate speech reward model. The aim is to generate less toxic text summarization contents. A pretrained Flan-T5 model from HuggingFace which has already been fine-tuned using with Parameter Efficient Fine-Tuning (PEFT) - LoRA had proximal policy optimization (PPO) applied to it adapters. 

# Table of Content
* [**Introduction**](##Introduction)
* [**Getting Started**](##Getting-Started)
* [**Methodology and Results**](##Methodology-and-Results)
* [**Conclusion** ](##Conclusion)
* [**Further work** ](##Further-work)

# Introduction
This project demonstrates the fine-tuning of an LLM (FLAN-T5) aimed at generating less toxic content. Leveraging Meta AI's hate speech reward model (facebook/roberta-hate-speech-dynabench-r4-target ), a binary classifier predicting either "not hate" or "hate" for the provided text. Proximal Policy Optimization (PPO) was used to fine-tune and reduce the model's toxicity.

# Getting started 
The following steps will help you get started:

This projects was originally carried out in an AWS Sagemaker notebook. The Instance type from SageMaker Comprises of Eight vCPU, 32 gigabyte. This is the AWS instance type from SageMaker, ml.m5.2xl

![instance_type](https://github.com/kennethugo/PEFT-LoRA_Fine-tuning/assets/50516854/ca0fa9b2-54ec-4737-a8a7-35c1e17bcceb)

1 - Set up Kernel and Required Dependencies

    torch==1.13.1 \
    
    torchdata==0.5.1 --quiet
    
    transformers==4.27.2 \
    
    evaluate==0.4.0 \
    
    rouge_score==0.1.2 \
    
    peft==0.3.0 --quiet

2 - Load FLAN-T5 Model, Prepare Reward Model and Toxicity Evaluator

* 2.1 - Load Data and FLAN-T5 Model Fine-Tuned with Summarization Instruction

* 2.2 - Prepare Reward Model

* 2.3 - Evaluate Toxicity

3 - Perform Fine-Tuning to Detoxify the Summaries

 * 3.1 - Initialize PPOTrainer

 * 3.2 - Fine-Tune the Model

 * 3.3 - Evaluate the Model Quantitatively

 * 3.4 - Evaluate the Model Qualitatively

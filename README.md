# Optimizing an ML Pipeline in Azure

## Overview
This project is part of the Udacity Azure ML Nanodegree.
In this project, we build and optimize an Azure ML pipeline using the Python SDK and a provided Scikit-learn model.
This model is then compared to an Azure AutoML run.

## Useful Resources
- [ScriptRunConfig Class](https://docs.microsoft.com/en-us/python/api/azureml-core/azureml.core.scriptrunconfig?view=azure-ml-py)
- [Configure and submit training runs](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-set-up-training-targets)
- [HyperDriveConfig Class](https://docs.microsoft.com/en-us/python/api/azureml-train-core/azureml.train.hyperdrive.hyperdriveconfig?view=azure-ml-py)
- [How to tune hyperparamters](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-tune-hyperparameters)


## Summary
**The dataset provides insights into a financial institution's marketing campaign.**

**The best performing model is the VotingEnsemble of AutoML config run."**

## Scikit-learn Pipeline
1. Data is read from file
2. Clean data, prepare for training
3. Split the data to train, test parts
4. Train LogisticRegression model with the data
5. Config 'C', and 'max_iter' as the hyper parameter for the Parameter Sampling

**What are the benefits of the parameter sampler you chose?**
The sampler help me try on variety of C and max_iter to and then I can choose the best model to use futhur.

**What are the benefits of the early stopping policy you chose?**
This help to stop the training early when the criteria is met, not always run "max_total_runs" times.

## AutoML
In the best run, automl help to generate the VotingEnsemble model with hyper parameters with a lot of algorithms: XGBoost, LogicticRegression and data transfromation: StandardScalarWrapper, SparseNormallizer

## Pipeline comparison
**Compare the two models and their performance. What are the differences in accuracy? In architecture? If there was a difference, why do you think there was one?**
The model of automl is better than the sklearn pipeline a little bit. About the architechture, the pipeline is just LogicticRegression algorithm, which decided myself before. While the automl try help me try a lot of solution of algorithm, esspecially the ensemble models with a lot of model and transform combination.

## Future work
**What are some areas of improvement for future experiments? Why might these improvements help the model?**
* For the pipeline, can change some preprocesses and the sampler with difference parameters. This could helps me find the better model.
* For the automl, I think I can analyzed the model explaination to get some insight about the importance variable, the data. So that I can have my own preprocesses. With the additional preprocess, I think the accuracy as well as the training time will be improved

## Proof of cluster clean up
**If you did not delete your compute cluster in the code, please complete this section. Otherwise, delete this section.**
**Image of cluster marked for deletion**

# Autodesk_ADP_Failure_Prediction
## Introduction
Autodesk has recently made a strategic move to a cloud subscription model for its products and services to remain competitive in the industry. This strategic transition to cloud positions Autodesk as a data company. Operating a big data system brings many levels of complexity and challenges. As data moves end to end through a big data platform, there are many opportunities for bottlenecks and system failures caused by infrastructure issues, changes in data volume, upgrades to parts of the system, and more. These unplanned system failures essentially impact Autodesk’s net profit due to high cost (IT and labor) of system repair, customer dissatisfaction and potential loss of market share, as well as the capability to provide timely data to support functions and analytics teams within Autodesk. Therefore, Autodesk is looking forward to a solution that will identify and remediate a system issue before it causes a failure. 

Our primary stakeholder team inside Autodesk manages Autodesk Data Platform (ADP) which is an AWS-based big data architecture that stores organizational data in S3 for processing, launches virtual servers and manages storage in EC2, and monitors all systems’ metrics in CloudWatch. As ADP is still in the initial stages of transforming to AWS cloud service, it faces several challenges externally as well as internally. One of the major internal challenges is managing system failures which occur due to scale and complexity of big data systems. 
In an attempt to consolidate data on a single cloud enterprise platform, managing uptime and predicting failure modes for big data systems is a huge challenge for ADP. Specifically, maintaining high availability of systems is a significant problem. These failures cause inefficiency in terms of providing quality data in a timely manner to downstream businesses, negatively impact customer experience, and most importantly, result in revenue losses. In the long term, if these failures are not controlled, Autodesk will be at risk of losing customers, and its strategic move to the cloud will fail. In a nutshell, ADP needs a model to analyze historical failures to control future failures.

## Methods
*Transform the unstructured system logs to analysable data, using Python parser.
*Conduct data mining and insight exploration with Apache Spark and PySpark.
*Building prediction models with python: python parser package, supervised learning, unsupervised learning, data mining, machine learning, and statistical modeling.

## Keywords Extraction
The first thing is to extract key information from logs. We firstly defined keywords to search, using [text clustering](https://github.com/mengyjia/Autodesk_ADP_Failure_Prediction/blob/master/Text%20Clustering%20Using%20Pyspark.ipynb).
Then we use different numbers to represent those keywords and thus compiled a keyword list. Based on that list, we used pyspark to parse log files.Please see [Log_Keywords_Extraction.ipynb](https://github.com/mengyjia/Autodesk_ADP_Failure_Prediction/blob/master/Log_Keywords_Extraction.ipynb).
After parsing, a several-thousand-line log file will become a list:
```
[1,2,3,4,6,6,6,7,8,35,67]
```
Here, every number represents a unique keyword and the sequence of those numbers represents the sequence that keywords occur in that log file.
## Machine Learning Classification 
Then we adopted machine learning algorithms to predict failure. Please see [Traditional Machine Learning Method-Copy1.ipynb](https://github.com/mengyjia/Autodesk_ADP_Failure_Prediction/blob/master/Traditional%20Machine%20Learning%20Method-Copy1.ipynb)

## RNN
We also used neural network to do the classification job. You can check [Deep_Learning_Mar08.ipynb](https://github.com/mengyjia/Autodesk_ADP_Failure_Prediction/blob/master/Deep_Learning_Mar08.ipynb)



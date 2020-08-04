# AWS Machine Learning Speciality Certification (MLS-C01)

Passed the MLS-C01 certification in July 2020 with 941/1000. There is not much detailed info on the exam compared to other popular AWS certifications, so I want to give as detailed information as possible. Everybody who is looking into this certification will have a better idea what he can expect from the exam.

There is no gold standard for preparing for MLS-C01. Compared to other popular certifications there are only very few resources to be used aside from Amazon's official papers and videos (which are very good!)

I made use of free trials on LinuxAcademy and ACloudGuru to go over their MLS-C01 preparation course. I'd estimate both courses are overlapping for at least 80% of the topics. Most important takeaway from those two courses: Neither of them will get you the certification. Both give a good overview of topics, but they just scratch the surface and you will need to go much deeper into almost all topics in order to have a shot at passing the certification. Don't be fooled by the practice exams at the end! The questions are not as detailed as the real questions will be.

## What I already knew:

To put everything what I am going to say about the exam into perspective, here is the stuff that I already knew before going after this certification:

- I have been dabbling in Data Engineering/Data Science for a couple years as an autodidact. At the beginning of the year I decided to participate in a 3-month fulltime Data Science-bootcamp at [neuefische.de](http://neuefische.de) which consolidated and broadend my knowledge. 
- Already have Amazon's Cloud Solutions Architect Associate (SAA-C02) under my belt. This helps a lot when dismissing answers in AWS Services related questions.
- 15+ years experience with various programming languages, database systems, development patterns and IT best practices.

## What I used as preparation for the exam:

- LinuxAcademy [MLS course](https://linuxacademy.com/course/aws-certified-machine-learning-specialty/) (good overview)
- ACloudGuru [MLS course](https://acloud.guru/learn/aws-certified-machine-learning-specialty) (good overview)
- AWS SageMaker [Documentation](https://docs.aws.amazon.com/sagemaker/index.html) (that's where I spent most of my time)
- Sagemaker DeepDive [YouTube Playlist](https://www.youtube.com/watch?v=uQc8Itd4UTs&list=PLhr1KZpdzukcOr6jzmSrvYnLUtgqsZz)  (very good! shows a lot of dry stuff from the docs in action)
- Bunch of SageMaker presentations from [re:invent](https://www.youtube.com/results?search_query=re%3Ainvent+2019) (mainly 3xx/4xx)
- AWS Machine Learning [Blog](https://aws.amazon.com/de/blogs/machine-learning/) (imo most of the scenario based questions in the exam are coming from case studies from the blog)
- Book: [Hands-On Machine Learning by Geron](https://www.oreilly.com/library/view/hands-on-machine-learning/9781492032632/) (very good ML book overall, mainly used to refresh my memory in some areas)

## What I used to test my knowledge:

- Udemy Practice [Exam by Abhishek Singh](https://www.udemy.com/course/aws-certified-machine-learning-specialty-full-practice-exams/) (very, very good questions which come pretty close to the style of the real exam questions)
- Udemy Practice [Exam by Frank Kane](https://www.udemy.com/course/aws-machine-learning-practice-exam/) (imo a lot weaker (not as close to the exam questions) exam than the one from Singh, still worth the money to find blank spots)
- AWS MLS Practice exam (40$ for 20 exam questions - would spent the money on it (had a voucher from passing SAA-C02))

## What I was tested on during the exam:

- __no__ questions about hyperparameter, input types, parallelization of built-in algorithms 
- LOTS of questions regarding preprocessing of datasets
  - dropping/imputation, oversampling
  - dealing with skewed datasets (log-transform, binning, etc)
  - what to do with correlating/depending features in linear regression
  - how to scale and split a dataset correctly (split then scale training and fit test/validation vs scale all and split afterwards, etc)
  - mitigation of high/low correlation in datasets with lots of raw features
  - what to look for in features (high correlation vs low correlation, etc)
- lots of questions about dealing with over- and underfitting in general and specifically in neural nets
  - dropout, early stopping, decrease number of hidden layers,... in all variations and scenarios
  - regularization (L1 vs L2)
- evaluation metrics
  - trick question with switching positive/negative observations so you have to adjust to that
  - business implications of misclassification (FN more/less impact on cost of business, etc)
  - calculate accuracy and precision
  - interpret 3x3 confusion matrix
- visualization
  - best visualization types for various situations
  - visualization for correlation of features (scatter plots)
- custom algorithms
  - docker container (which services are used ECR? ECS? both? S3?)
  - process of deploying an algorithm in a custom docker container
  - docker related questions about entrypoints, paths (/opt/ml,...)
  - transfer learning
- hyperparamter optimization
  - xgBoost init statement - which hyperparameter to optimize when overfitting
  - neural net - learning rate/batch size tuning
- scaling/load balancing
  - Endpoint Configuration calculate InvokePerInstance based on given numbers
  - TensorFlow scaling with horovod
  - multiple questions with IoT devices (and managing endpoints) vs using Neo
- algorithm choices
  - business scenarios, which algo to use
    - regression scenario
    - recommendation scenario
    - binary classification
  - anomaly detection scenario - which algorithm to use
- chaining of AWS Services (most of them regarding ETL)
  - scenarios where you should chain services/algorithms as solutions (transcribe, translate,..)
  - classic ETL questions: Glue vs Data Pipeline vs Kinesis (in combination with Lambda, Elasticsearch,...)
  - EMR related questions (PySpark integrated solutions, "EMR legacy solution" inclusion, ...)
- SageMaker Security
  - company has certain standards regarding tags, instance-types - how can this be accomplished? (aws service catalog vs python script vs cloudformation script vs ...)
generic question
  - optimized filetypes for Athena
  - Normal vs Poisson-Distribution
  - Baysian Network/Naive Bayes/Pearson co-effcient
  - Classification Scenario: Which algorithm to use ? (classic SVM RBF Kernel plot - probably all you need to know about SVM)
  - Question regarding activiation function of NN in certain scenario (Softmax vs ReLu vs ...)

## What I did not expect to see in the exam (but it was mentioned/given as an option):

- AWS Service Catalog
- AWS Connect 
- AWS Alexa Business

## What makes this exam much different to SAA-C02:

The range of level of detail across the questions is a lot wider in MLS-C01. There can be an ETL question were answers rely on knowing supported input/output filetypes of various AWS Services. Other questions have very broad answers like "use kinesis and store it in s3".

---

If you are going for this certification I encourage you to spend a lot of time in SageMaker itself. Do not just click "Run all cells" in a example notebook. Built models yourself, launch endpoints, find other ways to deploy the same stuff (by using docker containers f.e.). Have as much hands-on experience as possible!

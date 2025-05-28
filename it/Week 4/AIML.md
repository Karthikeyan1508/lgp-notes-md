## Confusion Matrix

A confusion matrix is a performance evaluation tool in machine learning, representing the accuracy of a classification model. It displays the number of true positives, true negatives, false positives, and false negatives. This matrix aids in analyzing model performance, identifying mis-classifications, and improving predictive accuracy.A Confusion matrix is an N x N matrix used for evaluating the performance of a classification model, where N is the total number of target classes. The matrix compares the actual target values with those predicted by the machine learning model. This gives us a holistic view of how well our classification model is performing and what kinds of errors it is making.
For a binary classification problem, we would have a 2 x 2 matrix, as shown below, with 4 values:

![image](https://github.com/user-attachments/assets/c6356afe-8b96-4378-b759-09225cf39941)

1. The target variable has two values: Positive or Negative
2. The columns represent the actual values of the target variable
3. The rows represent the predicted values of the target variable

### True Positive (TP) 
The predicted value matches the actual value, or the predicted class matches the actual class.
The actual value was positive, and the model predicted a positive value.

### True Negative (TN) 
The predicted value matches the actual value, or the predicted class matches the actual class.
The actual value was negative, and the model predicted a negative value.

### False Positive (FP) – Type I Error
The predicted value was falsely predicted.
The actual value was negative, but the model predicted a positive value.
Also known as the type I error.

### False Negative (FN) – Type II Error
The predicted value was falsely predicted.
The actual value was positive, but the model predicted a negative value.
Also known as the type II error.

For eg, consider a classification dataset with 1000 data points. We fit a classifier (say logistic regression or decision tree) on it and get the below confusion matrix:

![image](https://github.com/user-attachments/assets/c7b3b881-22b8-4592-8027-4178e16be5a0)


The different values of the Confusion matrix would be as follows:
True Positive (TP) = 560, meaning the model correctly classified 560 positive class data points.
True Negative (TN) = 330, meaning the model correctly classified 330 negative class data points.
False Positive (FP) = 60, meaning the model incorrectly classified 60 negative class data points as belonging to the positive class.
False Negative (FN) = 50, meaning the model incorrectly classified 50 positive class data points as belonging to the negative class.

## Metrics based on Confusion Matrix Data

1. Accuracy
Accuracy shows how many predictions the model got right out of all the predictions. It gives idea of overall performance but it can be misleading when one class is more dominant over the other. For example a model that predicts the majority class correctly most of the time might have high accuracy but still fail to capture important details about other classes. It can be calculated using the below formula:

![image](https://github.com/user-attachments/assets/428643e3-4caa-4f43-9b35-9d185f2c3d84)

2. Precision
Precision focus on the quality of the model’s positive predictions. It tells us how many of the "positive" predictions were actually correct. It is important in situations where false positives need to be minimized such as detecting spam emails or fraud. The formula of precision is:

![image](https://github.com/user-attachments/assets/e4acd1f4-bc2f-432b-b757-a7ef03031e20)

3. Recall
Recall measures how good the model is at predicting positives. It shows the proportion of true positives detected out of all the actual positive instances. High recall is essential when missing positive cases has significant consequences like in medical tests.

![image](https://github.com/user-attachments/assets/74418d33-5c2f-4731-aec8-9b37bda84a65)

4. F1-Score
F1-score combines precision and recall into a single metric to balance their trade-off. It provides a better sense of a model’s overall performance particularly for imbalanced datasets. It is helpful when both false positives and false negatives are important though it assumes precision and recall are equally important but in some situations one might matter more than the other.

![image](https://github.com/user-attachments/assets/c7f703f3-f035-4b4c-b332-8cc579cbe63c)

5. Specificity
Specificity is another important metric in the evaluation of classification models particularly in binary classification. It measures the ability of a model to correctly identify negative instances. Specificity is also known as the True Negative Rate Formula is given by:

![image](https://github.com/user-attachments/assets/ec1065ed-e9e3-49cf-aa73-b689f641404b)

## ML pipeline
A machine learning pipeline (ML pipeline) is the systematic process of designing, developing and deploying a machine learning model. ML pipelines or ML workflows follow a series of steps that guide developers and business leaders toward more efficient model development.
The end-to-end machine learning pipeline comprises three stages: 
**Data processing:** Data scientists assemble and prepare the data that will be used to train the ML model. Phases in this stage include data collection, preprocessing, cleaning and exploration. 
**Model development:** Data practitioners choose or create a machine learning algorithm that fits the needs of the project. The algorithm is trained on the data from the previous step and the resulting model is tested and validated until it is ready for use. 
**Model deployment:** Developers and software engineers deploy the model for real-world use, integrating it into a production environment and monitoring its performance. 

### Stage 1: Data processing
After scoping out the problem the ML model is to solve, the first step in an ML workflow is to collect, prepare and analyze the data. Practitioners must identify relevant data sources, gather and integrate data from them, prepare and clean the data, employing data science techniques including feature engineering to arrive at a prepared data set. 
The data processing stage is usually the most time-consuming. But ML model performance hinges on good data. Any errors and oversights in the data engineering phase negatively affect the model’s performance across its lifecycle. Data automation strategies can reduce the time and human effort required to produce strong training datasets. 
Data processing includes: 
1. Data ingestion 
2. Data preprocessing
3. Data exploration
4. Feature engineering
5. Data splitting

**Data ingestion:**
Data ingestion is the collection and import of data from disparate data sources into a centralized data repository through a data pipeline. Data scientists must identify appropriate data sources, such as proprietary enterprise data stored internally—sales reports, customer demographics and other organizational knowledge. 
Sometimes external data is also required. External data sources can include API connections to data providers, data scraped from the internet or synthetic data. Because new data is always being created, data ingestion is often a continuous process.

**Data preprocessing:**
Data preprocessing, or data preparation, transforms the raw data from the previous step into clean data that is ready for analysis. After gaining an understanding of the training data through exploratory data analysis (EDA), data scientists select data preprocessing strategies. Data preprocessing steps include: 
-> Data wrangling (data transformation): Transforming the data into the appropriate format 
-> Identifying missing values and dealing with outliers
-> Data cleaning: Correcting errors in the dataset
-> Data normalization: Standardizing the dataset
-> Denoising: Removing random errors and signal interference 
-> Data integration: Combining the data into a unified dataset

**Data exploration:**
Data exploration is the process of evaluating data to understand the information it contains. EDA aims to learn the characteristics of the data, discover patterns and relationships and identify insights with the help of data visualization tools. 
EDA findings inform the model selection choices that occur next.

**Feature engineering:**
Feature selection is a critical data preprocessing step that involves identifying the most relevant features, or characteristics, of the data points. Data features are extracted and selected that give the model the best possible chance of solving real-world challenges. 
Focusing on the wrong features can result in a model that doesn’t perform as intended. After applying feature extraction techniques to streamline the data, data scientists choose the features that will lead to the strongest model predictions.

### Stage 2: Model development
After the training data has been prepared, the next step in the ML workflow is to build the machine learning model. The process of creating a deep learning model involves selecting an appropriate machine learning algorithm and exposing it to the training datasets. The result of this process is the creation of an AI model ready for real-world use with similar unseen data. 
The model development process involves: 
1. Model selection 
2. Hyperparameter tuning 
3. Model training
4. Model evaluation

**Model selection**
Model selection is the process of choosing the type of model that is most likely to deliver top performance in the intended use case. The initial project planning stages have already given all stakeholders and participants a clear understanding of the business needs, limitations and project goals. ML practitioners base their choices on these factors, balancing optimization with feasibility. 
Choices include linear regression and logistic regression, random forests and decision trees, neural networks and large language models (LLMs), support vector machines (SVMs), ensemble models, agentic systems and many others. 
Depending on the nature of the machine learning challenge, certain types of algorithms make more suitable candidates. 
For example, neural networks can handle complex generative AI challenges but come with high compute costs and are more prone to overfitting. Regression models are compute-efficient but have limited use cases.

**Hyperparameter tuning**
Model hyperparameters are external variables that control the model’s behavior during training. Hyperparameters also govern the shape of the model that the algorithm builds, such as the number of neurons and layers in a neural network. 
Hyperparameter tuning is the process of optimizing the hyperparameters so that the training process produces a top-performing model. Data scientists can set hyperparameters manually but usually automate the process through various algorithms and other techniques.

**Model training**
Model training is the process of optimizing a model’s performance with training datasets that are similar to the input data the model processes once deployed. A machine learning training pipeline is an extensive system that can take any number of shapes depending on the algorithm and the task for which the model is being developed. 
Many training methods revolve around minimizing a loss function that measures the model’s error: the gap between the model’s outputs and real-world data values. With each round of training, the new model updates its parameters as it fits closer to the training data. Each update iterates on previous results. 
Model training methods include: 
-> Supervised learning: The model is trained on a dataset of structured data. Inputs are labeled with corresponding outputs, teaching the model how to associate input features with the correct output values. 
-> Unsupervised learning: The model is trained on unstructured data and must discern the patters and relationships between data points and features on its own. 
-> Semi-supervised learning: The model is trained in a hybrid method that mixes supervised and unsupervised learning. 
-> Self-supervised learning: The model is trained with unlabeled data for tasks that usually call for supervised learning. 
-> Reinforcement learning: The model is trained to take the actions that generate the largest possible reward, rather than minimize error. 
-> Continual learning: The model is trained on a real-time stream of input data, as opposed to a preassembled training dataset.

**Model evaluation**
After the model is deemed to be trained—such as when its loss function has been sufficiently minimized—its performance is evaluated before deployment. The LLM evaluation process uses the testing and validation datasets that were prepared during the data splitting phase.

1. Validation
Validation estimates the model’s prediction error: how good is it at making the correct predictions? During training, the machine learning algorithm often outputs multiple models with various hyperparameter configurations. Validation identifies the model with the optimal hyperparameter configuration.

2. Testing
Testing simulates real-world values to evaluate the best-performing model’s generalization error: how well does the model adapt to new unseen data? Test data is independent of training data and benchmarks the model’s performance after training is complete. Tests reveal whether the model will perform as intended after it is deployed.

### Stage 3: Model deployment
After developing a suitable model with strong performance, it’s time to put that model to work. Model deployment serves the model to users in the intended production environment. This can be anything from a mobile app or API connection to a pharmaceutical development or robotics research facility. 

Models don’t begin working until they are actively deployed. Achieving strong results from a machine learning project means that the model must be deployed in a way that makes it easy to use, whether that is by consumers, business leaders or other computer systems. 

Model deployment includes: 
-> Model serialization 
-> Integration 
-> Architecture 
-> Monitoring 
-> Updates 
-> Compliance

**Model serialization**
Serialization is a common deployment method that involves converting a model into a format that can be stored and transmitted, then deserializing it in the production environment. It’s like packing up a roomful of belongings into a box, moving the box to a new home, then unpacking to set up the new room. 
For example, Python, a coding language popular with ML development, recommends the pickle framework for deployment.

**Integration**
Integration incorporates the model into its production environment, such as a mobile app. Models can be served through cloud computing providers such as AWS or Azure, or hosted onsite. Alternatively, it might be better to use a containerized solution such as Kubernetes and Docker. 
Depending on how the model will be served, developers need to make the model accessible with the appropriate machine learning libraries and frameworks, such as PyTorch or TensorFlow Serving.

**Architecture**
Portability and scalability are two primary concerns to consider during ML deployment. 
1. Portability is the ease with which the model can be transferred between systems. 
2. Scalability is the model’s ability to handle growing workloads, such as an increasing user base, without needing to be redesigned. 

The model’s production environment must be able to support the projected growth of the machine learning project. Autoscaling and orchestration tools can help field increased demand over time.

**Monitoring**
The ML workflow isn’t complete once the model is deployed. The model’s performance must be monitored over the course of the AI lifecycle to avoid model drift: when performance suffers due to changes in data distribution. Many other metrics pertain to the model’s ability to generate and process tokens: a single unit of input or output. Some of these metrics include: 
1. Time per output token (TPOT) / inter-token latency (ITL): The amount of time it takes for the model to generate a token. 
2. Time to first token (TTFT): The amount of time it takes for a model to generate the first token of its response. 
3. Throughput: A measure of the model’s overall token generation capacity, measured in tokens per second (TPS). 
4. Latency: The amount of time it takes for the model to generate a complete output after receiving a user input.

**Updates**
Unless a model is being trained with continual learning, its training dataset is finite. A model’s knowledge cutoff refers to the last date on which its knowledge base was updated with new data. Over time, a model becomes less relevant as the information in the knowledge base grows more dated. 
Models must be regularly updated to mitigate model drift and keep error rates to an acceptable minimum. New data, new features and algorithmic updates can both optimize model performance. Retraining can also help models stay current.

**Compliance**
Wherever data collection is concerned, model operators must consider all relevant legal regulations and requirements surrounding privacy, intellectual property, copyright and other concerns. For example, HIPAA protects medical data in the U.S., while GDPR provides specific data protections to people in the European Union. 
Models built for use in regulated industries such as pharmaceuticals and finance might also be subject to stricter operating controls. Any models used in an enterprise setting likely process sensitive internal data, necessitating strong cybersecurity measures. 
Model operators are obligated to protect user data and prevent their models from being used for malicious ends, such as fraud and misinformation. One advantage of open-source models is that anyone can evaluate the model to see how it works and whether it’s abiding by all relevant regulations.

## Deep Learning

Deep learning is a subset of machine learning that uses multilayered neural networks, called deep neural networks, to simulate the complex decision-making power of the human brain. Some form of deep learning powers most of the artificial intelligence (AI) applications in our lives today.

![image](https://github.com/user-attachments/assets/fe84c9c2-7a09-4676-82a5-65e44a414817)

Difference between Machine Learning and Deep Learning
Machine learning and Deep Learning both are subsets of artificial intelligence but there are many similarities and differences between them.

![image](https://github.com/user-attachments/assets/f241b303-2689-48f8-8c0d-a76fb729597f)


## Advantages of Deep Learning
**High accuracy:** Deep Learning algorithms can achieve state-of-the-art performance in various tasks such as image recognition and natural language processing.
Automated feature engineering: Deep Learning algorithms can automatically discover and learn relevant features from data without the need for manual feature engineering.
**Scalability:** Deep Learning models can scale to handle large and complex datasets and can learn from massive amounts of data.
**Flexibility:** Deep Learning models can be applied to a wide range of tasks and can handle various types of data such as images, text and speech.
**Continual improvement:** Deep Learning models can continually improve their performance as more data becomes available.

## Disadvantages of Deep Learning
**Data availability:** It requires large amounts of data to learn from. For using deep learning it's a big concern to gather as much data for training.
**Computational Resources:** For training the deep learning model, it is computationally expensive because it requires specialized hardware like GPUs and TPUs.
**Time-consuming:** While working on sequential data depending on the computational resource it can take very large even in days or months. 
**Interpretability:** Deep learning models are complex, it works like a black box. It is very difficult to interpret the result.
**Overfitting:** when the model is trained again and again it becomes too specialized for the training data leading to overfitting and poor performance on new data.

## Perceptron

Perceptron is a type of neural network that performs binary classification that maps input features to an output decision, usually classifying data into one of two categories, such as 0 or 1.

**Basic Components of Perceptron**

-> Input Features: The perceptron takes multiple input features, each representing a characteristic of the input data.
-> Weights: Each input feature is assigned a weight that determines its influence on the output. These weights are adjusted during training to find the optimal values.
-> Summation Function: The perceptron calculates the weighted sum of its inputs, combining them with their respective weights.
-> Activation Function: The weighted sum is passed through the Heaviside step function, comparing it to a threshold to produce a binary output (0 or 1).
-> Output: The final output is determined by the activation function, often used for binary classification tasks.
-> Bias: The bias term helps the perceptron make adjustments independent of the input, improving its flexibility in learning.
-> Learning Algorithm: The perceptron adjusts its weights and bias using a learning algorithm, such as the Perceptron Learning Rule, to minimize prediction errors.

## Types of Perceptrons
### Single Layer Perceptron
It is a type of perceptron is limited to learning linearly separable patterns. It is effective for tasks where the data can be divided into distinct categories through a straight line. While powerful in its simplicity, it struggles with more complex problems where the relationship between inputs and outputs is non-linear.
The main functionality of the perceptron is:-
1. Takes input from the input layer
2. Weight them up and sum it up.
3. Pass the sum to the nonlinear function to produce the output.

![image](https://github.com/user-attachments/assets/ab7593f0-528d-43a7-8fa9-0a940fd36ca0)


## Types of Neural Networks:

![image](https://github.com/user-attachments/assets/6478c71a-4eb2-4c1d-a426-a46a0862a351)



















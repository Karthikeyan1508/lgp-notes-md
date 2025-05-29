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

## Implementation of Single-layer Perceptron
Let’s build a simple single-layer perceptron to recognize handwritten digits from the MNIST dataset using TensorFlow. This model will help you understand how neural networks work at the most basic level.

## Types of Neural Networks:

![image](https://github.com/user-attachments/assets/6478c71a-4eb2-4c1d-a426-a46a0862a351)

### Convolutional Neural Network (CNN)
Convolutional Neural Networks (CNNs) are deep learning models designed to process data with a grid-like topology such as images. They are the foundation for most modern computer vision applications to detect features within visual data.

**Key Characteristics of CNN**
-> Local receptive fields: CNNs employ small, machine-learning filters that move across the input image, focusing on specific regions to detect local features such as edges, textures, and patterns.
-> Weight sharing: The same filter is applied to various regions of the input image, decreasing the number of parameters and computational complexity while allowing the network to recognize objects regardless of position.
-> Pooling: Pooling layers minimize the spatial dimensions of feature maps, making the network more efficient and adaptable to changes. Max pooling, for example, takes the highest value from each patch, aggregating feature presence while decreasing parameters.

CNNs' structure, which combines local receptive fields, weight sharing, and pooling, makes them extremely efficient and reliable for image processing tasks. This enables CNNs to perform tasks such as image classification, object detection, and segmentation, making them indispensable in computer vision.

### Layers in CNN
The convolutional layer is the primary component of a CNN. It works as a convolution operation by sliding a filter (which is also referred to as a kernel) across the input image and calculating the dot product of the filter and the input's receptive field. This operation aids in detecting local characteristics such as edges, textures, and trends. The layers in CNN are:

**Convolutional Layers:** Apply filters to the input image to extract local features such as edges and textures.
**Pooling Layers:** Reduce the spatial dimensions of feature maps, decreasing the computational load and enhancing feature robustness.
**Fully Connected layers:** Connect every neuron in one layer to every neuron in the next, integrating extracted features for final predictions.
**Dropout:** Randomly sets a fraction of neurons to zero during training to prevent overfitting and improve model generalization.
**Activation Functions:** Introduce non-linearity into the network, enabling the learning of complex patterns; common examples include ReLU and Sigmoid.

### Convolutional Operations and Working
The convolution operation entails sliding a filter across the input image and calculating the dot product between the filter and the local region of interest. This operation generates a feature map that highlights the detected features.
![image](https://github.com/user-attachments/assets/f6c11c5a-49d1-46a4-9203-b1dc2bc6e966)

Where I is the input image, K Is the kernel, and (I,j) are the coordinates of the output feature maps.

**Example of a Convolution Operation**
Consider a 3x3 filter used on a 5x5 input image. The filter moves across the image, computing the dot product at each position, yielding a smaller feature map.
Pooling Operation
Pooling reduces the spatial dimensions of the feature map by aggregating the presence of features in different patches of the map.

### Workflow of CNN
Convolutional Neural Networks (CNNs) are designed to process and analyze visual data by learning spatial feature hierarchies automatically and adaptively. Here's a thorough explanation of how CNNs operate:

![image](https://github.com/user-attachments/assets/90ece1ba-2b81-4d7c-a145-77299fa9a19c)


**1. Input Layer**
The input layer of a CNN receives the image's raw pixel values. A color image typically has three channels (RGB), whereas a grayscale image only has one. For example, a color image measuring 32x32 pixels would have an input dimension of 32x32x3.

**2. Convolutional Layers**
The main operation in convolutional layers is convolution, which involves applying filters (kernels) to the input data. A filter is a small matrix (e.g., 3x3) that moves across an input image and performs element-wise multiplication and summation to yield a single output value. Convolution is the process that produces a feature map or an activation map.

For example, if a 3x3 filter is applied to a 5x5 input image, the filter slides over it, calculating the dot product between the filter and the input. The output feature map captures specific features such as edges, corners, or textures, depending on the filter's learned values.

**3. Stride and Padding**
Stride: The stride determines how the filter traverses the input image. A stride of 1 indicates that the filter moves one pixel at a time, whereas a stride of 2 moves two pixels at a time. Higher strides produce smaller output feature maps.
Padding: Padding is used to control the spatial dimensions of the final feature map. "Same" padding adds zeros around the input's border, resulting in an output feature map with the same dimensions as the input. "Valid" padding does not include any padding, resulting in a smaller output feature map.

**4. ReLU(Rectified Linear Unit)**
The ReLU activation function is widely used in CNNs due to its simplicity and effectiveness. It is defined as:
ReLU(x)=max(0,x)
This means that if the input value is positive, ReLU outputs it directly; otherwise, it returns zero. ReLU helps to mitigate the vanishing gradient problem, allowing for faster and more effective deep network training by keeping the gradient flow active and non-zero for positive inputs.

**5.Pooling Layers**
Pooling layers are used to reduce the spatial dimensions of feature maps, lowering the computational load and the network's parameter count. Pooling is typically used after the convolution and activation layers. Max pooling is the process of extracting the maximum value from each receptive field (for example, 2x2) of the feature map. Average pooling computes the average value for each receptive field.

**6. Stacking Layers**
CNNs are made up of stacked convolutional and pooling layers. Early layers detect basic features such as edges and textures, while later layers detect more complex structures and objects. This hierarchical feature extraction is critical to the success of CNNs in visual recognition.

**7. Fully Connected Layers**
Following several convolutional and pooling layers, the network's high-level reasoning is carried out via fully connected layers (dense layers). Each neuron in these layers is connected to every neuron in the layer before it. The features extracted by the convolutional layers are combined in the fully connected layers to make final predictions.

**8. Dropout**
Dropout layers are commonly used in CNNs to prevent overfitting. During training, dropout randomly assigns a fraction of input units to zero at each update cycle. This helps to make the model more generalizable by preventing it from relying too heavily on individual neurons.

## Recurrent Neural Networks (RNNs)

A recurrent neural network or RNN is a deep neural network trained on sequential or time series data to create a machine learning (ML) model that can make sequential predictions or conclusions based on sequential inputs.

![image](https://github.com/user-attachments/assets/ec12c405-dade-4b85-be19-4daad4824bbe)


The Recurrent Neural Network consists of multiple fixed activation function units, one for each time step. Each unit has an internal state which is called the hidden state of the unit. This hidden state signifies the past knowledge that the network currently holds at a given time step. This hidden state is updated at every time step to signify the change in the knowledge of the network about the past. The hidden state is updated using the following recurrence relation:- 

![image](https://github.com/user-attachments/assets/7b2f6972-c7ca-495d-85f5-1ddc4337f982)

![image](https://github.com/user-attachments/assets/b1b06ee4-b1b5-4064-a8b7-05930aa9020f)

At each time step, the new hidden state is calculated using the recurrence relation as given above. This new generated hidden state is used to generate indeed a new hidden state and so on. 

The basic work-flow of a Recurrent Neural Network is as follows:- 

![image](https://github.com/user-attachments/assets/3c1ddfde-03d6-4d36-a373-6cac42c74030)

Note that h0 is the initial hidden state of the network. Typically, it is a vector of zeros, but it can have other values also. One method is to encode the presumptions about the data into the initial hidden state of the network. For example, for a problem to determine the tone of a speech given by a renowned person, the person's past speeches' tones may be encoded into the initial hidden state. Another technique is to make the initial hidden state a trainable parameter. Although these techniques add little nuances to the network, initializing the hidden state vector to zeros is typically an effective choice. 

**Working of each Recurrent Unit:**

Take input the previously hidden state vector and the current input vector. 
Note that since the hidden state and current input are treated as vectors, each element in the vector is placed in a different dimension which is orthogonal to the other dimensions. Thus each element when multiplied by another element only gives a non-zero value when the elements involved are non-zero and the elements are in the same dimension.
Element-wise multiplies the hidden state vector by the hidden state weights and similarly performs the element-wise multiplication of the current input vector and the current input weights. This generates the parameterized hidden state vector and the current input vector. 
Note that weights for different vectors are stored in the trainable weight matrix.
Perform the vector addition of the two parameterized vectors and then calculate the element-wise hyperbolic tangent to generate the new hidden state vector.


During the training of the recurrent network, the network also generates an output at each time step. This output is used to train the network using gradient descent. 

![image](https://github.com/user-attachments/assets/44426e1d-5865-477a-952a-3af157cf57c8)






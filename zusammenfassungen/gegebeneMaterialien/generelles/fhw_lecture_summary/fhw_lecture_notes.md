# FH Wedel - Lecture notes

* Explorative Data Analysis: Teilgebiet der Statistik, untersucht & begutachtet Daten von denen nur ein gerringerres Wissen über deren Zusammenhänge vorliegt.
    * confirm / validate the data
    * discover correleations
    * spot anomalies (e.g. outliners)
    * frame hypothesis
    * check assumptions
    * prepare data 
    * visual explorations of the data
* substantive expertise
    * ability to ask good questions it requires domain knowledge (= Wissensgebiet)
* Data science is the intersection of hacking skills, math and statistics knowledge and substantive experience
    * answering questions with data for better action decisions

## Machine Learning 

### Intro
* Paradigm shift between traditional programming and machine learning: 
    * TP: Takes in Data and so called rules to determine the computation for the answers
    * ML: Takes in Data and Answers for predifined problems and computes the answers using a model
* Quite popular nowadays because of the stagnating storage, cpu and bandwidth costs
* Supervised vs. unsupervised learning
    * Supervised: Data needs to be labeled, training data contains both 
        * the input and the desired result (target)
        * construction of disting training- / dev- / testset of the data is critical
        * Supervised methods usually fast and accurate
        * Aim is generalization: predict the correct results with new, unseen data
    * Unsupervised: Data doesn't need to be labeled
        * Used for exploratory analysis (exploratory = untersuchend / Forschungs- / erforschend)
        * Aim is to find unknown underlying intrinisic structures (intrinsic = innewohnend / innere) of data (clusters)
    * Mixed machine learning types
        * semi-supervised: e.g. not all labels are known
        * reinforced: learning from consequences of action and reward

### Common ML techniques: 
* Regression analysis: How much / many?
* Classification: Is this A or B?
* Cluster analysis: Where does it belong to?
* Anomaly detection: is this weird?
* Recommender systems What's the next best thing?
* NLP / Text Mining: What does it mean?
* Association analysis: What goes with this?

### Linear regression
![linear regression](./img/01.png)
* Example: How much / many would a user spend on e.g. candy crush
* Popular algorithms: 
    * Linear regression
    * Polynomial regression
    * Ridge Regression
    * LASSO
    * Elastic Net
* Can be expressed with a linear function _y = f(x)_
* is a statistical ML method
* you can quantify and make forecasts (predictions) based on relationships between numerical variables
* **simple linear regression**: one predictor and one outcome (predicant)
* **multiple linear regression**: multiple predictors and one outcome (predicant)

### Cross validation
* The process to test the model on differen datasets and determine its' quality.
![corss validation](./img/04.png)
* **Training set**: a set of examples used for learning where the target value is known
* **Validation set**: a set of examples used to tune the architecture of a classifier and estimate the error
* **Test set**: used only to assess (= beurteilen) the performances of a classifier. It is never used during the training process so that the error on the test set provides an unbiased estimate of the generalization.

* **K-Fold**-cross validation: 
![k-fold cross validation](./img/05.png)

### ML - common problems
* **Overfitting**: Model performs well on the data used during training and poorly on new data.
![overfitting 1](./img/06.png)
![overfitting 2](./img/07.png)
* Solutions for overfitting: 
    * remove noise (outliners)
    * train with more data
    * reduce model complexity (features, polynomial degree, etc.)
    * add weight regularization
        * Given two explanations for something always take the simpler one!
        * Idea: Penalize large weights using penalties or constraints based on their squared values (L2 penalty) or absolute values (L1 penalty). 
    * try another algorithm
    * reduce ANNs (artificial neural networks) capacity
        * fewer hidden layer
        * fewer neurons per layer
        * adjust epochs & batch size
        * early stop
    * add dropout
        * Idea: remove conspiracy
![dropbout](./img/20.png)

### Hypothsis function
![Hypothsis function 1](./img/02.png)
![Hypothsis function 2](./img/03.png)
* Error (aka loss or cost) function: MSE - Mean Square Error
![cost function visualized](./img/08.png)

### Gradient descent
![gradient descent](./img/09.png)

### Cluster analysis
* Where does it belong to? How is it organized?
* Popular algorithms: 
    * k-Means
    * Fuzzy k-Means 
    * Hierarchical clustering
* Typical example: Image recognition (e.g. apple vs. pear)
* _Clustering is simple grouping things together according to similar features and attributes._
* Objective of clustering: 
    * Discover structures and patterns in high-dim. data.
    * Pragmatic (= sachbezogen) grouping of data with similar patterns
    * Clustering reduces the complexity and facilitates (= erleichern) interpretation

* **K-Means**: Steps
    * 1. Select the number of clusters you want to identify in your data. This is the _K_ in _K-Means clustering_. 
    * 2. Randomly select k distinct data points. (Initial clusters)
    * 3. Measure Measure the distance between the nth point and the generated initial clusters. 
    * 4. Assign the nth point to the nearest cluster.  
    * repeat steps 2 till 4 until every data point has been looked at.
    * 5. Calculate the mean (= Durchschnitt) of each cluster. 
    * We can assess the quality of the clustering by adding up the variation within each cluster
    * Since k-means clustering can't _see_ the best clustering, its only optionis to keep track of these clsuters, and their total variance, and dot the whole thing over again with different starting points.

![k-means clsutering 1](./img/10.png)
![k-means clsutering 2](./img/11.png)

* Conclusion: 
    * **Minimize with group variance** for tight clusters
    * **Maximize between group variance** for well sepearted clusters 

### Classification
* Question: Is this A or B?
* Classification is the process of taking some sort of input and assigning a label (aka category, class) to it.
    * Labels are discrete values (e.g. yes or no)
    * Example: Is this e-mail actually spam? Is the tumor malignant (cancer) or not? What kind of breed is that dog?
* Popular algorithms: 
    * k-nearest neighbors (kNN)
    * Decision trees
    * Logistic regression
    * naive Bayes
    * Support vector machines (SVN)
    * Artificial neural networks (ANN)
* deeply connected to the topic of big data.
* Distinction between _binary_ and _multiclass_ classification
    * **Binary**: clasification task with (binary, e.g. yes / no; 0 / 1) classes
    * **Multiclass**: classification task with more than two classes (classess are mutually exclusive)

* k-Nearest Neightbors (kNN):
* k-Nearest Neighbors (or k-NN) is a simple machine learning algorithm that categorizes an input by using its k nearest neighbors 
* steps: 
    * 1. Start with a dataset with known categories. The dataset needs to be already clustered. 
    * 2. Then we add a new data point with unknown category to the plot. 
    * 3. We classify the data point by looking at the nearest annotated points. (i.e. the _nearest neighbors_)
        * If the K is equal to 1, then we only use the nearest neighbor to define the category. 
        * With a larger K we pick the category with the most votes.

![k-Nearest neighbors](./img/12.png)  

## Statistics Types 
* Descreptive
    * Deal with the whole population
    * Describe & summarize the truth
    * Do not generalize
    * Do not make assumptions
* Inferential 
    * Deal with a subset of the population (sample)
    * Draw conclusion based on it (generalize)
    * Thus can neve be 100% accurate

## Logistic Regression
* Similar to linear regression but predicts whether something is **true** or **false** instead of predicting something continuous like _size_ (the way the linear regression does). 
* Also instead of fitting a line to the data, logistic regression fits an _S_ shaped _logistic function_.  
* Example: The curve tells you the probability that a mouse is obese based on its weight.

![logistic function](./img/13.png)  


## Neurons 
* Multiple input signals 
* Each signal gets a weight assigned
* The neuron then multplies the weights with the respective input signals
* apply an activation function to the summed signal of the synapses for binary classification
    * The activation function decides wheter a neuron should fire (activate / forward) his input signal or not. 
* Fun fact: A neural network with only one neuron is called _perceptor_. 

![neuron in a nutshell](./img/14.png)  

* The passing over of the signal from neuron to neuron is called **forward propagation**

### Normalization / Standardization
* It is quite important to normalize / standardize the input layer values
* Different kinds of activation functions

![activation function 1](./img/15.png)  
![activation function 2](./img/16.png)  
![activation function 3](./img/17.png)  
![activation function 4](./img/18.png)  
![activation function 5](./img/19.png)  

* It is possible to blend multiple activation functions in one nn
    * (put several af in one model)

### Backpropagation
* The backwards distribution of the cost is called _backpropagation_. 
* Once the derivatives have been claculated for all weights we can use them in _gradient descent_ to minimize _the cost_ and _train_ the neural network. 
* At its' essence backpropagation is just a clever application of the chain rule. <- Not really clear what this means. 
    * Whatch 3blue1brown video. 
* Multiple gradient descent algorithms, e.g.
    * Batch gradient descent
    * Stochastic gradient descent
    * Momentum
    * etc.
* NN automate the process of feature engineering


### Königsberger Bridge problem
* Graph theory started with this simple problem
    * As a pedestrian you want to pass each bridge exactly once
    * You end your tour at the exact spot from which it all started

### Recommender Systems
* What's the next best thing?
* Popular algorithms 
    * Content based recommender
    * Collaborative Filtering (user / item based)
    * Singular value decomposition (SVD)
* Content based recommender (aka context based recommender) first analyzes the nature of each item (e.g. by NLP TF/IDF etc.)
* Then recommends items similar to the given one
    * Pro: No cold start problem
    * Con: Over-specification, no improvement over time
* Collaborative Filtering (User based)
    * Collaborative Filtering try to find user who are look-a-like to a given one (based on their preferences, behaviour, etc.)
    * Pro:
        * Good results 
        * more discovery
        * improves over time
        * no initial content analysis
    * Con: 
        * new-user problem
        * cold-start problem
        * sparse (= dürftig) data
* Collaborative Filtering (Item based)
    * Item-item collaborative filtering (aka product association recommender)
    * refer to the fact that the taste of users remeins constant or change very slightly over time
    * once the recommender knows what user likes, it will offer him associated items
        * E.g. spotify discovery weekly
    * Pro: 
        * even better results
        * less suprise 
        * improves over time
        * no initial content analysis
    * Con: 
        * new-item problem
        * cold-start problem
        * sparse data


### Keras - The depplearning frontend
* A high-level framework for building neural networks with only a few lines of code
* written in python
* open source
* uses either TensorFlow (default) or Theano behind the scenes to do all its calculations
* build in industry practices
* optimized default settings
* build in pretrained models
    * e.g. for image recognition
* Theano vs. TensorFlow
    * Theano:
        * Works well with Python
        * GPU acceleration
    * TensorFlow:
        * GPU acceleration
        * distributed computing
* Keras vs. TensorFlow
    * Keras
        * high level
        * fast experimentation
        * less code
    * TensorFlow
        * low level
        * more control
        * more code




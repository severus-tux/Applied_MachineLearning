# Spam Filter
Testing different Machine Learning models for _Spam-Ham_ Classification 
## Models Implemented
* Logistic Regression
* Decision Tree
* Naive Bayes
* SVC
* Random Forest

_The following explaination tries to give an intution behind the working of a given model without dwelling into any mathematical rigour_

<hr>

### Logistic Regression

Logistic Regression is a type of classification algorithm involving a *linear discriminant*.

Unlike actual regression, logistic regression does not try to predict the value of a numeric variable given a set of inputs. Instead, the output is a probability that the given input point belongs to a certain class. For simplicity, lets assume that we have only two classes( there could also be multiple classes , such as "veg", "non-veg" & "vegan"), and the probability in question is **P>t** the probability that a certain data point belongs to the a class with probability greater than a threshold **t** (0.5 default). Thus, the output of Logistic Regression always lies in [0, 1] . ( [_click here to learn more about sigmoid functions_](https://developers.google.com/machine-learning/crash-course/logistic-regression/calculating-a-probability) )

The central premise of Logistic Regression is the assumption that your input space can be separated into two nice ‘regions’, one for each class, by a **linear** boundary. So what does a ‘linear’ boundary mean? For two dimensions, its a straight line- no curving. For three dimensions, its a plane. And so on. This boundary will ofcourse be decided by your input data and the learning algorithm. But for this to make sense, it is clear that the data points MUST be separable into the two aforementioned regions by a linear boundary. If your data points do satisfy this constraint, they are said to be linear-separable. Look at the image below.

<p align="center">
  <img src="https://i.stack.imgur.com/D8Yh0.png" title="linear seperation">
</p>

This dividing plane is called a **linear discriminant**, because 1. its linear in terms of its function, and 2. it helps the model ‘**discriminate**’ between points belonging to different classes.

_But how does Logistic Regression use this linear boundary to quantify the probability of a data point belonging to a certain class?_

First, lets try to understand the geometric implication of this ‘division’ of the input space into two distinct regions. Assuming two input variables for simplicity x1 and x2, the function corresponding to the boundary will be something like `**p + q.x1 + r.x2**`

Consider a point **(a, b)**. Plugging the values of  x1 and x2 into the boundary function, we will get its output **p + q.a + r.b**. Now depending on the location of (a, b), there are three possibilities to consider-

1. (a, b) lies in the region defined by points of the + class. As a result, **p + q.a + r.b** will be positive, lying somewhere in (0,∞). Mathematically, the higher the magnitude of this value, the greater is the distance between the point and the boundary. Intuitively speaking, the greater is the probability that (a, b) belongs to the + class. Therefore, **P** will lie in (0.5, 1].

2. (a, b) lies in the region defined by points of the - class. Now, **p + q.a + r.b** will be negative, lying in (-∞, 0). But like in the positive case, higher the absolute value of the function output, greater the probability that (a, b) belongs to the - class. **P** will now lie in [0, 0.5).

3. (a, b) lies ON the linear boundary. In this case, **p + q.a + r.b = 0**. This means that the model cannot really say whether (a, b) belongs to the + or - class. As a result, **P** will be exactly 0.5.

to change the boundry from (-∞,+∞ ) to [0.1] , we use a sigmoid function (or log-odds function).

<hr>

### Decision Tree

Decision Tree algorithm belongs to the family of **supervised learning** algorithms. Unlike other supervised learning algorithms, decision tree algorithm can be used for solving regression and **classification** problems too.

The general motive of using Decision Tree is to create a training model which can use to predict class or value of target variables by learning decision rules inferred from prior data(training data).


The understanding level of Decision Trees algorithm is so easy compared with other classification algorithms. The decision tree algorithm tries to solve the problem, by using tree representation. Each internal node of the tree corresponds to an attribute, and each leaf node corresponds to a class label.
Decision Tree Algorithm Pseudocode

  1. Place the best attribute of the dataset at the root of the tree.
  2. Split the training set into subsets. Subsets should be made in such a way that each subset contains data with the same value for an attribute.
  3. Repeat step 1 and step 2 on each subset until you find leaf nodes in all the branches of the tree.

<p align="center">
  <img src="https://i.stack.imgur.com/RoeXe.png" title="Decision Tree">
</p>

In decision trees, for predicting a class label for a record we start from the root of the tree. We compare the values of the root attribute with record’s attribute. On the basis of comparison, we follow the branch corresponding to that value and jump to the next node.

We continue comparing our record’s attribute values with other internal nodes of the tree until we reach a leaf node with predicted class value. As we know how the modeled decision tree can be used to predict the target class or the value. Now let’s understanding how we can create the decision tree model.

<hr>

### Naive Bayes

 		
The Naive Bayesian classifier is based on Bayes’ theorem with the independence assumptions between predictors. A Naive Bayesian model is easy to build, with no complicated iterative parameter estimation which makes it particularly useful for very large datasets. Despite its simplicity, the Naive Bayesian classifier often does surprisingly well and is widely used because it often outperforms more sophisticated classification methods. 

Bayes theorem provides a way of calculating the posterior probability, *P(c|x)*, from *P(c)*, *P(x)*, and *P(x|c)*. Naive Bayes classifier assume that the effect of the value of a predictor (x) on a given class (c) is independent of the values of other predictors. This assumption is called class conditional independence.

<p align="center">
  <img src="https://i.stack.imgur.com/BzMwG.png" title="Bayes Thm">
</p>

Where

  *  P(c|x) is the posterior probability of class (target) given predictor (attribute). 
  *  P(c) is the prior probability of class. 
  *  P(x|c) is the likelihood which is the probability of predictor given class. 
  *  P(x) is the prior probability of predictor.

<hr>

### SVC

“Support Vector Machine” (SVM) is a supervised machine learning algorithm which can be used for both classification or regression challenges. However,  it is mostly used in classification problems. In this algorithm, we plot each data item as a point in n-dimensional space (where n is number of features you have) with the value of each feature being the value of a particular coordinate. Then, we perform classification by finding the hyper-plane that differentiate the two classes very well (look at the below snapshot).


<p align="center">
  <img src="https://i.stack.imgur.com/KgIs2.png" title="SVC">
</p>

Support Vectors are simply the co-ordinates of individual observation. Support Vector Machine is a frontier which best segregates the two classes (hyper-plane/ line).

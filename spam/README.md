# Spam Filter
Testing different Machine Learning models for _Spam-Ham_ Classification 
## Models Implemented
* Logistic Regression
* Decision Tree
* Naive Bayes
* SVC
* Random Forest

_The following explaination tries to give an intution behind the working of a given model without dwelling into any mathematical rigour_

### Logistic Regression
Logistic Regression is a type of classification algorithm involving a *linear discriminant*.

Unlike actual regression, logistic regression does not try to predict the value of a numeric variable given a set of inputs. Instead, the output is a probability that the given input point belongs to a certain class. For simplicity, lets assume that we have only two classes( there could also be multiple classes , such as "veg", "non-veg" & "vegan"), and the probability in question is **P>t** the probability that a certain data point belongs to the a class with probability greater than a threshold **t** (0.5 default). Thus, the output of Logistic Regression always lies in [0, 1] . ( [_click here to learn more about sigmoid functions_](https://developers.google.com/machine-learning/crash-course/logistic-regression/calculating-a-probability) )

The central premise of Logistic Regression is the assumption that your input space can be separated into two nice ‘regions’, one for each class, by a **linear** boundary. So what does a ‘linear’ boundary mean? For two dimensions, its a straight line- no curving. For three dimensions, its a plane. And so on. This boundary will ofcourse be decided by your input data and the learning algorithm. But for this to make sense, it is clear that the data points MUST be separable into the two aforementioned regions by a linear boundary. If your data points do satisfy this constraint, they are said to be linear-separable. Look at the image below.

<p align="center">
  <img src="https://i.stack.imgur.com/D8Yh0.png" title="linear seperation">
</p>

This dividing plane is called a **linear discriminant**, because 1. its linear in terms of its function, and 2. it helps the model ‘**discriminate**’ between points belonging to different classes.


_But how does Logistic Regression use this linear boundary to quantify the probability of a data point belonging to a certain class?_


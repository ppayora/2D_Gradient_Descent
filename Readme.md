# Description

This project is the first part of SMM284 An introduction to machine learning 2019 CASS Business School. The goal of this project is to create a 2D gradient descent class, try to optimize the fucntion, and draw a conclusion on the effect of each hyperparameter with the result. Three techniques being used are 1. Plain Vanilla 2. Momentum 3. Nesterov and the function that is being tested is SIX-HUMP CAMEL

## Why is gradient descent so important in machine learning

Gradient descent is an important because every machine learning algorithms have their own cost function. Cost function is a function that measure how well the model perform.The lower it's the better.Therefore,we try to minimize so that the model have as much predictive power as possible.

###Plain Vanilla Gradient descent

Plain Vanilla GD works by moving against the direction of gradient at the initial point of the function until the magnitude of gradient is within limited tolerance

Two modifications on Vanilla gradient descent

### Stochastic Gradient Descent

This method instead of using entire data set before moving by a step size(learning rate) uses one set of independent variables to update its parameters which is appropriate for big data.

Application :

Online learning where there is a continuous stream of data.
Map reduce and data parallelism
Product search
Mini Batch Gradient Descent.

This method modify is different from gradient descent by instead of using just one dataset to minimize the cost function. it uses 2-100 datasets to update the parameter. Minibatch technique tends to work faster because of the vectorization in computation.

http://www.sfu.ca/~ssurjano/camel6.html

Six-Hump Camel Fucntion

$$f(x) = (4-2.1x_1^2 +\frac{x_1^4}{3})x_1^2 +x_1x_2 + (-4+4x_2^2)x_2^2$$
Result Discussion
### Number of iteration vs Learning rate

Generally, the number of iteration tend to decrease when the learning rate increase. However, when the learning rate is too high, the loss function can explod because it moves to the very steep region. 

![Plain_GD](https://user-images.githubusercontent.com/52139322/60985380-4fdd2d00-a335-11e9-809d-d05c60f30c6d.png)
![Plain_GD_path](https://user-images.githubusercontent.com/52139322/60985383-510e5a00-a335-11e9-989c-2218a3971db5.png)


### Momentum and Nesterov

Problem of Gradient Descent

Slow when gradient is constantly small
Follow wrong path in Noisy gradient
Particulary for this function if the learning rate is too high the magnitude of gradient is going to explode because it's very flat at the bottom and very steep on the side.

#### Solution: 
Use the learning rate decay which decrease the learning rate every n steps which generally do better. Momentum and Nesterov allows me to increase the learning rate more than 10 times.

Momentum allows to tune for the higher learning rate(with learning rate decay)
### Momentum

![Momentum_GD](https://user-images.githubusercontent.com/52139322/60985374-4c49a600-a335-11e9-8a38-5d7557d48cdc.png)
![Momentum_GD_path](https://user-images.githubusercontent.com/52139322/60985362-481d8880-a335-11e9-9c59-920a94b26983.png)

### Nesterov

![Nesterov_GD](https://user-images.githubusercontent.com/52139322/60984025-e52af200-a332-11e9-82f3-5387e27644fb.png)
![Nesterov_GD_path](https://user-images.githubusercontent.com/52139322/60985357-45bb2e80-a335-11e9-9a11-53752bd750d8.png)

# Conclusion

Momentum and Nesterov generally allows for a faster learning rate because momentum take the accumulated gradient into account while Nesterov look ahead. But for this function there is weird behaviour because momentum and Nesterov suppose to smoothen the functional path however Plain Vanilla did better for this function but with lower maximum learning rate. My hypothesis is that there are 2 minimum points and symmetry so the algorithm might confuse.

ref: https://towardsdatascience.com/learning-rate-schedules-and-adaptive-learning-rate-methods-for-deep-learning-2c8f433990d1

Further Improvement
Try different active learning rate technique
Try different gradient descent technique

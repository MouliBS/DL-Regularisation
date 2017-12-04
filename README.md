Week 3 Quiz - Shallow Neural Networks


qs 1 Which of the following are true? (Check all that apply.)

X is a matrix in which each column is one training example.

a^[2]_4 is the activation output by the 4th neuron of the 2nd layer

a^[2](12) denotes the activation vector of the 2nd layer for the 12th training example.

a^[2] denotes the activation vector of the 2nd layer.


qs 2 The tanh activation usually works better than sigmoid activation function for hidden units because the mean of its output is closer to zero, and so it centers the data better for the next layer. True/False?

True

qs 3 Which of these is a correct vectorized implementation of forward propagation for layer l, where 1≤l≤L?

Z[l]=W[l]A[l−1]+b[l]
A[l]=g[l](Z[l])


qs 4 You are building a binary classifier for recognizing cucumbers (y=1) vs. watermelons (y=0). Which one of these activation functions would you recommend using for the output layer?

sigmoid
Sigmoid outputs a value between 0 and 1 which makes it a very good choice for binary classification. You can classify as 0 if the output is less than 0.5 and classify as 1 if the output is more than 0.5. It can be done with tanh as well but it is less convenient as the output is between -1 and 1.


qs 5Consider the following code:

A = np.random.randn(4,3)
B = np.sum(A, axis = 1, keepdims = True)
print(B)
B.shape
[[ 1.00796631]
 [ 0.9067746 ]
 [-1.6589113 ]
 [-0.57905721]]

Out[6]: (4, 1)

we use (keepdims = True) to make sure that A.shape is (4,1) and not (4, ). It makes our code more rigorous.


Qs 6: Suppose you have built a neural network. You decide to initialize the weights and biases to be zero. Which of the following statements is true?

True :  Each neuron in the first hidden layer will perform the same computation. So even after multiple iterations of gradient descent each neuron in the layer will be computing the same thing as other neurons.

False: Each neuron in the first hidden layer will perform the same computation in the first iteration. But after one iteration of gradient descent they will learn to compute different things because we have “broken symmetry”.

False: Each neuron in the first hidden layer will compute the same thing, but neurons in different layers will compute different things, thus we have accomplished “symmetry breaking” as described in lecture.

False: The first hidden layer’s neurons will perform different computations from each other even in the first iteration; their parameters will thus keep evolving in their own way.


Qs 7 Logistic regression’s weights w should be initialized randomly rather than to all zeros, because if you initialize to all zeros, then logistic regression will fail to learn a useful decision boundary because it will fail to “break symmetry”, True/False?

False

Logistic Regression doesn't have a hidden layer. If initialize the weights to 0, the first example x fed in the logistic regression will output zero but the derivatives of the Logistic Regression depend on the input x (because there's no hidden layer) which is not zero. So at the second iteration, the weights values follow x's distribution and are different from each other if x is not a constant vector.

Qs 8: You have built a network using the tanh activation for all the hidden units. You initialize the weights to relative large values, using np.random.randn(..,..)*1000. What will happen?

It doesn’t matter. So long as you initialize the weights randomly gradient descent is not affected by whether the weights are large or small.

This will cause the inputs of the tanh to also be very large, causing the units to be “highly activated” and thus speed up learning compared to if the weights had to start from small values.

This will cause the inputs of the tanh to also be very large, thus causing gradients to be close to zero. The optimization algorithm will thus become slow.

True:
This will cause the inputs of the tanh to also be very large, thus causing gradients to also become large. You therefore have to set α to be very small to prevent divergence; this will slow down learning.


Qs9  Consider the following 1 hidden layer neural network:


Which of the following statements are True? (Check all that apply).

https://user-images.githubusercontent.com/14886380/29200515-7fdd1548-7e88-11e7-9d05-0878fe96bcfa.png

b[1] will have shape (4, 1)
W[1] will have shape (4, 2)
W[2] will have shape (1, 4)
b[2] will have shape (1, 1)



Qs 10 In the same network as the previous question, what are the dimensions of Z[1] and A[1]?

True: Z[1] and A[1] are (4,m)

Z[1] and A[1] are (4,1)

Z[1] and A[1] are (4,2)

Z[1] and A[1] are (1,4)

formula: A[1] =g(Z[1]) g is the activation function












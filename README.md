# [DLAI21 projects] BASED SQRT LEARNABLE ACTIVATION FUNCTION

**Where I started:** Why ReLU? Can we get better? Can we get better in accuracy
and in computational complexity?

Meanwhile I am studying linearity and non-linearity I asked myself “how much
Non-linearity a DNN needs to learn good function approximation?”

Next, I tried to remove, half and double the number of activation function in
networks, I noted that performances of the models are getting worse if the
number of activations is too small or too large.

**Finding the right number of function activation seems to me an optimization
problem!**

After some research I found some interesting papers:

- X. Yang, Y. Chen and H. Liang, "Square Root Based Activation Function in
    Neural Networks," 2018 International Conference on Audio, Language and
    Image Processing (ICALIP), 2018, pp. 84-89, doi:
    10.1109/ICALIP.2018.8455590.
- Mohit Goyal, Rajan Goyal, & Brejesh Lall. (2020). Learning Activation
    Functions: A new paradigm for understanding Neural Networks.

After I have implemented “Square Root
Based Activation Function in Neural
Networks” on PyTorch I’ve noticed (as the
paper said) in some environments that
activation function worked better than ReLU

Question: **the paper made a comparison between identical networks replacing
activation functions, but what if we choose the right number of applications of
the activation function(or, what if we choose the right quantity of non-
linearity)?**

Found the question found the problem, we can have only a integer as number of
application of function activation (we cannot apply ReLU 1.5 times).


The second paper bring a new idea for function activation, Learnable/Trainable
function activation.

```
In this paper they are using Taylor
Polynomial Basis as function activation,
assigning to each factor of Taylor a
multiplicative factor than can be trained
with gradient descent. Proving that
trainable activation function can perform
better than classical one in some
environments.
```
**Idea: Using a generalization of SQRT- activation function**


**The idea is leading to backpropagation optimization choose how much each
activation function has to be non-linear. Indeed, more z is near to 1 , more
the function is similar to a linear activation function.**


**Project proposal:**

```
Investigate if this idea can be useful, make comparison between ReLU
based network and the new trainable sqrt-based function activation
through some classification (es: cifar 10 , mnist and image net) and
regression problem.
Using plain fully-connected, plain convolution and resnet networks.
Investigate how this approach interacts with dropout and batch
normalization and skip connections.
Comparison between function activations based on entropy of data after
their application.
```
Evaluating vanishing/exploding gradient with new activation.

Risks:

- The new activation function can not lead to network converge. Changing
    the activation function at each back propagation cannot lead the time to
    the network to adapt and learn. Possible solution can be some constrains
    on z (max value, min value or a sort of normalization on z).
- Connected to previous point the error is going to be too small, or the error
    is going to explode.


- The computational time is too high in respect to ReLU time and possible
    performance gain is not enough: can be perform better in respect to
    number of epochs but not in respect to time training.



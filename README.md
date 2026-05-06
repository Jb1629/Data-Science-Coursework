# Data-Science-Coursework
Coursework for past project research
Testing certain machine learning algorithms that are not accustomed for input from images.
Instead of CNN I used Support Vector Machines and Fully Connected Neural Networks. (SVM, FCNN)

SVM:
The data moves along a diagonal trend, indicating that the
original features have strong correlation with each other, where the colors in ground truth represent the actual class
and our model predicting the class to be of a different label for most of the time. When PCA is applied, there are less
features to work with (around 90 instead of 3072) and the data makes the model less informative on what the object
predicted in the image is, reducing accuracy in some outputs. Due to the overlapping of classes thereby making it
harder for the model to determine what is a true label. In our confusion matrix that is outputted, darker colors that
are thus represented as labels 0 and 51 for example were very accurate in prediction, but for the surrounding area of
the matrix, there is some misclassification in the labels, such as label (51, 96). Yet for the most part it predicts the
greatest SVM can perform in this instance.

FCNN:
We ran multiple tests, changing the learning rate greatly, using Relu instead of Leaky Relu, changing
batch size and more. After careful analysis we saw that some of the data was being construed by the number of
layers as well as the number of neurons too hence why we made it 1024 for each layer. Increasing the batch size
from 32 to 64 greatly increased the accuracy of the model because it allowed it to forwardly and backwardly
propagate through the network with more passes, which allowed the model to increase connections with patterns but
also increased the time complexity, making it 𝑂(𝑁^2) time complexity where N is the total number of weights in the
network. This is due to forward propagation of our network performing one multiplication and one addition
operation each time.[8]. Upon looking at the training and validation accuracy, we can also see that validation
accuracy on the right separates which could be a sign of close overfitting if the number of epochs increased hence
why we kept around the 50-60 epoch mark.

When evaluating the convolution matrix, we created a truth table to see what it was predicting correctly. We can see
that in the top left corner, over 9k samples are True Negative (TN), in the top right corner over 20 were False
Positive (FP), since we are testing over class 0. One may imply that the model performs well specifically for class 0
due to high true negatives and few false positives. However, we can see it struggles with identifying all instances of
class 0 since we have 53 false negatives. There is indeed a possibility that perhaps class 0 may be underrepresented
or cannot distinguish properly between certain classes, that comes down to a multitude of reasons and even the
algorithm itself, which was the purpose of our experiment.

# Multilayer-Perceptron-on-EMNIST-Dataset
Libraries
For this project you will need network.py, network2.py, and mnist_loader.py from the Nielsen book. This code requires NumPy.
You will also need the Matplotlib library to visualize data; see the fig/ subdirectory for the code used to generate the plots in the textbook.
You will also need SciPy in order to load the dataset. This may already have been installed along with NumPy.

Dataset
While synthetic data can be useful for experiments, you are no doubt looking forward to working with some real data. In order to build on the work done so far in the textbook, we will adopt a subset of the Extended MNIST or EMNIST dataset.
EMNIST expands on the original MNIST data, adding handwritten letters as well as additional samples of handwritten digits. There are several “splits” of the data by various characteristics. We will be using the “EMNIST Letters” dataset, which contains data split into 26 classes, one for each letter in the English alphabet.
Download the Matlab format dataset and extract matlab/emnist-letters.mat. This file can be opened by scipy.io.loadmat(), but you will need some guidance in figuring out how to navigate the structure. See this answer on StackOverflow for details on retrieving the training, validation, and test sets.
Tip: The data['mapping'] field maps from class numbers to ASCII codes of the corresponding letters. For example, class 1 maps to ASCII codes 65 and 97 ('A' and 'a').

Preprocessing
Once you have extracted the appropriate data from the file in Matlab format, you will need to save it in a format compatible with Nielsen’s code. Create two items:
A gzip-compressed pickle archive file emnist.pkl.gz of the training, validation, and test data. See mnist_loader.py for details of the file format.
A module emnist_loader.py implementing the same interface as mnist_loader.py.
Tip: see src/expand_mnist.py for an example of creating a .pkl.gz file, but note that cPickle is a Python 2.7 module whose functionality has been subsumed by pickle.

Viewing images
In order to verify that the data has been loaded correctly, try plotting some of the images in the dataset. See fig/mnist.py for reference, but keep in mind that the code is for Python 2.7.
Creating and testing a Multilayer Perceptron (Feedforward neural network)
Use the code in network.py to create and test a network with one hidden layer similar to the MLP developed in Chapters 1 and 2 of the Nielsen text. You will need to decide on an appropriate number of hidden neurons for the network. Keep in mind that
There are 26 classes rather than 10, so you will likely need more hidden neurons than the network for recognizing digits.
In addition to having more classes, the EMNIST Letters data mixes upper- and lowercase letters within each class, so even with enough neurons in the hidden layer, your accuracy is likely to be lower.  See the details in the EMNIST paper for the kind of performance you might reasonably expect.

Improving the network
Use the techniques given in the Nielsen book and their implementations in network2.py and tune their hyperparameters to obtain the highest accuracy you can on the validation set.

Tips
See How to choose a neural network's hyper-parameters? for advice on strategy and workflow.

Plot graphs of the cost and accuracy on the training and validation sets, and use that information to guide your tuning, See the fig/ subdirectory for examples.
When finished, evaluate your results on the test set. Compare the performance on the test set with your original network.

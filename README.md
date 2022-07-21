# Instrument detector
An detector of instruments in a photo

## IMAGE RECOGNISER FOR THE DETECTION OF AN INSTRUMENT
By Galo Pérez Gallego

This project was done in order to test my skills learned in the Jovian course "Deep Learning with PyTorch: Zero to GANs"

The content of this repository includes test images such as "piano.jpg" and "violin.jpg" and the notebook where the neural network is developed "instruments-detector.pynb".

The neural network that is developed in the notebook "instruments_detector.pynb" is trained for detecting the instrument that is passed as an image at the input of the network. The dataset used can be downloaded at: https://www.kaggle.com/datasets/gpiosenka/musical-instruments-image-classification

 There are 30 classes (30 different instruments) that the model can detect: 'acordian', 'alphorn', 'bagpipes', 'banjo', 'bongo drum', 'casaba', 'castanets', 'clarinet', 'clavichord', 'concertina', 'Didgeridoo', 'drums', 'dulcimer', 'flute', 'guiro', 'guitar', 'harmonica', 'harp', 'marakas', 'ocarina', 'piano', 'saxaphone', 'sitar', 'steel drum', 'Tambourine', 'trombone', 'trumpet', 'tuba', 'violin', 'Xylophone'.
 
 I reached over 98% accuracy using a pre-trained model named ResNet50 and some techniques in order to improve it and avoid overfitting:
 
 - **Dropout**: Dropout is a technique that drops neurons from the neural network or ‘ignores’ them during training, in other words, different neurons are removed from the network on a temporary basis. 
 
 - **Learning rate scheduling**: Instead of using a fixed learning rate, we will use a learning rate scheduler, which will change the learning rate after every batch of training. There are many strategies for varying the learning rate during training, and the one I'll use is called the "One Cycle Learning Rate Policy", which involves starting with a low learning rate, gradually increasing it batch-by-batch to a high learning rate for about 30% of epochs, then gradually decreasing it to a very low value for the remaining epochs.

- **Weight decay**: We also use weight decay, which is yet another regularization technique which prevents the weights from becoming too large by adding an additional term to the loss function.

- **Gradient clipping**: Apart from the layer weights and outputs, it also helpful to limit the values of gradients to a small range to prevent undesirable changes in parameters due to large gradient values.

For the correct reproduction of the training of this network and then to be able to put it to the test, you will need to download the dataset specified in the previous link (227.69 MiB are required). One way to execute this is by uploading the notebook "instruments-detector.pynb" to the cloud, such as Colab or Amazon Web Services. We must also upload the dataset and separate images to make predictions, such as "flute.jpg" (photo of a flute) and "violin.jpg" (photo of a violin). 

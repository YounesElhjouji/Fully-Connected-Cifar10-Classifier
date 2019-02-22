# Fully-Connected-Cifar10-Classifier

A fully-connected classifier for the CIFAR-10 dataset programmed using TensorFlow and Keras. Fully-connected networks are **not** the best approach to image classification. However, this project is a part of a series of projects that serve to incrementally familiarize myself with Deep Learning. 

I do use ConvNets to train a cat-dog classifier in a different repository.

## Hyperparameters Used
```
epochs = 30
nodes_per_layer = [1024,512,256,128,64]
batch_size = 64
dropout_rate = 0.3
activation=tf.nn.relu
optimizer=tf.train.AdamOptimizer(0.001)
loss='sparse_categorical_crossentropy'
metrics=['accuracy']
```

## Most Important Takeaway from the Project

### On the one hand
Training using the unaugmented data set wuickly results in overfitting
### On the other hand 
Using the augmented data set right away causes undefitting
### Therefore 
The best approach that I came up with is to train using unaugmented data first until that results in overfitting and then to switch to augmented data. The model has less of a hard time training on augmented data because it has already leared many of the main features of the classes before data augmentation makes learning harder but less prone to overfitting.

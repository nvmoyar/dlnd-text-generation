# dlnd_tv_script_generation

Use of RNNs to build a TV script using 'Simpsons by the data' dataset from Kaggle. 

Initially in this project, it is generated an own Simpsons TV scripts using RNNs. The Neural Network will generate a new TV script for a scene at Moe's Tavern.
However for experimenting purposes, the whole dataset has been used for training in order to get a more sensical script, with
no success. It can be found some scripts for different characters -still nonsensical- saved as html files, and different epochs. 

Two jupyter notebooks can be found:

** simpsons_dataset_preparation.ipynb --> the additional operations to prepare a txt with the whole The Simpsons Dataset from Kaggle. 

** dlnd_tv_script_generation.ipynb --> the NN model and training

NN model: 

* lookup table
* tokenize
* word embedding 
* batch generation
* optimising (AdamOptimizer)
* gradient clipping

## Requirements

FloydHub is a platform for training and deploying deep learning models in the cloud. It removes the hassle of launching your own cloud instances and configuring the environment. For example, FloydHub will automatically set up an AWS instance with TensorFlow, the entire Python data science toolkit, and a GPU. Then you can run your scripts or Jupyter notebooks on the instance. 
For this project: 

> floyd run --mode jupyter --gpu --env tensorflow-1.0

You can see your instance in the list is running and has ID XXXXXXXXXXXXXXXXXXXXXX. So you can stop this instance with floyd stop XXXXXXXXXXXXXXXXXXXXXX. Also, if you want more information about that instance, use floyd info XXXXXXXXXXXXXXXXXXXXXX

### Environments

FloydHub comes with a bunch of popular deep learning frameworks such as TensorFlow, Keras, Caffe, Torch, etc. You can specify which framework you want to use by setting the environment. Here's the list of environments FloydHub has available, with more to come!

### Datasets 

With FloydHub, you are uploading data from your machine to their remote instance. It's a really bad idea to upload large datasets like CIFAR along with your scripts. Instead, you should always download the data on the FloydHub instance instead of uploading it from your machine.

> floyd run "python train.py" --data diSgciLH4WA7HpcHNasP9j

Here, diSgciLH4WA7HpcHNasP9j is the ID for this dataset, you can get IDs for other data sets from the list linked above. The dataset will be available at /input. So, the CIFAR10 data will be in /input/CIFAR10.

### Output
Often you'll be writing data out, things like TensorFlow checkpoints. Or, updated notebooks. To get these files, you can get links to the data with:

> floyd output run_ID

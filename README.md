# StoBatch
Code for paper "Scalable Differential Privacy with Certified Robustness in Adversarial Learning" in ICML2020.

# Requirements:
Python 3.x (tested with 3.5.2)
Tensorflow (1.x, tested on 1.15.0), numpy, scipy, imageio
An early (compatible) version of Cleverhans library is included
GPU with at least 11GB of memory, better to have at least 4 GPUs
Script should download the CIFAR10 automatically, if the dataset is not there
Raw TinyImageNet dataset https://tiny-imagenet.herokuapp.com/
Pretrained weight of resnet-18 ("resnet18_imagenet_1000_no_top.h5") from: https://github.com/qubvel/classification_models/releases/download/0.0.1/resnet18_imagenet_1000_no_top.h5

# How it works:
For centralized MNIST and CIFAR-10: python3 StoBatch.py. The parameters can be finetuned in the main python file: StoBatch.py

For StoBatch with CIFAR10, run "StoBatch_cifar10.py" to train the model, run "StoBatch_cifar10_testing.py" to test.
Things to change before running: GPU settings, path to checkpoints, path to results.

For StoBatch with Tiny ImageNet:
Before running the training script, you can run the "tinyimagenet_read.py" to generate the pre-packed dataset (normalized and augmented). You need to change the path to data in that script. By default we use 30 out of 200 classes in the TinyImageNet.
    For StoBatch with TinyImageNet, run "StoBatch_resnet_pretrain.py" to train the model, run "StoBatch_resnet_pretrain_testing.py" to test.
    For SecureSGD (baseline method), run "SecureSGD_resnet_pretrain.py" to train the model, run "SecureSGD_resnet_pretrain_testing.py" to test.
    Things you need to change before running: 
        GPU settings (according to your own GPU setup)
        path to data
        path to checkpoints
    Things you can change (if you know it is necessary):
        Settings for training and testing
        The weight mapping in: resnet18_weight_table_enc_layer.txt

About the "parameter_settings.txt":
    This described the core parameters we used in the code. How the parameters were defined in the code was kind of messy, so I made a summary there.


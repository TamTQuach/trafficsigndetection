## Traffic Sign Classification

![title](images/title.png)



Background and scope of work:

    Traffic signs provide critical information drivers, which in turn requires them to adjust their driving behavior to make sure they follow with whatever road regulation currently enforced. Autonomous vehicles must also recognize and understand traffic signs to follow abide by road legislation.
    I will build a convolutional neural network to classify traffic signs


DataSet 

    The dataset that will be used in this project is traffic sign dataset downloaded from from Laboratory for Intelligent & Safe Automobiles (LISA)
    7840 rgb images-divided into 4 classes
    Sign sizes from 6x6 to 168x168 pixels.

<p align="center" >
  <img src="images/eda2.png" width="400">
</p>
<p align="center" >
  <img src="images/eda3.png" width="400">
</p>


Dataset pipeline:

    Rescale images to 32 x 32 x 1 (grayscale) 
    Split dataset into 80/20 train-validatation
    Batch size = 32

<p align="center" >
  <img src="images/eda1.png" width="400">
</p>

Build simple 3 layers CNN:

<p align="center" >
  <img src="images/cnn-graph.png" width="800">
</p>

<p align="center" >
  <img src="images/Training-Validation.png" width="800">
</p>
The test accuracy is about 55%
<p align="center" >
  <img src="images/cfmatrix.png" width="800">
</p>

Using Transfer Learning:


    -Import base Xception model from Keras without last layer
    -Adding the last layer:
        +Adding GlobalAveragePooling2D
        +Adding activation 'relu'
        +Adding dropout rate .5
        +change number of classes to 4
    -Retrain dataset with different image size (299,299,3) and in rgb , with 5 epochs

    <p align="center" >
  <img src="images/diagram.png" width="800">
</p>

    <p align="center" >
  <img src="images/transferlearningcf.png" width="800">
</p>


# -Image-Retrieval-from-Feature-Maps
In this project, we use deconvolution layers to visualize the extracted features of different layers of AlxNet.
<br>
<br>
__Data Set__:
<br>
We use the tiny ImageNet data set.
<br>
<br>
__Model__:
<br>
First, load the pre-trained Alexnet model and separate the conv(convolution) and fc(fully connected) layers. 
L is the desired layer number to separate as input (it should be 2, 5, 8) if l<6, that means the desired layer is conv, so two layers after the 1th conv layer 
We put it as a whole (the two layers of relu and pooling should also be considered after conv). If l ≥ 6, it means the desired layer is fc. Therefore, for fc layers, we take up to one layer after l.
<br>
Conv2: we use 4 deconv layers.
<br>
Conv5: we use 6 deconv layers.
<br>
fc8: we use 3 fully connected and 5 deconv layers.
<br>
<br>
__Training__:
<br>
We use Optimizer: Adam and Loss: L2 in all three models. The more similar the output and input images are, 
the closer the corresponding pixels in the two images are to each other, and as a result, they have less L2 loss.
We make conv2, conv5, fc8 networks 10, 15, 20 epoch respectively. We also take batch size: 128.


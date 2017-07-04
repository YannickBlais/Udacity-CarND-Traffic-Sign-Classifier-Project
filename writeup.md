# **Traffic Sign Classifier** 

---

**Dataset Exploraton**
* The dataset used for training, validation and testing is the one provided by the zipped file provided by Udacity: traffic-signs-data.zip
* All sub-sets include small imagelets containing a single traffic sign 28x28 image.
* Exploratory Visualization -> See Traffic_Sign_Classifier.ipynb, "Include an exploratory visualization of the dataset" section

**Design and Test a Model Architecture**
* The preprocessing consists of image normalization, i.e. with mean of zero and unit norm => pixel values ranging between -1.0 and +1.0. This technique is of course useful to help Tensorflow converge faster.
* The Model Architecture is of course similar to LeNet architecture. The modifications I brought to this model are
&nbsp;&nbsp;&nbsp;&nbsp;1- Doubling the number of features calculated at every convolutional layer. Therefore the first convolutional layer uses a [5x5] kernel with a depth of 3 as input and a depth of 12 in output. Same goes for the second convolutional layer which uses a [5x5] kernel with a depth of 12 in input and 32 in output.
&nbsp;&nbsp;&nbsp;&nbsp;2- Expansion of the fully connected layers with the first layer having 800 inputs, 240 outputs and the second layer having 240 inputs and 168 outputs.
&nbsp;&nbsp;&nbsp;&nbsp;3- Perform dropout at the fully connected layer, using 0.5 as keep probability during training and 1.0 during evaluation
* Model Training
&nbsp;&nbsp;&nbsp;&nbsp;1- Optimizer used: The original AdamOptimizer is used, since training converges relatively quickly and using a different optimizer didn't seem to change much in my case anyway, I left it as is.
&nbsp;&nbsp;&nbsp;&nbsp;2- Batch size: Depending on my tests, I tested with batch sizes of 128 and 256. Finally a batch of 256 was optimum in my case.
&nbsp;&nbsp;&nbsp;&nbsp;3- Number of Epoch: I found that 10 epochs was a bit small in some cases, especially when making the learning rate smaller. I found that at least 15 was better to see the training converge.
&nbsp;&nbsp;&nbsp;&nbsp;4- Other hyperparameters: tf.truncated_normal uses a mu of 0 and sigma of 0.1 and learning rate is left at 0.001
* The approach I used to obtain the 0.93 or greater was simply to test methods that we learned from previous lessons. The first method I used was dropout but was not enough. The second method I used is the one described in the model architecture which is to expand the different layers. That was enough to reach that score.

**Test a Model on New Images**
* The new images found on the Internet are shown in the .ipynb file, at the "Load and Output the Images" section. The images are not actually aprticularly difficult except maybe for the roundabout signt that is tilted and had some website info on top of it.
* The final result is 100%, meaning that all signs were classified correctly. The test set had a performance of XXX%.
* 

# **Traffic Sign Classifier** 

---

**Dataset Exploraton**
* The dataset used for training, validation and testing is the one provided by the zipped file provided by Udacity: traffic-signs-data.zip
* All sub-sets include small imagelets containing a single traffic sign 28x28 image.
* Exploratory Visualization -> See Traffic_Sign_Classifier.ipynb, "Include an exploratory visualization of the dataset" section

**Design and Test a Model Architecture**
* The preprocessing consists of image normalization, i.e. with mean of zero and unit norm => pixel values ranging between -1.0 and +1.0. This technique is of course useful to help Tensorflow converge faster.
* 

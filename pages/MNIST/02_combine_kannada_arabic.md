## MNIST Digit Classification ([Repo](https://github.com/JamesDargan/MNIST){:target="\_blank"})

**Project Description:**
I combine the Arabic handwritten digits data with Kannada handwritten digits hosted on Kaggle to double the number of categories to predict. I then step-by-step test and optimize each layer component of a CNN architecture. My final model predicts all 20 digits with 98.692% test accuracy. I then explore errors introduced by confusion of digits from different languages. [NB](https://github.com/JamesDargan/MNIST/blob/master/code/Compare_Arabic_Kannada.ipynb){:target="\_blank"}
<br><br>

**Optimize Convolution Filter Count at 32-64**
<img src="compare_assets/NN_filter_structure.png?raw=true"/>

**Determine Sufficient Dense Layer Size of 128**
<img src="compare_assets/NN_dense_size.png?raw=true"/>

**Optimize Dropout at 30% at each Layer**
<img src="compare_assets/NN_dropout_rate.png?raw=true"/>


**Insight 1:**
Stacking convolution layers and utilizing convolution with stride in place of max pooling do not improve performance. Traditional single-layer convolution of appropriate size with a MaxPooling layer performs sufficient.

**Insight 2:**
About 28% of all prediction errors in my test data due to similarity of handwritten digit to those of the other language. For example, the single greatest error in classifying Arabic digits came from confusion with the Kannada 0, with a total of 19 false predictions from the test data.

<img src="compare_assets/arab_misclass_as_kan.png?raw=true"/>


**Insight 3:**
Despite visual similarity of curves in the Kannada digits, my CNN performs better on Kannada digits than Arabic digits, as measured by Precision, Recall, and Accuracy.

<img src="compare_assets/Score_compare.png?raw=true"/>

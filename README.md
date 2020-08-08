# Covid-19-chest-x-ray-detection
![COVID-19](https://github.com/akhiilkasare/Covid-19-chest-x-ray-detection/blob/master/Images/Covid-19-India-and-crisis-communication-1280x720.jpg)

This is the data repository for the 2019 Novel Coronavirus Visual Dashboard operated by the Johns Hopkins University Center for Systems Science and Engineering (JHU CSSE). Also, Supported by ESRI Living Atlas Team and the Johns Hopkins University Applied Physics Lab (JHU APL).

### Clinical
COVID-19 usually presents with fever (85%), cough (70%) and shortness of breath (43%), but abdominal and other symptoms are possible and the disease can be asymptomatic.
Overal mortality rate is 2.3% in some series of patients who had a positive test for COVID-19.
Since we do not know the number of people who were infected but not tested for the virus, the actual mortality rate of all the people that are infected is probably much lower.


### The main aim is to predict is whether the x-ray of the patient is COVID-19 positive or COVID-19 negative using deep learning.
### To predict the X-ray images we have used the Transfer Learning technique

* The deep learning architecture used in this project is **ResNet50**

## Why are we using ResNet?
* The ResNet has an extremely deep network i.e of 152 layers.
* The shallower version (i.e ResNet50) is available.
* This specialized network architecture was introduced by Microsoft.

## Why does ResNet Perform well ?
* Having a regular network which is very deep actually hurts the performance because of vanishing gradient and exploding gradient
* In most of the cases the ResNet's will stop improving rather than decreasing the performance.
* If the layer is not useful L2 regularization will bring its parameters very close to zero.
* The ResNet allows us to converge more faster
* The ResNet's have **moderate efficiency** depending upon the model and has **highest accuracy**.

# Residual Block
![residual block](https://github.com/akhiilkasare/Covid-19-chest-x-ray-detection/blob/master/Images/residual_bolck.png)

1. In this (x) goes through conv-relu-conv series and gives us F(x).
2. The result is then added to the original input (x) (i.e. F(x) + x).
3. We now here call it as H(x) = F(x) + x

# Full ResNet architecture
![architecture](https://github.com/akhiilkasare/Covid-19-chest-x-ray-detection/blob/master/Images/resnet-50.png)
1. It has stacked residual block.
2. Every residual blockc has 3x3 convolution layer.
3. Double layered & the downsample is done spatially using stride of 2 in each dimension.
4. It has an additional convolution layer at the beginning 
5. No fully connected layer at the end (only FC 1000 to output class).

# Dataset
* The dataset contains the X-ray images of the normal patients and the patients having COVID-19
* The dataset has two classes COVID and NON-COVID.

* Normal X-ray
![normal](https://github.com/akhiilkasare/Covid-19-chest-x-ray-detection/blob/master/Images/normal_xray.jpg)

* COVID-19 X-ray
![covid](https://github.com/akhiilkasare/Covid-19-chest-x-ray-detection/blob/master/Images/covid_chest_x-ray.jpeg)

# Building the model

Determining which model to go forward with is not an easy decision, and it requires a lot of trial and error. Every model is unique and requires a balance between complexity and efficiency. According to the No Free Lunch Theorem, no one model works best for all possible situations, so it is best to test as many as you can.

# Evaluating the model

Depending on the type of problem you have set out to solve, there are specific evaluation metrics to use that can give insight into how well your model is doing and what hyperparameters might need to be tuned. Evaluating a model is a holistic approach that’s not solely based on having high accuracy.
![accuracy](https://github.com/akhiilkasare/Covid-19-chest-x-ray-detection/blob/master/Images/accuracy.png)

![loss](https://github.com/akhiilkasare/Covid-19-chest-x-ray-detection/blob/master/Images/tl.png)

# Conclusion

Developing and Implementing a Deep Learning for a healthcare setting is not a quick process, but I hope this project gives you a foundation for knowing the obstacles you might come across. Keep in mind, even if you build your model and it works well, you still need to deploy it. Although deploying a Deep Learning system is very simple in practice, healthcare regulations and controls require you to take certain measures to ensure standardization and quality assurance.


# Cotton-Disease-Prediction
![img1](https://user-images.githubusercontent.com/37875797/117844621-75bf1a00-b29d-11eb-9c7a-47ef88e9f50a.jpg)

## Table of Content
  * [Demo](#demo)
  * [Overview](#overview)
  * [Aim](#aim)
  * [Dataset](#dataset)
  * [Modeling](#modeling)
  * [Directory Tree](#directory-tree)
  * [Deployement](#deployement)
  * [Technical Aspect](#technical-aspect)
  * [Future Scope](#future-scope)
  * [Technologies Used](#technologies-used)
  * [Credits](#credits)

## Demo
https://user-images.githubusercontent.com/37875797/117831114-e7916680-b291-11eb-8b62-99f8028bc3ea.mp4

## Overview

India is the largest producer of cotton in the world. The United States Department of Agriculture (USDA) pegs India’s cotton production at 29 million bales in the 2019-20 season as against 26 million bales the previous year. The latest figures mean that India is all set to surpass China, which has a projection of 27.75 million bales for the same season. However, despite these impressive numbers, the productivity per hectare is starkly low.The production of cotton in india reducing gradualy over year because of major cotton diseases which impact their production very much some common diseases like insect attack,charcol rot and many are making heavy impact over their plantation.Due to this many cotton cultivators farmer get a huge drop down in their production and income.The problem will be solved if the farmer get to know about the plants which are infected and diseased in early stages of their growth so that farmers can use pesticides and different medicinal equipments to sprinkles medicines over plants and save their crops from diseases in early stages of production.As this project will help the farmers to recognize the cotton plants which are Fresh and Diseased by simply uploading the pictures of the cotton plants on the web app.we can also use drone to capture realtime images and uploaded to web app.

## Aim
There is a need for a system which can automatically detect the diseases as it can bring revolution in monitoring large fields of crop and then plant leaves can be taken cure as soon as possible after detection of disease. 

## Dataset
Dataset link - https://www.kaggle.com/janmejaybhoi/cotton-disease-dataset

![Screenshot (189)](https://user-images.githubusercontent.com/37875797/117844104-0ba67500-b29d-11eb-8083-e6ae2b31b85c.png)

In this dataset we are provided with images that belong to 4 classes : diseased leaf , diseased plant , fresh leaf and fresh plant. The objective of this study is to create a CNN model to help us predict whether these image of the leaf/plant belong to the diseased category or the healthy category.

## Modeling
For modeling purposes, we used only keras transfer learning models.
First, we have done a basic image augmentation technique for the training dataset.

![Screenshot (191)](https://user-images.githubusercontent.com/37875797/117935983-f1fb4100-b321-11eb-9d56-4829e7f28564.png)

For transfer learning, we used three models.In these models we trained our dataset on top layer of the models and set other layers to non-trainable.
```
+-------+-------------------+------------------+------------------+---------------+
| Sl.N0 |       Model       | Number of epochs | Total parameters |  val_accuracy |
+-------+-------------------+------------------+------------------+---------------+
|   1   |      Resnet50     |        20        |     23989124     |     0.611     |
+-------+-------------------+------------------+------------------+---------------+
|   2   |    Resnet152v2    |        20        |     58733060     |     0.959     |
+-------+-------------------+------------------+------------------+---------------+
|   3   | Inception Network |        20        |     22007588     |      0.95     |
+-------+-------------------+------------------+------------------+---------------+
```
## Directory Tree
```
├── Model
│   ├── model_inception.h5
├── template	
│   ├── disease_leaf.html
│   ├── disease_pant.html
|   |── healthy_leaf.html
|   |── healthy_leaf.html
|   |── index.html
├── cotton_disease_predictioin.ipynb
├── app.py	
├── requirement.txt
|── procfile
  ```

## Deployement
An implementation of a cotton leaf disease prediction machine learning model in TensorFlow. The application operates via a web interface where one may upload an image of a cotton plant/leaf and retrieve the prediction of whether or not it is infected.The app implemented by pthon flask framework

### Run your Flask APP #

   - Install all the PyPI requirements.
   ```
   > pip3 install -r requirements.txt
   ```
 - Manually place the model file `model_inception.h5` in the application directory (optional).
 - Start the Flask server.
   ```
   > flask run
   ```
   Make sure that the `FLASK_APP` enviroment variable is either empty or set to `app.py`. You can manually do that by executing `export FLASK_APP=app.py`.
   
   The application will try to locate the model i. e. `model_inception.h5` in the current directory, and if it is not found, download it.
* Note - model_inception.h5 not present in github repository because of larger size.

## Technical Aspect

1) Training image dataset using transfer learning models.
2) Deployement of model using flask.

* For training purposes, we use tensorflow.keras library.
* For deployment, we use Flask.

## Future Scope
* Deploy the model in any of the Paas.
* Developing front end that can recommend solution(pesticides and natural remedies) to the diseases.
* Accessible to all the regional langauges in india.

## Technologies Used
* Jupyter Notebook
* Tensorflow
* Keras
* Flask

## Credits
[Kaggle](https://www.kaggle.com/janmejaybhoi/cotton-disease-dataset) - For conducting problem and providing this wonderful dataset.

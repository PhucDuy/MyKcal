# MyKcal - Food image recognition for dietary assessment 
![](https://i.imgur.com/ADjuRmy.png)

## Introduction
With people paying increasing attention to tracking meal items and nutrition contents in daily life for weight loss or medical purposes, self-managed food monitoring has become a vital application for computer vision. The tradiation dietary assessment have multiple challenges to be accurately assessed. Most of the current methods for dietary assessment must rely on memory to recall foods eaten. Even we remember the food we ate, but we didn't know what it is and their ingredients.Furthermore, nutrition information is vital for fitness, where we need to control the number of calories, carbohydrates, fats, proteins. 
In order to improve accuracy and convenience in diet assessment, The project aim to build a system that can instantly detect food through the phone camera and return nutritional information of this food. 
## Objective
Build the mobile app that can help user can easily record their meals and keep track consumption of nutrition through their mobile phone.

### Milestone
1. Detect food from a picture
Build the mobile app that can take a picture and detect food in this picture.
- Detect 1 dish in a picture
- Detect multiple dishes in 1 picture
2. Display a nutrition of food in a picture
3. Record the meal nutrition 
4. Show ingredients and recipe of dish
5. Daily nutriotion calculation 

## Methodology 

### Approach 
The project is mainly referenced from the two articles: [YOLO for Real-Time Food Detection](http://bennycheung.github.io/yolo-for-real-time-food-detection) and [A Real-time Food Detection Mobile Application by Deep Convolutional Neural Networks](https://arxiv.org/pdf/1909.05994.pdf)

![](https://i.imgur.com/4GK6Ij0.png)

1. Food detection
![](https://i.imgur.com/SBKyanK.png)

Before we start to classify food in the picture, we have to understand how many objects appear on the image.
The main idea here is to divide each input image in to (S,S) grid and predict N bouding boxes and confidence in each cell. The confidence reflects the accuracy of the bounding box and whether the bounding box actually contain an object. 
We will separate the input image to multipe input by the bounding box of YOLO.

Using the [Open Images Dataset V6 + Extensions](https://storage.googleapis.com/openimages/web/index.html) to train model that could clasify food in a picture. 

2. Food tracking
![](https://i.imgur.com/CTj33y7.png)

After we have the input images, we can use the CNN model to detect type of food.
I believe we can train use some pretrain model such as mobilenet or EfficientNet. 
After detecting the food, we should use YOLO to display name of food.


3. Display nutrition of Food
Using api of [Nutritionix](https://www.nutritionix.com/)


4. Mobile application
Our final application will detect the food through image which is input by user. Mobile app will send image to server and receive result of food from server. After that, app will display food detection and nutrition for user.


### Dataset
[A Dataset for Learning Cross-Modal Embeddings for Cooking Recipes and Food Images](http://pic2recipe.csail.mit.edu/)
[Other food dataset](https://github.com/ivanDonadello/Food-Categories-Classification)


## Helpful links
https://www.nutritionix.com/
https://github.com/ivanDonadello/Food-Categories-Classification
https://github.com/SumithBaddam/NeuralCook
http://pic2recipe.csail.mit.edu/
https://arxiv.org/ftp/arxiv/papers/1606/1606.05675.pdf
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6368251/
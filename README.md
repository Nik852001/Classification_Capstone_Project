# Classification_Capstone_Project

Project Summary:

The Mobile Price Range Prediction project is a machine learning-based solution designed to help consumers and businesses determine the appropriate price range for mobile phones. With the proliferation of mobile devices and the wide variety of features available, it can be challenging for buyers to assess the fair market value of a smartphone. This project aims to provide an accurate price range prediction based on various device specifications and market trends.

Key Objectives:

1) Data Collection: Gather a comprehensive dataset containing information on various mobile phone models, including specifications such as processor type, RAM, storage capacity, camera quality, battery life, and more. This data should also include historical price data for each phone.

2) Data Preprocessing: Clean and preprocess the dataset to handle missing values, outliers, and standardize features for model training.

3) Feature Engineering: Create meaningful features from the raw data, such as calculating performance indices, camera quality scores, and other relevant metrics to improve prediction accuracy.

4) Model Selection: Explore and select the most suitable machine learning algorithms for the task of price range prediction. Common models include regression algorithms (e.g., linear regression, decision tree, random forest) and deep learning models (e.g., neural networks).

5) Model Training: Train the selected machine learning models using the preprocessed dataset, and employ techniques like cross-validation to evaluate their performance. Fine-tune hyperparameters to achieve the best results.

6) Model Evaluation: Evaluate the models using appropriate evaluation metrics (e.g., Mean Absolute Error, Root Mean Squared Error, R-squared) to assess their predictive accuracy.

7) Hyperparameter Tuning:Fine-tune model hyperparameters to optimize predictive accuracy.

The Mobile Price Range Prediction project aims to simplify the mobile phone buying process by providing users with reliable price range predictions based on the specific features they desire. This project can empower consumers to make informed decisions while buying mobile devices and assist businesses in setting competitive prices for their products in the dynamic mobile market.

 Data Description:

 *  **Battery_power** - Total energy a battery can store in one time measured in mAh
*   **Blue** - Has bluetooth or not
*   **Clock_speed** - speed at which microprocessor executes instructions
*   **Dual_sim** - Has dual sim support or not
*   **Fc** - Front Camera mega pixels
*  **Four_g** - Has 4G or not
*  **Int_memory** - Internal Memory in Gigabytes
*   **M_dep** - Mobile Depth in cm
*   **Mobile_wt** - Weight of mobile phone
*   **N_cores** - Number of cores of processor
*   **Pc** - Primary Camera mega pixels
*   **Px_height** - Pixel Resolution Height
*   **Px_width** - Pixel Resolution Width
*   **Ram** - Random Access Memory in Mega
*   **Touch_screen** - Has touch screen or not
*   **Wifi** - Has wifi or not
*  **Sc_h** - Screen Height of mobile in cm
*   **Sc_w** - Screen Width of mobile in cm
*   **Talk_time** - longest time that a single battery charge will last when you are
*   **Three_g** - Has 3G or not
*   **Wifi** - Has wifi or not
*  **Price_range** - This is the target variable with value of 0(low cost), 1(medium cost),
2(high cost) and 3(very high cost).

Exploratory data analysis:

Column: 'price'
![image](https://github.com/Nik852001/Classification_Capstone_Project/assets/93510310/26fbe50d-cb8c-473d-ac74-5bce4eb8c464)
Observation:
*   There are mobile phones in 4 price ranges. The number of elements is almost similar.

Column: 'Battery Power'
![image](https://github.com/Nik852001/Classification_Capstone_Project/assets/93510310/21e8f7af-18ac-4170-81f7-7ee4d1810316)
Observation:
*   This plot shows how the battery mAh is spread.
 There is a gradual increase as the price range increases

Column: 'Bluetooth'
![image](https://github.com/Nik852001/Classification_Capstone_Project/assets/93510310/8e6ae8a7-034c-4786-a7a3-99be69217f1e)
Observation:
*   Almost half the devices have Bluetooth, and half don’t have the bluetooth.

Column: 'RAM'
![image](https://github.com/Nik852001/Classification_Capstone_Project/assets/93510310/1ae9884f-5f9e-4c04-9d3a-0c5242db1cc6)
Observation:
*   RAM has continuous increase with price range while moving from Low cost to Very high cost.

Column: 'pixel_width'
![image](https://github.com/Nik852001/Classification_Capstone_Project/assets/93510310/3cdf29bb-feda-4b0b-8192-b7e0cdba15e7)
Observation:
*   There is not a continuous increase in pixel width as we move from Low cost to Very high cost. Mobiles with 'Medium cost' and 'High cost' has almost equal pixel width. So we can say that it would be a driving factor in deciding price_range.

Column: 'FC(Front Camera Megapixel)'
![image](https://github.com/Nik852001/Classification_Capstone_Project/assets/93510310/0f1f493d-3fcc-4674-b943-8072718e41d5)
Observation:
*   This features distribution is almost similar along all the price ranges variable, it may not be helpful in making predictions.

Column: 'Primary Camera Megapixel'
![image](https://github.com/Nik852001/Classification_Capstone_Project/assets/93510310/fc70e5b0-5f32-4e73-a467-c58a82f6be6c)
Observation:
*   Primary camera megapixels are showing a little variation along the target categories, which is a good sign for prediction.

Column: 'Mobile Weight'
![image](https://github.com/Nik852001/Classification_Capstone_Project/assets/93510310/ee9f3fb5-8549-4619-b809-b83a43c4cb7a)
Observation:
*   Costly phones are lighter.

Column: 'Screen Size'
![image](https://github.com/Nik852001/Classification_Capstone_Project/assets/93510310/23a81f57-e834-4118-9734-fecc0bc7bd97)
Observation:
*   Screen Size shows little variation along the target variables. This can be helpful in predicting the target categories.

Plot of binary features against price range:
![image](https://github.com/Nik852001/Classification_Capstone_Project/assets/93510310/fb70b6b6-13f9-447c-a7a6-ff441ebeb010)
Observation:

*   52.1% phones support 4G and 76.2% phones support 3G.
*   Feature 'three_g' play an important feature in prediction

Checking for multi-collinearity:
![image](https://github.com/Nik852001/Classification_Capstone_Project/assets/93510310/92cfb734-6005-453a-818f-7147b99ec179)
Observation:
*   List itemRAM and price_range shows high correlation which is a good sign, it signifies that RAM will play major deciding factor in estimating the price range.
*   There is some collinearity in feature pairs ('pc', 'fc') and ('px_width', 'px_height'). Both correlations are justified since there are good chances that if front camera of a phone is good, the back camera would also be good.
*   Also, if px_height increases, pixel width also increases, that means the overall pixels in the screen. We can replace these two features with one feature.
*   Front Camera megapixels and Primary camera megapixels are different entities despite of showing colinearity. So we'll be keeping them as they are.

Checking For Outlier:
![image](https://github.com/Nik852001/Classification_Capstone_Project/assets/93510310/d38f76d7-a759-4c3d-a87a-d1d8f1dc1adf)
Observation:
*   There are no such outliers.


# Model Implementation

Machine learning models can be described as programs that are trained to find patterns or trends within data and predict the result for new data.

In this project we are dealing with a classification problem, therefore we will be using classification models.

1.   Logistic Regression
2.   Random Forest
3.   Decision Tree
4.   XGBoost


# Conclusion

1.  From EDA we can see that here are mobile phones in 4 price ranges. The    number of elements is almost similar.
2.  Half the devices have Bluetooth, and half don’t have the Bluetooth.
3.   There is a gradual increase in battery as the price range increases.
4.   Ram has continuous increase with price range while moving from Low cost to Very high cost.
5.   Costly phones are lighter.
6.   RAM, battery power, pixels played more significant role in deciding the price range of mobile phone.
7.   Form all the above experiments we can conclude that logistic regression and, XGboosting with using hyperparameters Tunning  we got the best results.













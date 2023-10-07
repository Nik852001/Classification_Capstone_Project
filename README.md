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

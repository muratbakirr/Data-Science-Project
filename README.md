## Data Science-NBA Analysis
## Introduction
![nba images](https://github.com/muratbakirr/Data-Science-Project/assets/153373667/e98899ec-e0aa-4c6c-a5b4-b08a4abdda2c)


The my goal for this project is to analyze and to visualize how the shooting preferences changed over the years, and also to create a regression model which predicts to enough offensive rate for each team to be in NBA Play-offs.

I've played basketball for long time and I am a big fan of NBA so that's why I chose it to anaylze. The data that I will use this project has been collected from [here](https://www.basketball-reference.com/leagues/NBA_2021.html) by myself and it covers the years between 2000-2020.

# Data preview

<img width="688" alt="Screenshot 2023-12-10 at 5 36 55 PM" src="https://github.com/muratbakirr/Data-Science-Project/assets/153373667/ed2bbd23-aa0a-4b60-9f31-9b6f2d21446d">


* After finished the data cleaning process, firts of all I'd like to explain the variables of data. 

FGA: Field Goal Attempts 

2PA: 2-Point Fields Goal Attempts

3PA: 3-Point Fields Goal Attempts

FTA: Free Throw Attempts

ORB: Offensive Rebounds	

DRB: Defensive Rebounds

AST: Assits

STL: Steals

BLK: Blocks

TOV: Turnovers

PT: Points

# The Visualization of Shooting Preferences by Years

* I will also use the Tableau to visualize it, and be use to another data that is called "Shooting Stats" from the same source. Firtsly, I will start it with rising of 3-Point attempts which changed to gameplay of basketball.

<img width="468" alt="image" src="https://github.com/muratbakirr/Data-Science-Project/assets/153373667/432cde06-b631-491e-9d72-70b736e88765">

- Yes, 3-Point attempts had increased from 17.1% to 39.2% in 20 years. So let's have a look at this increasing's relationship with teams' offensive rate (PTS for 100 poss).

<img width="562" alt="Screenshot 2023-12-10 at 6 25 42 PM" src="https://github.com/muratbakirr/Data-Science-Project/assets/153373667/098c244a-493f-462c-b9da-5d5e39f484d1">

There is a strong positive relationship between 3-Point attempts and offensive rate. What about 2-Point attempts, alright let's see it;

<img width="562" alt="Screenshot 2023-12-10 at 7 36 39 PM" src="https://github.com/muratbakirr/Data-Science-Project/assets/153373667/0538ffcc-7ca7-490b-9750-bbc8994516d7">

There is a strong negative relationship between 2-Point attempts and offensive rate. So to make the shooting preferences by teams understandable for everyone, I've created the chart in Tableau. It suggests how it changed over the years.

<img width="468" alt="image" src="https://github.com/muratbakirr/Data-Science-Project/assets/153373667/d48fab02-93e2-46ae-8cea-55a42d5eb490">


# Create a Regression Model

Before start to create a model, I'd like to see correlation between variables. 

<img width="572" alt="Screenshot 2023-12-10 at 8 09 00 PM" src="https://github.com/muratbakirr/Data-Science-Project/assets/153373667/e4401a14-2881-474a-a9f6-cfc55463f02a">

Alright, as we can see that many variables are correlated each, and also we need to see the distribition in order to do that I made histogram charts for every variables.

<img width="421" alt="image" src="https://github.com/muratbakirr/Data-Science-Project/assets/153373667/451e9e7e-786f-4602-884c-9f7cf3d31e50">

Alright next step will be seperate the feature variables (X) and the target variable (y). The feature are scaled using the "StandartScaler" from scikit-learn as assume that all features are on the same scale.

<img width="420" alt="Screenshot 2023-12-10 at 9 06 34 PM" src="https://github.com/muratbakirr/Data-Science-Project/assets/153373667/cb0433d4-eb45-49ef-8ee4-29cf489ee96f">


The next step is that to split data into testing and training sets. The train_test_split function from scikit-learn is used for this purpose. The test_size parameter I determined that training set will be like 80% and testing 20% . 

<img width="825" alt="Screenshot 2023-12-10 at 9 14 08 PM" src="https://github.com/muratbakirr/Data-Science-Project/assets/153373667/ea615ef7-4779-4624-a023-f5db9888b1a0">

I createad Support Vector Regressin (SVR) model from scikit-learn, the model are trained using the trainin sets. 

<img width="340" alt="Screenshot 2023-12-10 at 9 18 20 PM" src="https://github.com/muratbakirr/Data-Science-Project/assets/153373667/a9be59e2-a26c-4afd-ab84-ba607e694938">

Evaluation for the regression, Mean Squared Error (MSE) and R-squared, are then calculated to assess the model's performance.

<img width="480" alt="Screenshot 2023-12-10 at 9 20 52 PM" src="https://github.com/muratbakirr/Data-Science-Project/assets/153373667/61fec3a1-07d2-413c-a218-7e4be65cf4da">

Visualizing the actual vs. predicted values is a helpful way to understand how well the Support Vector Regression (SVR) model is performing.

<img width="572" alt="Screenshot 2023-12-10 at 10 40 52 PM" src="https://github.com/muratbakirr/Data-Science-Project/assets/153373667/4c2328f5-7dc0-4371-beb7-f7c6724c1870">

I also created a user input into the console that after a user inputs 10 different stats, it will tell you if your team would be in Playoffs. I determined the threshold value 115 Points to be in Playoffs based on took the last year statistics.

<img width="793" alt="Screenshot 2023-12-10 at 10 46 58 PM" src="https://github.com/muratbakirr/Data-Science-Project/assets/153373667/9b0114b2-73de-4c37-b3b3-f328493c952b">

<img width="501" alt="Screenshot 2023-12-10 at 11 02 48 PM" src="https://github.com/muratbakirr/Data-Science-Project/assets/153373667/95e61722-75aa-4a2f-94b1-ba8f8ba0f1a8">


<img width="650" alt="Screenshot 2023-12-10 at 10 56 14 PM" src="https://github.com/muratbakirr/Data-Science-Project/assets/153373667/2b57de75-6bdc-419e-8ecc-badd47519d6e">

# Summary

There are many values ​​that affect PTS. Teams increased their 3-point attempts to score more PTS. In this project I conducted, we observed how the preferred shooting changed over the years, especially how mid-range shooting decreased significantly while 3-point shooting increased. We also created a regression model and examined whether the teams achieved the PTS required for the playoffs.




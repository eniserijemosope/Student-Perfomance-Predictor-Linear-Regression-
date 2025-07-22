# Student Scores Prediction using Linear Regression

## Project Overview

This project analyzes student performance to predict scores in three academic subjects: **Math**, **Reading**, and **Writing** using a simple yet powerful **Linear Regression** model.

##  Dataset Used

* **File**: StudentsPerformance.csv
* **Records**: 1000 students
* **Features**:

  * Categorical: gender, race/ethnicity, parental level of education, lunch, test preparation course
  * Targets: math score, reading score, writing score


## Exploratory Data Analysis (EDA)

###  Data Inspection

* No missing values.
* Numerical targets range from 0 to 100.
* Categorical variables were one-hot encoded.

###  Visualizations Performed:

* **Histograms**: Score distributions
* **Boxplots**: Score comparison by gender, lunch type, etc.
* **Heatmap**: Correlation between math, reading, and writing scores
* **Countplots**: Distribution of each categorical feature

*NB: All plots are included in the "images/" folder.*

## Data Preprocessing

* **Features**: All categorical variables encoded using pd.get_dummies().
* **Targets**: Grouped as a single DataFrame with 3 target columns.

## Model Used: Linear Regression

We trained a single LinearRegression() model on all three scores simultaneously (multi-target regression).


##  Model Evaluation

We used **3 main evaluation metrics**:

| Metric   | Description                                              | Value      |
| -------- | -------------------------------------------------------- | ---------- |
| R² Score | Measures how much variance is explained (per target avg) | **0.251**  |
| RMSE     | Root Mean Squared Error – average prediction error       | **186.21** |
| MAE      | Mean Absolute Error – average absolute difference        | **10.85**  |

###  Interpretation:

* **R² = 0.251**: The model explains \~25.1% of the variation in the scores — modest, but expected for a simple linear model.
* **RMSE = 186.21**: On average, the squared error between predicted and actual combined score (sum of 3 scores) is quite high.
* **MAE = 10.85**: Each subject score is off by around 11 points on average.

> These results show **linear regression underfits slightly**, but still gives a decent baseline.

## 📉 Actual vs Predicted Plots

Visualizing how close the predictions are to the real scores:

### 📘 Math Score

<img width="1002" height="622" alt="math" src="https://github.com/user-attachments/assets/5e1fc6d5-f3c1-42d6-8e58-120f9f2cf649" />

### 📗 Reading Score

<img width="1002" height="622" alt="reading" src="https://github.com/user-attachments/assets/f0404591-0060-45b1-bf12-d796f67bba58" />

### 📙 Writing Score
<img width="1002" height="622" alt="writing" src="https://github.com/user-attachments/assets/12724095-c67e-429b-9ed3-9bdb51396b8f" />


### Each plot shows:
 Actual values on the x-axis
 Predicted values on the y-axis
 (Red dashed line "y = x" as a reference for perfect prediction)


## Limitations

* Linear regression assumes a linear relationship meaning it may miss complex interactions.
* Model may predict scores above 100 or below 0 (non-realistic values).
* Categorical data may be better handled using tree-based models.


## WHat I can do for a better prediction??

* Compare results using **Random Forest** or **Gradient Boosting**.
* Add **cross-validation** for more robust accuracy checks.
* Explore **feature importance** to interpret what influences scores most.

## Conclusion

**Linear Regression** gives a reasonable approximation of student performance. This project demonstrates the core ML workflow and is perfect for building confidence with regression problems but it would be better used when the target feauture is just one thing.


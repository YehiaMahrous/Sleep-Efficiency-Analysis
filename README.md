## Project Overview
This project analyzes factors affecting sleep efficiency, including deep sleep percentage, light sleep percentage, awakenings, alcohol consumption, smoking status, and exercise frequency. The dataset consists of various sleep metrics and demographic information. Our goal is to build a machine learning model to predict sleep efficiency based on these factors.

## Dataset
The dataset used in this analysis contains information on sleep patterns and habits. It includes the following columns:

Age: Age of the individual
Gender: Gender of the individual
Bedtime: The time the individual went to bed
Wakeup_time: The time the individual woke up
Sleep_duration: Duration of sleep
Sleep_efficiency: Efficiency of sleep
REM_sleep_percentage: Percentage of REM sleep
Deep_sleep_percentage: Percentage of deep sleep
Light_sleep_percentage: Percentage of light sleep
Awakenings: Number of times the individual woke up during sleep
Caffeine_consumption: Amount of caffeine consumed
Alcohol_consumption: Amount of alcohol consumed
Smoking_status: Smoking status (Yes/No)
Exercise_frequency: Frequency of exercise (0-5 times a week)
Date: Date of the record
hour: Hour of the record

## Data Preprocessing
-Handling Missing Values: Missing values in the Awakenings, Caffeine_consumption, Alcohol_consumption, and Exercise_frequency columns were filled with the mode of each respective column.


'awakenings_mode = df['Awakenings'].mode()[0]'

'df['Awakenings'].fillna(awakenings_mode, inplace=True)'

'caffeine_mode = df['Caffeine_consumption'].mode()[0]'

'df['Caffeine_consumption'].fillna(caffeine_mode, inplace= True)'

'alcohol_mode = df['Alcohol_consumption'].mode()[0]'

'df['Alcohol_consumption'].fillna(alcohol_mode, inplace= True)'

'exercise_mode = df['Exercise_frequency'].mode()[0]'

'df['Exercise_frequency'].fillna(exercise_mode, inplace = True)'

-Encoding Categorical Variables: The Smoking_status column was encoded to numeric values (0 for 'No' and 1 for 'Yes') for machine learning model compatibility.

## Exploratory Data Analysis
Various visualizations were created to explore the relationships between the sleep metrics and the other factors such as smoking, alcohol consumption, and exercise frequency.

# Findings:
Smoking: Smokers tend to have lower sleep efficiency and reduced deep sleep duration.
Alcohol Consumption: Higher alcohol consumption is associated with lower sleep efficiency, decreased deep sleep, and increased light sleep duration.
Exercise Frequency: Regular exercise (4-5 times a week) is associated with higher sleep efficiency, more deep sleep, and less light sleep.

## Machine Learning Model
A Gradient Boosting Regressor was used to predict sleep efficiency based on the following features: Deep_sleep_percentage, Light_sleep_percentage, Awakenings, Alcohol_consumption, Smoking_status, and Exercise_frequency.

# Model Performance
Mean Squared Error (MSE): 0.0026
R² Score: 0.8571

# Feature Importance
Light_sleep_percentage:	0.4500
Deep_sleep_percentage:	0.3292
Awakenings:	0.1393
Smoking_status:	0.0340
Alcohol_consumption:	0.0243
Exercise_frequency:	0.0229

# Interpretation
The R² score of 0.8571 indicates that the model explains approximately 85.71% of the variance in sleep efficiency based on the selected features. The most influential features are Light_sleep_percentage and Deep_sleep_percentage.

## Conclusion
The analysis shows that smoking and alcohol consumption negatively impact sleep efficiency, while regular exercise improves it. The Gradient Boosting Regressor model provides good predictive accuracy for sleep efficiency based on the identified key features.

## Future Work
-Explore additional features that may influence sleep efficiency.
-Experiment with other machine learning algorithms to further improve prediction accuracy.
-Investigate the impact of different data preprocessing techniques on model performance.

## Usage
Clone the repository.
Install the necessary libraries using pip install -r requirements.txt.
Run the Jupyter notebook Sleep_Efficiency_Analysis.ipynb to reproduce the analysis and model training.

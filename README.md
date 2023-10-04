# Group Assessment 2 for unit HIT140 - Group 9
## Objective
By examining these voice samples, we aim to explore the potential of speech data as a diagnostic tool. This project aims to predict the motor and total UPDRS scores, which indicate the severity and progression of PD in patients.

## Datasets
We use a dataset provided by our lecturer in a CSV file, which has 5875 rows and 24 columns. The original study collected the voice recordings of 42 subjects with early-stage Parkinson’s disease, with each participant contributing between 101 and 168 voice samples. These samples were then broken down into various acoustic characteristics using a software named Praat.

We also used another dataset in a .txt file to validate the models which was provided in the previous assignment. The dataset contains voice recordings from 20 individuals with Parkinson's disease and 20 without. Each of these participants contributed 26 voice samples, and these were also extracted for different acoustic characteristics using software called Praat.

Learn more about Praat software: https://www.fon.hum.uva.nl/praat/

## Methodology
We started with a simple linear regression model. However, after seeing that its R-squared value was unsatisfactory, we transitioned to using multiple linear regression, which showed improved performance. We also built models based on median values of subjects. And then we removed outliers and rebuilt the models and decided not to remove outliers due to data loss concerns.  We then refined our model by applying various optimisation techniques. This included using log-transformation and examining collinearity. Next, we standardized the data and used a Gaussian transformation. We also removed the intercept to see if it improved the models and applied 10-fold cross validation for the optimal models. Finally, we fine-tuned the model's settings using hyperparameter optimization and tested the performance of the models using the dataset from our previous assignment. Finally, we employed a dataset from a prior project for model validation. This dataset provided a set of features instrumental in distinguishing individuals with Parkinson's disease from healthy individuals.

## Results
After apply log-tranformation, Gaussian transformation, backward feature selection combined with collinearity analysis, we have the optimal models to predict UPDRS scores (Adjusted R-squared = 0.187 for motor_updrs and 0.188 for total_updrs).

The predictors to build the model of motor_updrs are: 'age', 'test_time', 'jitter(%)', 'jitter(abs)', 'jitter(ppq5)', 'shimmer(%)', 'shimmer(apq5)', 'shimmer(apq11)', 'nhr', 'hnr', 'rpde', 'dfa', 'ppe', 'harmonicity_difference', 'log_shimmer(apq3)', 'log_shimmer(dda)'.

The predictors to build the model of total_updrs are: 'age', 'test_time', 'shimmer(apq5)', 'shimmer(apq11)', 'nhr', 'hnr', 'rpde', 'dfa', 'ppe', 'jitter_shimmer_difference_ratio', 'harmonicity_difference', 'log_shimmer(apq3)', 'log_shimmer(dda)', 'log_jitter(rap)'.

## Installation and usage guide
numpy: Provides support for working with arrays and various mathematical functions. Installation: pip install numpy

pandas: A powerful data manipulation and analysis library. Installation: pip install pandas

matplotlib: A plotting library for creating static, animated, and interactive visualizations. Installation: pip install matplotlib

seaborn: A data visualization library based on matplotlib that provides a higher-level interface for drawing attractive statistical graphics. Installation: pip install seaborn

scipy: Used for mathematical operations and has support for linear algebra, optimization, integration, and statistics. Installation: pip install scipy

statsmodels: Provides classes and functions for the estimation of many different statistical models, as well as for conducting statistical tests. Installation: pip install statsmodels

sklearn (scikit-learn): A machine learning library that provides tools for data mining and data analysis. Installation: pip install scikit-learn

## Acknowledgements
We'd like to express our gratitude to our lecturer Dr. Yakub Sebastian at CDU for his invaluable guidance and insights throughout this project and Prof. Andrew Ng for the inspirational machine learning course on Coursera.

## List of project participants and contacts
I spearheaded this project as the team leader, with the invaluable collaboration of three other members: Thi Minh Chau Pham, Hai Dang Dang, and Quoc Vinh Nguyen.

Any concerns or contributions you might have, please feel free to reach me through [email](lecongdoo3@gmail.com).

## References
AZADI, H., AKBARZADEH-T, M.-R., SHOEIBI, A. & KOBRAVI, H. R. 2021. Evaluating the effect of Parkinson's disease on jitter and shimmer speech features. Advanced Biomedical Research, 10.

BENBA, A., JILBAB, A. & HAMMOUCH, A. 2016. Voice analysis for detecting patients with Parkinson's disease using the hybridization of the best acoustic features. International Journal on Electrical Engineering and Informatics, 8, 108.

KHAN, T., WESTIN, J. & DOUGHERTY, M. 2014. Classification of speech intelligibility in Parkinson's disease. Biocybernetics and Biomedical Engineering, 34, 35-45.

NATIONAL INSTITUTES OF NEUROLOGICAL DISORDERS AND STROKE. 2023. Parkinson's Disease [Online]. Available: https://www.ninds.nih.gov/health-information/disorders/parkinsons-disease [Accessed].

PARKINSON’S FOUNDATION. Notable Figures with Parkinson’s [Online]. Available: https://www.parkinson.org/understanding-parkinsons/statistics/notable-figures [Accessed].


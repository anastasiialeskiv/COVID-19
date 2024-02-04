## Anastasiia Leskiv

![image](https://github.com/anastasiialeskiv/COVID-19/assets/124845922/9bbee5b3-2584-4003-a19d-919f75e700ea)

# Overview

Coronavirus disease (COVID-19) is an infectious disease caused by the SARS-CoV-2 virus. Most people infected with the virus will experience mild to moderate respiratory illness and recover without requiring special treatment. However, some will become seriously ill and require medical attention. Anyone can get sick with COVID-19 and become seriously ill or even die. 
Throughout the pandemic, healthcare providers have grappled with a critical challenge: a scarcity of medical resources and an effective distribution strategy. Anticipating the specific medical needs of individuals upon testing positive or even beforehand is paramount. This predictive ability could significantly assist authorities in proactively sourcing and organizing the requisite resources, potentially saving lives in critical situations during these challenging times.

The goal of this project is to build a machine learning model that, shows patient's current symptom, status, and medical history, predict patients who are at high risk of death from covid.

# Business and Data Understanding

This data set contains 21 unique features and 1,048,576 unique patients

sex: 1 for female and 2 for male.In the Boolean features, 1 means "yes" and 2 means "no". values as 97 and 99 are missing data.

sex: 1 for female and 2 for male.

age: of the patient.

classification: covid test findings. Values 1-3 mean that the patient was diagnosed with covid in different degrees. 4 or higher means that the patient is not a carrier of covid or that the test is inconclusive.

patient type: type of care the patient received in the unit. 1 for returned home and 2 for hospitalization.

pneumonia: whether the patient already have air sacs inflammation or not. pregnancy: whether the patient is pregnant or not.

diabetes: whether the patient has diabetes or not.

copd: Indicates whether the patient has Chronic obstructive pulmonary disease or not.

asthma: whether the patient has asthma or not.

inmsupr: whether the patient is immunosuppressed or not.

hypertension: whether the patient has hypertension or not.

cardiovascular: whether the patient has heart or blood vessels related disease.

renal chronic: whether the patient has chronic renal disease or not.

other disease: whether the patient has other disease or not.

obesity: whether the patient is obese or not.

tobacco: whether the patient is a tobacco user.

usmr: Indicates whether the patient treated medical units of the first, second or third level.

medical unit: type of institution of the National Health System that provided the care.

intubed: whether the patient was connected to the ventilator.

icu: Indicates whether the patient had been admitted to an Intensive Care Unit.

date died: If the patient died indicate the date of death, and 9999-99-99 otherwise.

![image](https://github.com/anastasiialeskiv/COVID-19/assets/124845922/0340239e-09eb-4c2f-a841-de90ad78f662)

Each square shows the correlation between the variables on each axis. Correlation ranges from -1 to +1. Values closer to zero means there is no linear trend between the two variables. The close to 1 the correlation is the more positively correlated they are; that is as one increases so does the other and the closer to 1 the stronger this relationship is. A correlation closer to -1 is similar, but instead of both increasing one variable will decrease as the other increases. The diagonals are all 1/dark because those squares are correlating each variable to itself (so it's a perfect correlation). For the rest the larger the number and darker the color the higher the correlation between the two variables.

![image](https://github.com/anastasiialeskiv/COVID-19/assets/124845922/e6d64785-b47a-489e-b377-5c46e63336f3)


Using crosstab plot to see Number of patients who died from COVID-19 based on age where 2- means this patient is alive, 1- dead

![image](https://github.com/anastasiialeskiv/COVID-19/assets/124845922/3948909b-135f-4031-807a-470df79906d7)

Here we can come to the conclusion, it's very rerely happens at a youg age it's mostly at the age of 50-80 y.o

![image](https://github.com/anastasiialeskiv/COVID-19/assets/124845922/4ecc9a70-2695-4324-8602-840c26b927d2)

Gender does not really affect the number of death.

![image](https://github.com/anastasiialeskiv/COVID-19/assets/124845922/960efccf-9af8-4f64-8f1b-6f58053af783)

Tabacco users are more likely to die from COVID-19

![image](https://github.com/anastasiialeskiv/COVID-19/assets/124845922/1c39e706-0559-436d-a536-237bbe76e439)

Patients with diabetes are more likely to die from COVID-19

![image](https://github.com/anastasiialeskiv/COVID-19/assets/124845922/4d68c3ed-6ca2-4470-bc5f-3c214778b57e)


Patients with obesity are more likely to die from COVID-19

# Modelind

![image](https://github.com/anastasiialeskiv/COVID-19/assets/124845922/b3ab7c18-5fbf-43a4-b03b-d25c106c0df9)

True Positive(we predict our patient has risk of death from COVID-19 and patient actually has it)-13861

True Negative (we predict our patient does not have risk of death from COVID-19 and patient actually has it)-13427

False Positive(we predict our patient has risk of death from COVID-19 and patient actually does not have it)-1535

False Negative(we predict our patient does not have risk of death from COVID-19 and patient actually has it)-1063


# Evaluation

![image](https://github.com/anastasiialeskiv/COVID-19/assets/124845922/89796730-7e1e-4726-8cda-e153df7327af)

Plotting the ROC Curve: The ROC curve is plotted using Matplotlib, with the diagonal line representing a random classifier, and the curve showing the trade-off between true positive rate and false positive rate.

The ROC curve is a useful visualization for understanding the model's discrimination ability across different threshold settings.

In my case the classifier can almost perfectly distinguish between all the Positive and the Negative class points with accuracy 91%


# Conclusion

The whole dataset was split into 80/20 train/holdout. Predictions on 20% holdout were limited till the end. After I finished this project I came to the conclusion that people who are getting COVID are at a very high risk of getting pneumonia. Tobacco users are more likely to die from COVIS-19.Patients with diabetes are more likely to die from COVID-19.Patients with obesity are more likely to die from COVID-19 Age also affects the number of people who died from COVID-19. It's very rarely happens at a young age it's mostly at the age of 50-80 y.o

For modeling: I used logistic regression, random forest, decision tree, stacking resembling for setting on random forest as the model with the best cross-validation performance, random forest feature importance ranking I used for guiding the choice and order of variables to be included as the model underwent refinement. I used Logistic Regression to predict the risk of getting COVID-19 virus with 91% accuracy and with F1 Score for Class 0: Approximately 0.9143. The F1 score is a useful metric, especially in imbalanced datasets, as it considers both false positives and false negatives. A higher F1 score indicates better performance, considering both precision and recall.

## Limitation

I would also like to have more information about patients' habits and how careful they are in this time of pandemic.

## Recomendation

I would recommend to my client to pay more attention to patient's sugar level, patients who use tobacco, recommend patients to do more exercise and keep healthy diet.Be more attentive to patients with age of 50 and older, and patients with obesity 

## Next step
My next step would be to continue with developing model for better result. Use more data for better prediction.




├── .gitignore

├── Notebook.ipynb

├── README.md

└── presentation.pdf

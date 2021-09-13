# Predicting Prevalence of Influenza-Like Illness From Geo-Tagged Tweets (Zhang & Arablouei & Jurdak, 2017)



## Summary of the Article
This study has been investigated to find out how the prevalence of influenza can be detected by state-of-the-art influenza-like illness(ILI) related Tweets. To examine the influence of Twitter data on the disease outbreaks, a linear regression was established with a correlation coefficient of 0.93 and a p-value 0f 0.017. The result reveals that ILI-related Twitter data has a strong linear correlation with state-level influenza spread and distribution. Therefore, the ILI-related Twitter data can estimate the state-level influenza prevalence.
 
*influenza-like illnesses (ILI)

## 1)What was the purpose for the authors to use regression analysis in the study?

To find out if ILI-related Twitter data has an ability to predict a disease outbreak,  the authors used regression analysis. Regression analysis was used to understand which independent variables are related to the dependent variable. 



## 2) What were the independent(cause) and dependent(effect) variables and how were they measured? 

Independent variable is ILI-related Twitter data dependent variable is disease outbreak

The study used 8,961,932 tweets, collected by The Commonwealth Scientific and Industrial Research Organisation(CSIRO) in Australia, 2015. A large dataset of geo-tagged tweets within Australia in 2015 was provided from Twitter Streaming API. This dataset is organized in JSON format, shown in Table 1. 
![image](https://user-images.githubusercontent.com/89971178/133129245-857f940e-eddf-4c68-bd4f-2dd5bcb84d80.png)


After data cleaning, refinement of the dataset is needed. In this tweet database, the classifiers were directed to differentiate “sick” tweets and “other” tweets, which were ILI_related tweets and non-ILI-related tweets respectively.  

In Figure 1 and 2, the training of the Support Vector Machine(SVM) classifiers and classification of the stage were shown. Two SVM classifiers, cs and co , are trained using “scikit-learn Python library”, that distinguish “sick” and “other” tweets and labeled them. To acquire a high-quality set of labeled training data, the repeated training was essential and manual checking validations are included. About 2000 tweets were labeled manually resulting in 36 ILI-related tweets and 1974 non-ILI-related tweets. csandco were trained and investigate the range of values for the parameters by using this labeled dataset. Then, the parameters that show the optimal sorting were selected. This process has been repeated by using the larger tweet texts. Throughout these process, the class weight and the cparameters are carefully selected.

![image](https://user-images.githubusercontent.com/89971178/133129339-0b9ceecb-2166-4e89-8c9e-3ce6ee669c34.png)


After refining the data set, the number of detected ILI related tweets with internet access and Twitter Penetration rates in each state is normalized. In the state-level analysis, based on the population of each state, the “sick” tweet numbers and the number of disease notifications were classified. 

By using the generated Twitter dataset, the state-level linear regression model between the Twitter data and the true influenza notification data is demonstrated.


Each state, the number of recorded influenza notifications is estimated by:
![image](https://user-images.githubusercontent.com/89971178/133129505-8f23f9cb-df20-4916-be9a-16a1b45d81c5.png)
where Y is the estimated number of influenza patients, B0 is the intercept, B1 is the regression slope coefficient, and  is the number of ILI-related tweets.

Internet access and Twitter penetration rate parameters are shown below. 
The independent variable xis calculated by:
![image](https://user-images.githubusercontent.com/89971178/133129484-6db71a47-82b6-4606-9c32-1c439d921224.png)
where i is the Internet access rate and t is the Twitter penetration rate.

Through these processes, ILI-related Twitter data and state-level influenza prevalence were measured.



## 3) Quote the regression model the authors have obtained. How big the determinant coefficient, R2? 
In Figure 9, After taking Internet access and Twitter penetration rates into consideration as weighting parameters, the linear regression model has generated a higher Pearson correlation coefficient of 0.93 and p-value 0.017.  

Therefore, the determinant coefficient is 0.86. The strength of the correlation is interpreted with large that shows influenza prevalence is able to estimate by using Twitter data.
“A strong positive linear regression model strongly suggests that Twitter data can capture the key features of state-level influenza prevalence and has a good potential in disease spread modeling.”
![image](https://user-images.githubusercontent.com/89971178/133129532-06570510-3632-4910-9366-503dc8c178ed.png)





## 4)Was the “1)” supported or not?

The results supported the “1)”. There is a strong positive linear correlation exists between the number of ILI-related tweets and the number of real-world recorded influenza notifications data at state scale with a correlation coefficient of 0.93 and a p-value of 0.017. Therefore, the Twitter data is able to predict influenza outbreaks.


## Reference

Zhang, K.,& Arablouei R.,& Jurdak R., (2017) Predicting Prevalence of Influenza-Like Illness From Geo-Tagged Tweets

#  Linear Regression on Student Performance in Highschool


## Dataset 

### Description 
This data approach student achievement in secondary education of two Portuguese schools. The data attributes include student grades, demographic, social and school related features. It was collected by using school reports and questionnaires. Two datasets are provided regarding the performance in two distinct subjects: Mathematics (mat), which is the subject I put my focus on, and Portuguese language (por). In [Cortez and Silva, 2008], the two datasets were modeled under binary/five-level classification and regression tasks. 


https://archive.ics.uci.edu/ml/datasets/student+performance


# Exploratory Data Analysis

## Descriptive Statistics and Visualization

After a quick cleaning and merging of the two datasets on math and portuguese, I spent a great amount of time visualizing data, since there were many interesting features to explore and thep possibility to see several two-dimensional relationships between the performance of a student (in math in particular) and its social, demographic, geographical background.

The feature with the greatest power of prediction on math performance is, unsurprisingly, the level in portuguese: very good students at math are also good at portuguese, and conversely.

Other point to highlight: the math average grade of boys in our dataset is higher than the average grade of girls; but the latter have a slightly better average grade in portuguese.

### Mean and Median Grades
![image](https://user-images.githubusercontent.com/63364114/102090599-f1678880-3e1d-11eb-90b6-5a691498d187.png)

The mean and median of the math average grades are both around 10.7/20

![image](https://user-images.githubusercontent.com/63364114/102088913-d562e780-3e1b-11eb-98f3-67e6be95db0f.png)

As usual, the distribution of grades in the dataset is Gaussian. Thanks to this two visualizations bewteen males and females, we can see that males have slightly better results at math.

### Age Feature 
![image](https://user-images.githubusercontent.com/63364114/102088863-c4b27180-3e1b-11eb-97e7-62d248ccd17c.png)

I dropped the outliers from the dataset and still obtained this apparent relationship between age and math grade:

![image](https://user-images.githubusercontent.com/63364114/102093355-5a9ccb00-3e21-11eb-82a8-ad718299b096.png)

### Portuguese and Math Grades Correlation

![image](https://user-images.githubusercontent.com/63364114/102088947-e3b10380-3e1b-11eb-8f2f-091180501490.png)

The pearson correlation coeff btw mean in maths and mean in portugese is 0.6.


### Studytime, Extra-paid Class, Absences and Math Mean

![image](https://user-images.githubusercontent.com/63364114/102091751-8ae36a00-3e1f-11eb-8988-d1d862d28c29.png)


![image](https://user-images.githubusercontent.com/63364114/102093445-77390300-3e21-11eb-9b94-f23be27d1527.png)


![image](https://user-images.githubusercontent.com/63364114/102090186-71d9b980-3e1d-11eb-8ab4-2b652be03bc2.png)

### Traveltime and Math Mean

![image](https://user-images.githubusercontent.com/63364114/102092059-e9a8e380-3e1f-11eb-9c4a-5609cc591b77.png)


![image](https://user-images.githubusercontent.com/63364114/102089659-d34d5880-3e1c-11eb-9c54-24142c010de2.png)

### Social and Demographic Features

![image](https://user-images.githubusercontent.com/63364114/102089674-d6e0df80-3e1c-11eb-920d-cd79946d687c.png)


![image](https://user-images.githubusercontent.com/63364114/102089685-db0cfd00-3e1c-11eb-847d-f65b47aa35db.png)


![image](https://user-images.githubusercontent.com/63364114/102089989-33dc9580-3e1d-11eb-86c6-01ad566705fa.png)


![image](https://user-images.githubusercontent.com/63364114/102090022-3dfe9400-3e1d-11eb-9fe6-b6337bf48c52.png)


![image](https://user-images.githubusercontent.com/63364114/102093279-435ddd80-3e21-11eb-8b20-81c2422b0e29.png)


### Social Life and Math Mean

![image](https://user-images.githubusercontent.com/63364114/102093159-20cbc480-3e21-11eb-8dc9-e869341c7aca.png)


![image](https://user-images.githubusercontent.com/63364114/102093038-fed24200-3e20-11eb-98ff-7c288b109633.png)


![image](https://user-images.githubusercontent.com/63364114/102093223-30e3a400-3e21-11eb-9712-c19b0ed6d329.png)



## Inferential Statistics

### Hypothesis Testing 

##### Are highschool boys in Portugal significantly better in maths than girls, on average ? 

Population: All highschool students in Portugal 

Parameter of Interest:  𝜇_m mean of boys in maths ; 𝜇_f mean of girls in maths. 

Null Hypothesis:  𝜇_m = 𝜇_f

Alternative Hypthosis:  𝜇_m > 𝜇_f

Data:
Df
Statistics on population are unknown.

#### Assumptions: 
- The observations of the grades and means in the dataset are considered to be the realizations of random variables independent and identically distributed. 
- Therefore they are normally distributed following a normal law with parameters 𝜇_m (males) and 𝜇_f (females).

#### Choice of test:

We will use a t-test, since we compare two samples of normally distributed data, with unknown parameters.


#### Conclusion on the test:
Since the p-value is significantly lower than 5%, we can reject the null hypothesis of equal means btw boys and girls with certainty 95%. Therefore we can say that it may be possible that male highschool students in Portugal get higher grades than female students in mathematics.

### Computing Confidence Intervals 

The mean of highschool girls in Portugal falls btw 9.7 and 10.8 with certainty 95%.
The mean of highschool boys in Portugal falls btw 10.7 and 11.8  with certainty 95%.




# Linear Regression Model

### Heatmap
![image](https://user-images.githubusercontent.com/63364114/102094229-6046e080-3e22-11eb-9ea2-00a2a33a1e1e.png)

### OLS Method using Statsmodel

![image](https://user-images.githubusercontent.com/63364114/102094369-89677100-3e22-11eb-81af-b6548a4645fc.png)

All p-values are less than 5%: the features used are statistically significant for the model. 

#### Assumptions of the Linear Relationship:

The assumptions are confirmed and the linear relationship is valid.

![image](https://user-images.githubusercontent.com/63364114/102094554-c3d10e00-3e22-11eb-827d-d895734d388e.png)

![image](https://user-images.githubusercontent.com/63364114/102094574-c895c200-3e22-11eb-8667-35f7bbd745a6.png)


![image](https://user-images.githubusercontent.com/63364114/102094593-ccc1df80-3e22-11eb-93f0-f397430d5f4e.png)


![image](https://user-images.githubusercontent.com/63364114/102094617-d0556680-3e22-11eb-8188-3ae2b85781c9.png)

![image](https://user-images.githubusercontent.com/63364114/102094628-d4818400-3e22-11eb-929a-716b9bb8646a.png)


## Contact me
[LinkedIn](https://linkedin.com/in/amelie-vogel-/)

[GitHub](https://https://github.com/amelie-vogel/)

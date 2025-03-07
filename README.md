<H3>NAME:Karnan K</H3>
<H3>REGISTER NO:212222230062</H3>
<H3>EX. NO.1</H3>
<H3>DATE:</H3>
<H1 ALIGN =CENTER> Introduction to Kaggle and Data preprocessing</H1>

## AIM:

To perform Data preprocessing in a data set downloaded from Kaggle

## EQUIPMENTS REQUIRED:
Hardware – PCs
Anaconda – Python 3.7 Installation / Google Colab /Jupiter Notebook

## RELATED THEORETICAL CONCEPT:

**Kaggle :**
Kaggle, a subsidiary of Google LLC, is an online community of data scientists and machine learning practitioners. Kaggle allows users to find and publish data sets, explore and build models in a web-based data-science environment, work with other data scientists and machine learning engineers, and enter competitions to solve data science challenges.

**Data Preprocessing:**

Pre-processing refers to the transformations applied to our data before feeding it to the algorithm. Data Preprocessing is a technique that is used to convert the raw data into a clean data set. In other words, whenever the data is gathered from different sources it is collected in raw format which is not feasible for the analysis.
Data Preprocessing is the process of making data suitable for use while training a machine learning model. The dataset initially provided for training might not be in a ready-to-use state, for e.g. it might not be formatted properly, or may contain missing or null values.Solving all these problems using various methods is called Data Preprocessing, using a properly processed dataset while training will not only make life easier for you but also increase the efficiency and accuracy of your model.

**Need of Data Preprocessing :**

For achieving better results from the applied model in Machine Learning projects the format of the data has to be in a proper manner. Some specified Machine Learning model needs information in a specified format, for example, Random Forest algorithm does not support null values, therefore to execute random forest algorithm null values have to be managed from the original raw data set.
Another aspect is that the data set should be formatted in such a way that more than one Machine Learning and Deep Learning algorithm are executed in one data set, and best out of them is chosen.


## ALGORITHM:
STEP 1:Importing the libraries<BR>
STEP 2:Importing the dataset<BR>
STEP 3:Taking care of missing data<BR>
STEP 4:Encoding categorical data<BR>
STEP 5:Normalizing the data<BR>
STEP 6:Splitting the data into test and train<BR>

##  PROGRAM:
### Import Libraries
```
from google.colab import files
import pandas as pd
import io
from sklearn.preprocessing import StandardScaler
from sklearn.preprocessing import MinMaxScaler
from sklearn.model_selection import train_test_split
```
### Read the dataset
```
df=pd.read_csv("/content/Churn_Modelling.csv")
print(df)
```
### Check the missing data
```
df.isnull().sum()

df=df.drop(['Surname', 'Geography','Gender'], axis=1)
df.fillna(df.mean().round(1), inplace=True)
df.isnull().sum()
```
### Split the dataset
```
X=df.iloc[:,:-1].values
print(X)
y=df.iloc[:,-1].values
print(y)
```
### Check for duplicates
```
df.duplicated()
df.describe()
```
### Normalize the dataset
```
scaler=MinMaxScaler()
df1=pd.DataFrame(scaler.fit_transform(df))
print(df1)
```
### Training and testing model
```
X_train ,X_test ,y_train,y_test=train_test_split(X,y,test_size=0.2)
print("X_train\n")
print(X_train)
print("\nLenght of X_train ",len(X_train))
print("\nX_test\n")
print(X_test)
print("\nLenght of X_test ",len(X_test))
```


## OUTPUT:

### Data checking:

![Screenshot 2025-03-07 114230](https://github.com/user-attachments/assets/0f39ad96-559b-4276-96d7-2a96607b4b0a)

### Missing Data:

![Screenshot 2025-03-07 114243](https://github.com/user-attachments/assets/baca98bf-2148-4285-8591-7c2d8b36f909)

### Vakues of 'X':

![Screenshot 2025-03-07 114254](https://github.com/user-attachments/assets/0822dc9e-17af-4548-820f-2f79a521c8e2)

### Vakues of 'Y':

![Screenshot 2025-03-07 114259](https://github.com/user-attachments/assets/9d6130b2-1df4-40ef-85e2-d54fa4674ecc)

### Outliers:

![Screenshot 2025-03-07 114315](https://github.com/user-attachments/assets/cb02d976-c080-4395-9ac5-2294278b346d)

### Normalize the dataset:

![Screenshot 2025-03-07 114324](https://github.com/user-attachments/assets/3f1fc74d-0945-4381-814c-a4c1bf96e0db)

### Training and testing model:

![Screenshot 2025-03-07 114334](https://github.com/user-attachments/assets/f7ca8f32-7fc8-4d0a-ae44-b83500bd721c)

## RESULT:
Thus, Implementation of Data Preprocessing is done in python  using a data set downloaded from Kaggle.



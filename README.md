# 120-years-Olympics

Dataset https://www.kaggle.com/datasets/heesoo37/120-years-of-olympic-history-athletes-and-results

## Tool and Language
* Google Colab
* Phyton

## Libraries
* pandas
* numpy
* mathplotlib
* seaborn
* sklearn, RandomForestClassifier

## Brief
The dataset contains historical dataset on the modern Olympic Games, including all the Games from __Athens 1896 to Rio 2016s__. The shape of data set consist of more than 270000 rows and 15 columns. The dataset was scrape by RGRIFFIN from www.sports-reference.com in May 2018. In this project we will explore the data set to get insight and find important statistic then we will create a model to predict from the physical of the athlete and which sport they participate to.

The notebook consist of
* Data Preprocessing
* Data Wrangling and Overview
* Data Analysis

#### Data Preprocessing
Data preprocessing can help identify and correct errors or inconsistencies in the data, such as missing values, duplicates, or incorrect data types. This can help ensure that the model is trained on accurate and reliable data. In this project, we will drop null values. Duplicate values could be important such same athlete can participate in different category of sport eg, Usain Bolt can participate in 100 meters and 4×100 metres relay.

Head of the dataframe/table. `df.head(2)` wil return head of the dataframe, the value 2 can be change as it represent n.

![image](https://user-images.githubusercontent.com/55817845/209832625-02a30403-087b-4d67-a2f0-18beaef90d22.png)

Sum of the null values. `df.isnull().sum()` will return all the null values for each colums

![image](https://user-images.githubusercontent.com/55817845/209833191-38c58c25-14b0-41e8-b184-f9843d1435af.png)

`df.dropna(inplace=True)` will drop all null values for each column and resuse `df.isnull().sum()` to check the null values.

![image](https://user-images.githubusercontent.com/55817845/209833793-97148d91-318b-4552-b297-8cd12d73cf89.png)


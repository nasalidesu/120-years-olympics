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

#### Data Overview
##### Countries with most participations including Winter and Summer Olympic

![image](https://user-images.githubusercontent.com/55817845/209835507-051c919c-bb2b-4f4d-97ed-3c40c44cefd7.png)

##### Countries with most medals
![image](https://user-images.githubusercontent.com/55817845/209835879-10f95c0d-08a2-4211-9e6d-ba9cb767898c.png)

##### Distribution medals of famous countries
![image](https://user-images.githubusercontent.com/55817845/209842783-4f32bc47-d2bf-4674-bdc9-33ae85303269.png)

##### Most held sport category during Summer Omplypic
![image](https://user-images.githubusercontent.com/55817845/209842928-ce0ff6bb-0a46-4e4d-a06f-2a2ef8c122a7.png)

##### Olympic timeline and 'Big Incident'
![image](https://user-images.githubusercontent.com/55817845/209843123-13e133c0-ca8a-4955-a15c-c34e99e6ee71.png)

##### Pairplot of modern day Olympic
![image](https://user-images.githubusercontent.com/55817845/209843548-6178be64-2b81-47df-a2fb-8fa502ad8d7a.png)


#### Analysis 1 - Which of the countries is the best at the football sport? (Descriptive)
![image](https://user-images.githubusercontent.com/55817845/209844171-3cba4435-ec86-4d9c-99d5-9a70758e5ffd.png)

In football sports including woman and men, USA has won 4 times gold medals over the years Olympic event organized followed by Hungary with 3 times. Argentina, Uruguay and Soviet Union shared the same number of gold medal with 2 times winning the football sport. It must be note that this category include men and women.

Why dont we analyze how many times these gold medalist countries participate in total for football games in Olympics.
![image](https://user-images.githubusercontent.com/55817845/209844370-179cb295-88fd-489d-9394-59e0bb8904ef.png)

#### Analysis 2 - Given the summer season, list the cities that have sports during that time? (Exploratory)
![image](https://user-images.githubusercontent.com/55817845/209844465-a823124d-a8f7-4c53-bed4-bf6059cd7d72.png)

There are 23 city already organized the summer Olympic which London (United Kingdom) and Athen (Greece) 3 times each. Most of the sport held during the year Olympic was held in the London are Football and Basketball including men and women.

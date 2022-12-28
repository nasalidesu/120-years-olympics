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

#### Analysis 3 - Does the increment of the age of the athletes increase the participation of the athletes? (Inferential)
![image](https://user-images.githubusercontent.com/55817845/209845142-421b977d-b6b2-4afd-9d92-64af8f753090.png)

The age distribution of the athletes were mostly between 20 - 40 years old. To analyze if there is relationship if the age requirement have an impact to the number of participant, we plot the box plot to see the range and the outliers of the athlete.

![image](https://user-images.githubusercontent.com/55817845/209845409-9aa31c28-0e80-4ce9-8015-2bf333249100.png)

Even though there are outliers at age more than 40s is still does not make the hyphothesis accurate which the age limit increase the number participations. Since there are no age limit in the olympics except the football team must be below 23 gymnastics must be above 16, it could not contribute to the partication instead we belive it contribute to the medal tally of the countries.

#### Analysis 4 - Which country has organized an Olympic event more than once? (Exploratory)
![image](https://user-images.githubusercontent.com/55817845/209847212-45ff2ca6-f0aa-43a0-a40d-416277805883.png)

Both cities London and Athens has already organized Summer Olympic 3 times in 2004 1906 1896(Athens) and 2012 1948 1908(London) respectively. Stockholm and Paris orgranized twiced where as Sankt Moritz, Innbruck and Lake Placid already orgranized Winter Olympics twice .Tokyo will organize next Summer Olympic in 2021 after it postponed on 2020 because of pandemic Covid-19.

#### Analysis 5 - Given the features of physicality of the athletes, is it possible to predict which sport that they belong to? (Predictive)
For modelling, we will take 'Sex','Age','Height','Weight','Sport' as our columns. The target will be 'Sports' and the rest will the features for prediction. We will use RandomForest Classifier for modelling.
It's a standard to split  the data into 70% of training and 30% of testing before inserting into the machine learning model.Moreover, it is also common to split the available data into two sets: a training set and a test set. The training set is used to train the model, while the test set is used to evaluate the performance of the model. Splitting the data in this way helps to prevent overfitting, which is when a model performs well on the training data but poorly on new, unseen data.

![image](https://user-images.githubusercontent.com/55817845/209848947-414f3941-832b-447b-93ec-fb90fbdb8f21.png)

The predicition is low. This could be explained since the target of the prediction is too many which is __56 targets__. The accuracy of the model can be increase if the traget is small.

Rather than taking all the type of sports, we limit the target into most popular sport watched during __Olympic which are Football, Swimming and Gymnastics__.

![image](https://user-images.githubusercontent.com/55817845/209849089-76cd9d12-600c-459e-b356-32c5733d5001.png)

The accuracy of the prediction increasing as the target is getting smaller. __87% accuracy__ for the model is quite good. This shows that indeed the target for previous model is to large as most of the athlete has optimum physicality to fit to almost type of sports.

![image](https://user-images.githubusercontent.com/55817845/209849166-f66ecc7c-1c0d-4455-a1c5-10686f1fd584.png)

As shown in the confusion matrix above, prediction for gymnastics athlete is quite low(30.8%) as true positive and most of the false positive fall into the football predictions. The prediction for Swimming athlete is very high (97.8) which is significant and almost 100%. The prediction for** Football** athlete is also high (89.8%)

The diagonal values is the true positive(correct predictions)
![image](https://user-images.githubusercontent.com/55817845/209849194-7b8c8742-4820-4a78-a642-25a0205c741b.png)

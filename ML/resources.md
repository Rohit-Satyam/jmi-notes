## AI and ML

AI is the set of tools for making computer behave intelligently. ML is most prevelant subset of AI.

## Supervised learning

# kNN
Exploratory Analysis of Wine dataset: [here](https://rawgit.com/allanbreyes/udacity-data-science/master/p3/submission.html)<br>
Tutorial 1: Click [here](https://rpubs.com/mayu2019/knn_WineQuality) <br>
```r
library(class)
library(caret)
library(e1071)
library(tidyverse)
set.seed(123)

setwd("C:/Users/Rohit Satyam/Downloads")
redWine <- read_csv("winequality-white.csv")
## Exploring categories
redWine %>% ggplot(aes(x = quality ))+ geom_histogram()
## trying to balance categories
redWine1 <- redWine %>% mutate(quality = ifelse(quality <= 5 ,"Low" , "High"))
redWine1$quality <- as.factor(redWine1$quality)
redWine1 %>% ggplot(aes(x = quality))+ geom_bar(width = 0.2)

## Data Preprocessing, using 70% data for training and rest for testing
wine_split <- caret::createDataPartition(redWine1$quality, p = 0.7 , list= FALSE)
wine_train <- redWine1[wine_split ,]
wine_test <- redWine1[-wine_split,]

#  Standardise data 

preProcValues <- preProcess(wine_train, method = c("center", "scale"))

wine_trainsc <- predict(preProcValues, wine_train )
wine_testsc <- predict(preProcValues, wine_test )

# Check processed data; Our dataset variables are standardised around mean zero with standard deviation as 1. Now we can train our model using the data.
summary(wine_trainsc$alcohol)

# usually the value of K is sqrt(nrow(redWine)) which is 69 approx

wineTrain <- wine_trainsc[,-12]
wineTest <- wine_testsc[,-12]

wineTrain_label <- wine_trainsc[,12 , drop = TRUE]
wineTest_label <- wine_testsc[,12 , drop = TRUE]

wineTrain_label <- wine_trainsc[,12 , drop = TRUE]
wineTest_label <- wine_testsc[,12 , drop = TRUE]

wineknns<- class::knn(train = wineTrain, test=wineTest, cl=wineTrain_label, k=69)
# Evaluating model performance

confusionMatrix(wineTest_label, wineknns)

## Our model accuracy is 75% which is less

######## Using Caret library #############

## Caret finds automatically vale of K using cross validation

# Setting up train controls;  3 separate 10-fold validations
repeats = 3
numbers = 10
tunel = 20



trnCntrl = trainControl(method = "repeatedcv",
                        number = numbers,
                        repeats = repeats,
                        classProbs = TRUE,
                        summaryFunction = twoClassSummary)

wineKnn <- train(quality~. , data = wine_trainsc, method = "knn",
                 trControl = trnCntrl,
                 metric = "ROC",
                 tuneLength = tunel)
## ROC was used to select the optimal model using largest value. k=11 was used

plot(wineKnn)

# Predict values using model 
test_pred <- predict(wineKnn ,wine_testsc, type = "prob")
# Reforctoring values in two classes
test_pred$final <- as.factor(ifelse(test_pred$High > 0.5 ,"High","Low"))
```

# Naive Bayes

The  `naivebayes`  package offers several ways to peek inside a Naive Bayes model.

Typing the name of the model object provides the  _a priori_  (overall) and conditional probabilities of each of the model's predictors. If one were so inclined, you might use these for calculating  _posterior_  (predicted) probabilities by hand.

Alternatively, R will compute the posterior probabilities for you if the  `type = "prob"`  parameter is supplied to the  `predict()`  function.
### Understanding the Priori and posterior  probability
1. [Source1](https://medium.com/analytics-vidhya/of-priors-and-posteriors-bayes-and-big-data-7d533b535df2)
2. 

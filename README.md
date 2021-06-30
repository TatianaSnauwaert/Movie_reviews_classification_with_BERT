# Movie_reviews_classification_with_BERT
## ML for Text project from Practicum by Yandex

The **goal** of this project was to develop a model that classifies movies reviews into positive and negative ones.

The F1 score on the test set should be at least 0.85. 

**This project's repo includes the following files:**

- The project's jupyter notebook (Movie_reviews_classification_with_BERT.ipynb);
- A pdf format of the notebook (Movie_reviews_classification_with_BERT.pdf);
- Input data (imdb_reviews.tsv);
- Project description from Practicum (Project_Description_ML_for_Texts.pdf);

We have completed the following steps in this project:

**1.Descriptive statistics**

**2.Data preprocessing**
   
We removed a few missing values and checked the data for duplicates. We have also normalized the reviews by removing  any digits, punctuations marks etc. and converting them to lower case letters. 
   
**3.EDA**

We analyzed both features and targets. We noticed an overall tendency of the growth of movie reviews over the years, with the peak being in 2006.
We found that most often there is just one or a few reviews per movie, although more than 400 movies (probably the most popular ones) have 30 reviews.
The overall distributions of ratings among the train and test sets are quite similar, we could probably use this feature in our model.

The distributions of the 2 classes of the train and test sets are very similar - it's a good sign, it means that a model trained on the train set should be predicting correctly on the test set as well.
We see that the classes are balanced - there is almost the same amount of positive as well as negative reviews.
    
**4.Splitting the data**

Data was split into train and test sets almost equally, according to the preexisting split.

**5.Model selection**

We have experimented with the 2 types of word embeddings - TF-IDF and BERT.
Besides, we tried 2 libraries for text preprocessing - nltk and spaCy.
Both Linear Regression and LightGBM models were used.

**6.Sanity check**

The test F1 score of the final chosen model is 31% higher than that of the dummy classifier model, that we used as a baseline to analyze the model quality. It means that the modeling was useful.

**7. Results**

Based on our research, **the NLTK+TFIDF+LR model showed the best test F1 score - over 88%.** The spaCy+TFIDF+LR model came close but its accuracy score it slightly lower. It also takes more preprocessing time, so we will recommend the first model to be the final one.

The BERT embedding also looks good but we should probably try a different ML algorithm with it in the future (LGBM, XGBoost, CatBoost) to get higher test F1 score. 

We have also tested our models on new reviews. It seems that all models predict better negative than positive reviews. Model 5 separates well the 2 classes with either very high or very low probability, respectively, however doesn't do so well when the review is more subtle. Our chosen model (model 2) misclassified 2 positive reviews, the rest was predicted correctly.

**Logbook**
The logbook of this project can be found [here](https://docs.google.com/spreadsheets/d/1SrGdReexaSEomJGS6yR6cRwJtHA_XqpprnLaE7B6Ayg/edit#gid=1947869430) (ML for Texts tab).
Total time spent on the project: 5.6 hours with a daily average of 1.51 hours working for 6 days.

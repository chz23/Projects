<img src="http://imgur.com/1ZcRyrc.png" style="float: left; margin: 20px; height: 55px">

# Project 3: Natural Language Processing - Classifying Definitions of Nouns and Adjectives


---
## Problem Statement
---

Constant exposure to a language through conversation, reading and writing is often the best long-term strategy to gain mastery. However, formal curricula and teaching methods are required to be explicit and objective-driven, thus leading to a structured, rules-based approach that is often seen as stifling and/or boring. To combat this, models can be built to mimic video games, where learners ‘compete’ against models. This may help learners view learning more positively by incentivising them to work harder so as to be able to win. This project represents the starting point, and it aims to use Natural Language Processing (NLP) to develop a model that can classify a given definition as either defining a noun or an adjective. Educators will be able to input word definitions and pit learners against the model to see who has a higher accuracy rate. In addition, much like how video games feature different levels of difficulty, the model can easily be tuned to the desired level of accuracy.

---
## Overview of Process
---

#### Introduction & Data Scraping

_Relevant notebook: 01_Introduction_and_Data_Scraping.ipynb_

This segment explores the objective of this project, how it compares to other NLP projects, as well as potential limitations and considerations. 

Following this, data scraping is carried out. Rationales for the websites used, as well as conditions put in place while scraping, are elaborated upon in the relevant sections of this document.


#### Exploratory Data Analysis (EDA)

_Relevant notebook: 02_EDA.ipynb_

Preliminary EDA is carried out in 3 main parts:
- length of definitions;
- prominent parts-of-speech (POS) by word class;
- prominent features by word class.


#### Modelling

_Relevant notebook: 03_Modelling_and_Applications.ipynb_

Based on a mixture of the EDA, logical reasoning as well as domain knowledge, data will be processed and models tuned accordingly.

A total of 4 models were explored: 
- Naive Bayes (NB) (part of the requirements for this project)
- Logistic Regression (LR)
- K-Nearest Neighbours (KNN)
- Random Forest (RF)

Prior to modelling, a brief overview of each model will be given, including potential advantages and limitations in the context of this project.

The models will then be assessed based on the following sets of scores:
| Metric | Applicable Dataset |
| --- | --- |
| CV | training |
| accuracy | training & test |
| specificity | test |
| recall | test |
| precision | test |
| f1 | test |


#### Explanatory Data Analysis (ExDA)

_Relevant notebook: 03_Modelling_and_Applications.ipynb_

After the final models are selected, explanatory data analysis will be carried out to explain how the models work and how some important differences may lead them to different conclusions.


#### Applications, Suggestions & Recommendations

_Relevant notebook: 03_Modelling_and_Applications.ipynb_

This final segment covers possible applications of the models, as well as potential extensions, future versions, etc.


---
## Inclusion of Parts-of-Speech (POS) in Data
---

Note that POS were included in the data that the models were eventually trained on as well. This is explained within the notebook itself, but the gist is that learning from POS allows the model to learn the inherent structures present in the definitions in the way it would be difficult to just based on the words.


---
## Models
---

After conducting EDA and fine-tuning of hyperparameters, the following models were selected:

### Naive Bayes

NB is part of the requirements of this project. That said, while it did not perform as well as LR, its performance is comparable to that of the other models. It has the additional advantages of being more easily interpretable and computationally efficient compared to KNN & RF, so it is a good choice to include regardless.

### Logistic Regression

In general, LR models performed better as compared to the rest. Like NB, it is computationally efficient and easily interpretable, and is thus a good pick for this project.

### Parameters used
| Parameter | NB | LR |
| --- | --- | --- |
| `min_df` | 10 | 30 |
| `max_df` | 0.65 | 0.7 |
| `alpha` | 1.5 | - |
| `C` | -| 1.0


### Scores
| Metric | NB | LR |
| --- | --- | --- |
| CV (mean) | 0.89 | 0.96 |
| accuracy (training) | 0.91 | 0.98 |
| accuracy (test) | 0.9 | 0.96 |
| specificity | 0.91 | 0.96 |
| recall | 0.89 | 0.95 |
| precision | 0.91 | 0.96 |
| f1 | 0.9 | 0.95 |

### Feature Importance

Feature importance was based on probabilities and coefficients for NB and LR respectively. Here are the relevant charts:

<img src="https://i.imgur.com/kay9zNq.png">

The chart above shows feature importance according to the NB model. As this is based on p(noun), the lower the value, the more indicative the feature is of adjectives, and vice-versa for nouns.

<img src="https://i.imgur.com/XqZcABV.png">

The chart above shows feature importance according to the LR model. As this is based on the coefficients (log-odds), negative values are associated with nouns, and vice-versa for adjectives.

Unlike the NB model, most of the features considered more significant by the LR model are parts-of-speech (POS). It is expected that this would not be the case for NB due to the general nature of POS - since they are essentially groupings of words, it is virtually impossible that an entire group is missing from a whole word class. Therefore, NB would not assign them as high probabilities. In fact, probabilties of features extracted from definitions would not change regardless of whether parts of speech are included in the model.

However, LR is more holistic. Since its equation has to balance all of the features, any 'movement' affects the coefficients across board. In this way, LR is able to learn from the inclusion of POS within the data. For example, consider the following phrases:
- 'the act of'
- 'the instance of'
- 'the state of'

All of them appear largely in definitions of nouns. Let's assume, for the sake of this example, that they rarely appear together. Without their relevant POS (determiner-noun-adposition), it would be difficult for the model the learn anything other than that they are very predictive of nouns. _With_ the inclusion of the POS, it will be a lot easier for the model to detect the underlying structure, because it would be able to detect that whenever each of these phrases appears in a definition, the same POS also appears. This way, it will be able to learn and model certain aspects of structure, and reflect these discoveries accordingly in the coefficients. This is likely why most of the key features for the LR model are actually POS.

---
## Applications of Models
---

### Applications

#### Friendly competition

The primary use of this model would be to serve as a 'competitor' to learners, who could be students or otherwise non-native speakers. For any given definition, the learner would classify it as either a noun or an adjective, and compare their answer against the model's classification. 

Naturally, for this to work out, there must be a 'correct' answer. In the context of the data we've been dealing with, it would necessitate, for example, the `df_word['word_class']` column to output the answer. Thus, the model would output two things: the correct answer from the dataset, as well as its predictions. 


#### Contextual clues - key skill taught in schools

The picking out of contextual clues is a skill that is increasingly emphasised upon in recent years in schools. In the context of this project, it would look something like this: "Why did you classify this definition as a noun? Which part or parts of the definition led you to this conclusion?" The main point of this is to encourage students to engage in close-reading (yet another important skill emphasised upon) as well as enable them to be able to explain their thought process, therefore improving logical-thinking as well as communication skills.

These models, being easily interpretable, can essentially do the same thing through feature importance. For example, in Naive Bayes, it's as simple as look at the probabilities of each distinct part in the definition. In other words, not only can students test their accuracy against the model, they can also check to see if they were able to pick out the most important clues (assuming the model classified it correctly).


#### Infinitely customisable

Learners vary greatly in terms of language ability as well as personal characteristics. Some students may appreciate and welcome tough challenges while others may shy away when they keep 'losing' to the model. Being models, customising accuracy rate is very doable. Therefore, it is possible to offer every learner a different 'difficulty level' depending on their preferences or needs.

### Limitations

This project features a small-scale model built on approximately 4,000 definitions all from the same source. 

First of all, this makes it difficult to achieve extremely high accuracy rates that may be needed in some cases, especially if a potential selling point is customisability. 

Secondly, dictionary definitions are very precise, which makes some of them potentially rather difficult to understand, which may in turn be confusing for the learner or unfair to them.

To tackle the above, a 'next version' of this model should ideally be trained on a much larger set of data from varying sources such that it is much easier for the model to generalise. 

In addition, it may be necessary for to have, for example, a function that isn't related to the data at all. Instead, it merely tweaks the class labels on a random basis to offer the 'illusion' of a model. This would be the most straightforward and reliable way of ensuring that we can cater to learners who want a model with extremely high accuracy levels. Of course, this is merely a short-term solution, because it wouldn't be a model at all, rather just a simple function that is unable to learn from data or generalise to unseen data.

### Further Extensions

If we think of this model as a blueprint, there may be many additional use cases for future versions of it.

#### Classifying user-defined definitions

If the model has been trained on an extremely large and diverse dataset, it may be possible for it to accept user-defined definitions as well. This could be rather fun for users, and the 'contextual clues' function (feature importance) can help users to understand why, for example, their definitions are not classified into the word class they intended it to be.

#### Other POS

If the quantity and quality of the data can be improved upon, it follows that the model would be able to handle many other types of classification as well.

#### Beyond language

With a sufficient amount of data, it could become possible for the model to classify all manner of things. For example, for a given 'definition' or description, it may be possible for the model to classify landforms taught in Geography.

### Conclusion

This model, while just a small-scale NLP project, has shown us that it _is_ possible for us to use modelling to make learning and/or informal assessment more engaging. In addition, it has the benefit of harnessing technology and potentially being a good teaching resource for educators as well. With some tweaking, and the resources to improve it further, it could potentially become a power tool for the teaching and learning of not just language, but many other areas as well.
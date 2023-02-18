<img src="http://imgur.com/1ZcRyrc.png" style="float: left; margin: 20px; height: 55px">

# Project 2: Data Analysis of HDB Housing Prices in Singapore

---
## Problem Statement
---

House hunting in Singapore can be a tiring ordeal, especially when one is looking to both buy and sell. The problem is especially pronounced for working adults who have to manage it in addition to a full-time job and, for some, caretaking of family members. This project aims to analyse and identify key features impacting resale prices of public housing (HDB flats) in Singapore so that prospective buyers and/or sellers will be able to avoid wasting unnecessary time and effort on the process, as well as be able to gauge whether prices being quoted are reasonable. A linear model will be built and evaluated accordingly to ensure that the selected features are appropriate and informative.

---
## Overview of Process
---

### Data Cleaning

Standard data cleaning was carried out for both the `train.csv` and `test.csv` files. The most notable part of this process would be the method used to deal with null values, which will be shown in the relevant section.

### Features Selection & Exploratory Data Analysis (EDA)

With 76 (excluding `resale_price`) features from the original dataset, there was a need to filter out features that are less relevant / inferior predictors of resale price. During this process, an additional feature, based on the original features available, was included to improve accuracy. 

In addition, it became apparent that a separate model for the most expensive resale flats might be useful. Thus, two models - high-end and regular - will be built.

### Modelling

Based on the above, the dataset was split into 2 parts - 'high-end outliers' and the remaining flats. For each of these split datasets, predictive models were created using linear regression, ridge regression and LASSO regression. For each model, a set of predictions for resale price for the `test.csv` file was generated and saved as csv files. These files were then submitted to kaggle.

Finally, the models were evaluated based on their $R_2$ scores (only available for `train.csv`) and RMSE values. Based on these, the final selection of models was made.

### Conclusion & Recommendations

## Data Dictionary

Based on what was done, recommendations were given to the target audience, prospective flat owners and buyers.

This is a summary of features that were used in the models. Out of 76 predictive features, 14 were selected due to their relevance and impact on resale prices.

Justifications for the selection of these features, as well as omission of the rest, are provided in the file `02_Feature-Engineering.ipynb` that is located within the same folder.

| Feature | Type | Description | No. Labels (Categorical) | Unit of Measurement |
| --- | --- | --- | --- | --- |
| `flat_type` | Categorical | Flat type of resale flat. | 7 | - |
| `flat_model` | Categorical | Flat model of resale flat. | 20 | - |
| `Tranc_Year` | Categorical | Year that the resale flat was transacted. | 10 | - |
| `planning_area` | Categorical | Planning area that resale flat is located in. | 32 | - |
| `bus_interchange` | Categorical | boolean value denoting if the resale flat's nearest MRT station has a bus interchange. | 2 | - |
| `mrt_interchange` | Categorical | boolean value denoting if the resale flat's nearest MRT station is an MRT interchange.  | 2 | - |
| `floor_area_sqm` | Numerical | Floor area of the resale flat. | - | squared metres ($m^2$) |
| `mid` | Numerical | Middle value of the range of levels that the resale flat is located in; used as an approximation of its level. | - | - |
| `max_floor_lvl` | Numerical | Number of levels in the resale flat's block. | - | - |
| `Mall_Nearest_Distance` | Numerical | Distance from the resale flat to the nearest mall. | - | metres (m) |
| `Mall_Within_500m` | Numerical | Number of malls within 500m of the resale flat. | - | - |
| `Hawker_Nearest_Distance` | Numerical | Distance from the resale flat to the nearest hawker centre. | - | metres (m) |
| `mrt_nearest_distance` | Numerical | Distance from the resale flat to the nearest MRT station. | - | metres (m) |
| `hdb_age_at_tranc` | Numerical | Age of the resale flat as at transaction. | - | years |

## Summary of Analysis (Key Features)

### Floor Area

Floor area is usually a very important determinant of housing price, and this is especially true of tiny Singapore which, for better or worse, is amongst the densest countries in the world. It is expected that floor area is positively correlated with resale price.

### Remaining Lease Period

All HDB flats are subject to a 99-year lease period without exception. This likely impacts valuation prices and may even be a point of negotiation between prospective buyers and sellers. It is expected that remaining lease period is inversely correlated with resale price.

### Location

Although Singapore is modest in size, proximity to central areas still matters. Flats located at or closer to the city centre tend to be more expensive. The most obvious reason would be land valuation, in that such areas tend to be seen as prime areas with corresponding high land valuations. 

From the buyer's point of view, practical reasons for higher prices include connectivity (multiple train lines, good selection of buses, etc.), proximity to the CBD (where many people work at) and selection of amenities (many shopping malls, meal options, etc.). 

Finally, in general, regardless of country, such houses also tend to be viewed as more prestigious, and may automatically fetch higher prices. Thus, it is expected the more centrally located a flat is, the higher the resale price.

### Connectivity & Amenities

For the average buyer, amenities probably do factor into decision-making, but the extent depends on type of amenity and the buyer themself. For example, while the presence of pavillions is unlikely to matter at all, proximity to the nearest MRT station probably does - especially for those who don't plan on driving everywhere. In particular, specific to the local context, proximity to either bus stops and/or MRT stations should be at least a point of consideration since commuting via public transport is very common.

## Recommendations & Conclusions

### Watch out for existing trends

Unfortunately, housing prices don't follow a particular year-on-year pattern. Regardless of what the model says, it's always going to be important to keep abreast of current economic trends, world news, government policies, etc. They _do_ have an impact on housing prices, and often not a small one, either.

### Be careful when interpreting the model

Despite having already been explained above, this point bears additional emphasis. Going at it from a purely mathematical point of view is unlikely to bode well, especially when looking at categorical variables. When attempting to interpret the coefficients, it's important to tie it back to reality to examine how this may _explain_ certain phenomenons, rather than assuming it to be the truth to abide by.

### These features are still important

There was a warning about coefficients above, but there's always a bright side, of course. The model scores and RMSE values are in fact rather reasonable. It does, at the very least, indicate that the feature selection process was largely a success, and that these features are the ones to look out for, although their relative importance will ultimately depend on the buyer and/or seller.

### Consider the buyer's profile

If you're looking to _sell_, it would be good to know your target audience. This may be something you come up with on your own, or it could be something that you come up with, based on suitability. After gaining some insights into housing prices in Singapore, it may be worthwhile to examine your house and think of who it's likely to attract. House buying and/or selling can be a stressful and time-consuming process - being able to correctly identify the best target audience for your needs is likely to reduce the amount of time spent on the process, and this in turn reduces the chances of you "settling", ie. running out of time (or patience) and accepting a deal that you shouldn't.

### Compromise!

You can't have the best of both worlds, much less _all_ worlds. Of the recurring trends within the EDA, there's one that should be obvious - houses are never priced _lower_ than what you'd expect. Unfortunately, there's no Shopee for resale flats. Rather than search endlessly for something that doesn't exist, it's better to think about what matters to you, then circle back to this model and see if you have to readjust those priorities. Doing it properly can be the difference between getting a flat you like and are comfortable with, and going with something you can't actually afford. For example, there's little reason to insist on staying within 500m to the MRT station if a flat merely a 100m away goes for $50K cheaper. How do you even know in the first place, without looking through every single listing, that something like this may exist? The answer lies in these notebooks that you've just read - internalise the findings, and apply them accordingly.

### What's on the inside matters, too

Some things were not covered in this process, because they weren't present as part of the dataset. But they are important, and increasingly so. A good example is interior design. There's a practical aspect to it, too - buyers look at houses and wonder how much extra money they would have to fork out for renovations. You don't even necessarily have to _redo_ your existing house, which wouldn't make sense, but you can certainly spruce it up and make it as presentable as possible. Do your research - instead of simply being amazed by all the oddly high-value resale flats being transacted, try to draw a link between them - what do they have in common? You can always start by using the features from the model as a checklist and branching out from there.

### Conclusion

House-hunting can be a tedious process, and downright a nightmare at times. The purpose of the features selection and modelling process was to discover key features and patterns that prospective buyers and sellers would be able to make use of to reduce their burden. Understanding _why_ certain features impact housing prices is key to unlocking the secrets behind the average buyer's or seller's decision-making process, which would better equip them to 'one-up' the house hunting (buying _and_ selling) process by avoiding the hunting altogether - and simply rely on data and knowledge.
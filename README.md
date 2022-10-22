# London-energy-consumption-prediction

As an electricity supplier you want to be able to predict the energy
consumption as accurate as possible for each customer, so that they do
not have to pay or get back so much afterwards.

The idea is to predict the current energy consumption of a single household in
London based on several different features. The prediciton of single households also could be added up to predict the total amount of energy consumption of London.

# Dataset
A dataset with which it is possible to experiment is the “Smart meters in London” - Dataset, available on kaggle:
https://www.kaggle.com/jeanmidev/smart-meters-in-london

It contains the energy consumption readings for a sample of 5,567 households in London for each 30 minutes from 2011-2014. In total it has about 167 Million data samples and takes rouhly 10 Gigabytes of space. 
It has features like:

* household_id, current energy consumption, timestamp, type of power supplier contract, ACORN-group (A-U, depends on 74 unique properties:
  age, house type & size, hobbies, monthly income...)
 
  "Acorn is a powerful consumer classification that segments the UK population." -https://acorn.caci.co.uk/
  
  
* Separately: Weather & holiday information
* For each ACORN property: Distribution over ACORN-groups


# Overall conclusion and possible improvements
Our goal was to predict the currentenergy consumption of a single household in London. For that we have explored a small part of publicy available dataset to confirm that it contains meaningful and almost complete data. Some features like some ACORN-groups were underrepresented though. To understand the influence of weather data on energy consumption, we merged the weather data into the energy-consumption data and interpolated the missing values. We calculated the relative distribution of features over the ACORN-groups from the aboslute one. Therefore we were able to determine the most likely ACORN-group given a set of features from the ACORN-groups distribution table. To be able to use the dataset for prediction algorithms and correlation analysis, we transformed the categorical features to one-hot-encoded ones. We pointed out a few explainable correlations within the dataset and checked for variables indepence.

The chosen algorithms didnt improve the result alot compared to the average guessing approach, which resulted in a mean error of 0.2477 kWh. The support vector machine outperfomed the linear regression model achieving a mean error of 0.2068 kWh. The extreme boost gradient algorithm performed unexpected a little worse.

To further improve the performance one should probaby use the whole dataset with 112 files instead of only 12. It wasnt possible in this case because some calculations and modifications would have taken several hours. Using the whole dataset also could help to balance the ununderrepresented features out. Another option would be to do a grid search over all features, so one could be sure about which combination of features would work and which wouldn´t. That would be a quite timeconsuming task of course, especially if the whole dataset with its 112 file is used.

Also it is possible that energy consumption depends on the features but only to a little extend, so that we can make only a vague guess about the current energy consumption of a specific household and it is not possible to predict it with a higher accuracy.

After all one can say our model works better than an average guess and seems to have understood the influence of some features as we have seen for example that temperature influence the prediction in an explainable way. We have shown dummy user data can be used to actually predict the current energy consumption of a specific household.

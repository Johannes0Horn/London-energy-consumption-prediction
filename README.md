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
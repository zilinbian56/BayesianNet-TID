# Traffic Incident Duration (TID) Prediction: An Introduction

Traffic Incident Duration (TID) refers to the time elapsed between when a traffic incident occurs and when it is resolved. This encompasses the entirety of the incident management process, from the moment of the incident's occurrence to the final resolution, including detection, response, clearance and site recovery times.

The process of TID is shown as follows:
 
 <p align="center">
      <img width="50%" src="https://github.com/zilinbian56/BayesianNet-TID/blob/6ab8a186b9e5bd3164fdee83e079ed24e95db198/Figure/Timeline%20of%20TID.png"></a>
 </p>


Predicting Traffic Incident Duration accurately is of paramount importance for several reasons:

1. **Enhanced Traffic Management**: Accurate predictions of incident durations allow traffic management centers to make informed decisions about deploying resources and managing traffic disruptions.

2. **Improved Incident Response**: Predicting the duration of traffic incidents enables emergency services and first responders to better plan their operations, potentially reducing the incident's overall duration.

3. **Informed Travelers**: Travelers can be provided with better information regarding expected delays and alternative routes, thus mitigating the impact of incidents on their travel plans.

However, TID prediction is inherently challenging due to the uncertain nature of traffic incidents. Factors influencing TID include incident characteristics (type, severity, location), environmental conditions (time of day, weather), and response attributes (response time, recovery strategy).

In this context, machine learning and probabilistic graphical models such as Bayesian Networks can play a significant role in effectively modeling and predicting TID by handling uncertainty and capturing complex relationships among influencing factors.

# Traffic Incident Duration Prediction using Bayesian Networks

This README outlines how to use Bayesian Networks (BN) for predicting Traffic Incident Duration (TID).

## References

The BN model and the TID prediction approach were inspired by and built upon the ideas presented in the following work:

1. Ozbay, K., & Noyan, N. (2006). [Estimation of incident clearance times using Bayesian Networks approach](https://www.sciencedirect.com/science/article/pii/S0001457505002009?casa_token=8Jj4Vss1w-MAAAAA:9BSQ7A1TuJYxhdad2cStk5U0eNZFPRjDMxTfzIdP1rNcB2ZmImMZG3lUhFz8_VX-CvqE7evg). *Accident Analysis & Prevention*, 38(3), 542-555. Elsevier. 
2. Demiroluk, S., & Ozbay, K. (2014). [Adaptive learning in Bayesian Networks for incident duration prediction](https://journals.sagepub.com/doi/pdf/10.3141/2460-09?casa_token=LtCbpoJrIRkAAAAA:Kqhh-oLqBAd7wdgnwx6yoIkHl97K27fVLgkBequJh0JjXNcoVJFYW_YAjvHaUHXhlLx59cBumrJcqQ). *Transportation Research Record*, 2460(1), 77-85. SAGE Publications Sage CA: Los Angeles, CA. 


## Table of Contents
1. [Introduction to Bayesian Networks](#introduction-to-bayesian-networks)
2. [Motivation for using Bayesian Networks in TID Prediction](#motivation-for-using-bayesian-networks-in-tid-prediction)
3. [Data Description](#data-description)
4. [Process of using Bayesian Networks for TID Prediction](#process-of-using-bayesian-networks-for-tid-prediction)
5. [Some quick results of using Bayesian Networks for TID Prediction](#some-quick-results-of-using-bayesian-networks-for-tid-prediction)

## Introduction to Bayesian Networks
Bayesian Networks (BN), also known as belief networks, are graphical models used to represent knowledge about an uncertain domain. It's an acyclic directed graph consisting of nodes representing variables, and edges representing dependencies between variables. Each node has a probability function that takes as input a particular set of values for the node's parent variables, and gives (as output) the probability of the variable represented by the node.

## Motivation for using Bayesian Networks in TID Prediction

Bayesian Networks (BN) are suitable for this task for several reasons:

1. **Ability to Handle Uncertainty**: Traffic incidents are inherently uncertain and dependent on a wide range of factors. BN's can manage this uncertainty effectively.

2. **Incorporation of Domain Knowledge**: BN's allow the integration of expert knowledge into the model in a transparent and interpretable way.

3. **Cause-Effect Relationships**: BN's can capture causal relationships between variables, which is critical in understanding and predicting traffic incidents.

In the notebook, you will see 

## Data Description

The dataset used in this project includes traffic incident records within New York City with various attributes. The main target variable is 'Duration (min)'. The target variable is converted into a categorical variable named 'Duration_class', class 0: 0-30min, class 1: 30-60min, class 2: 60-90min, class 3: larger than 90min. 
The independent variables that influence the duration include:

1. `Direction`: Direction of the incident, 0: both directions, 1: east, 2: west, 3: south, 4: north, 5: no information.

2. `County`: The county where the incident occurred, 0: Manhattan, 1: Kings, 2: Queens, 3: Bronx, 4: Richmond.

3. `Year`: The year of the incident.

4. `TOD`: Time of day (peak hour or off-peak) when the incident occurred, 0: off-peak, 1: peak hour.

5. `PeakHour`: The day of the week when the incident occurred.

6. `DayofWeek`: The day when the incident occurred, 0: weekday, 1: weekend.

7. `MonthofYear`: The season of month when the incident occurred, 0: psring and fall, 1: summer, 2: winter.

8. `Injury involved`: Whether there is injury involved in the incident, 0: no history, 1: injuries involved.

9. `Truck involved`: Whether there is truck involved in the incident, 0: no history, 1: heavy vehicle involved.

10. `Lane Closure Type`: How many travel lanes closed due to the incident, 0: zerao travel lane, 1: one travel lane, 2: more than two travel lanes, 3: all travel lanes.

12. `Fire involved`: Whether there is fire involved in the incident, 0: no history, 1: fire involved.

Each record in the dataset represents a unique traffic incident.


## Process of using Bayesian Networks for TID Prediction

Here are the steps to use Bayesian Networks for predicting Traffic Incident Duration:

1. **Data Preprocessing**: First, preprocess the data. This may involve cleaning the data, handling missing values, and converting categorical variables into a suitable numerical format.

2. **Network Structure Learning**: Next, learn the structure of the Bayesian Network. This involves defining the nodes (variables) and edges (dependencies) of the network. 

3. **Parameter Learning**: Once the structure is defined, learn the conditional probability Distributions (CPDs) for each node in the network. 

4. **Model Validation**: Validate the model by comparing the predictions with the actual values for a subset of data. Use appropriate metrics for evaluation.

5. **Prediction**: Finally, use the learned Bayesian Network to make predictions about Traffic Incident Duration. 

## Some quick results of using Bayesian Networks for TID Prediction

Here are some quick results of using BNs for predicting TID:
1. **Learned Network Structure**: the structure learning method used in this study is Chow-Liu ('cl'), the score type used in this study includes ['k2', 'bds', 'bic', 'bdeu'] for model comparison, and obtained the structure with the highest score.
The learned structure is shown as below:

 <p align="center">
      <img width="50%" src="https://github.com/zilinbian56/BayesianNet-TID/blob/d46e483c508cc7a84400f0b762b9b971859682bf/Figure/BN_structure.png"></a>
 </p>

2. **Learned Parameter**: the estimator used for parameter learning is BayesianEstimator, the prior type used is 'bdeu'.
3. **Model Validation**: The model performance of validation data set has been evaluated using Precision, Recall and F1-score for each class. Here is a summary of these metrics for our model:

|   | Precision | Recall | F1-Score |
|---|-----------|--------|----------|
| Class 0 | 0.99579832 | 0.96734694 | 0.98136646 |
| Class 1 | 0.93600000 | 1.00000000 | 0.96694215 |
| Class 2 | 1.00000000 | 0.64615385 | 0.78504673 |
| Class 3 | 0.66666667 | 1.00000000 | 0.80000000 |

The array of size `[245, 117, 65, 44]` represents the support for each class, that is, the number of instances in each class in the validation set.

**Note**: The classes in the table above refer to different categories of TID defined in the 'Data Description' section. 

4. **Prediction**: the prediction performance of BNs will be evaluated using AUC-ROC curves for each 'Duration_class':
<p float="left">
  <img src="/Figure/AUC_ROC_Class0.png" width="220" />
  <img src="/Figure/AUC_ROC_Class1.png" width="220" /> 
  <img src="/Figure/AUC_ROC_Class2.png" width="220" />
  <img src="/Figure/AUC_ROC_Class3.png" width="220" />
</p>


For a practical guide on how to implement these steps, refer to the associated Jupyter notebook and codebase in this repository.

Happy coding and good luck with your predictions!

## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file

# Traffic Incident Duration (TID) Prediction: An Introduction

Traffic Incident Duration (TID) refers to the time elapsed between when a traffic incident occurs and when it is resolved. This encompasses the entirety of the incident management process, from the moment of the incident's occurrence to the final resolution, including detection, response, recovery, and site clearance times.

The process of TID is shown as follows:
 
 <p>
      <img width="70%" src="https://github.com/zilinbian56/BayesianNet-TID/blob/6ab8a186b9e5bd3164fdee83e079ed24e95db198/Figure/Timeline%20of%20TID.png"></a>
 </p>


Predicting Traffic Incident Duration accurately is of paramount importance for several reasons:

1. **Enhanced Traffic Management**: Accurate predictions of incident durations allow traffic management centers to make informed decisions about deploying resources and managing traffic disruptions.

2. **Improved Incident Response**: Predicting the duration of traffic incidents enables emergency services and first responders to better plan their operations, potentially reducing the incident's overall duration.

3. **Informed Travelers**: Travelers can be provided with better information regarding expected delays and alternative routes, thus mitigating the impact of incidents on their travel plans.

However, TID prediction is inherently challenging due to the uncertain nature of traffic incidents. Factors influencing TID include incident characteristics (type, severity, location), environmental conditions (time of day, weather), and response attributes (response time, recovery strategy).

In this context, machine learning and probabilistic graphical models such as Bayesian Networks can play a significant role in effectively modeling and predicting TID by handling uncertainty and capturing complex relationships among influencing factors.

# Traffic Incident Duration Prediction using Bayesian Networks

This README outlines how to use Bayesian Networks (BN) for predicting Traffic Incident Duration (TID). 

## Table of Contents
1. [Introduction to Bayesian Networks](#introduction-to-bayesian-networks)
2. [Motivation for using Bayesian Networks in TID Prediction](#motivation-for-using-bayesian-networks-in-tid-prediction)
3. [Data Description](#data-description)
4. [Process of using Bayesian Networks for TID Prediction](#process-of-using-bayesian-networks-for-tid-prediction)

## Introduction to Bayesian Networks
Bayesian Networks (BN), also known as belief networks, are graphical models used to represent knowledge about an uncertain domain. It's an acyclic directed graph consisting of nodes representing variables, and edges representing dependencies between variables. Each node has a probability function that takes as input a particular set of values for the node's parent variables, and gives (as output) the probability of the variable represented by the node.

## Motivation for using Bayesian Networks in TID Prediction

Traffic Incident Duration (TID) prediction is a critical aspect of Intelligent Transportation Systems. Accurate TID prediction can help in effective traffic management and reduce the negative impact of incidents on traffic flow.

Bayesian Networks (BN) are suitable for this task for several reasons:

1. **Ability to Handle Uncertainty**: Traffic incidents are inherently uncertain and dependent on a wide range of factors. BN's can manage this uncertainty effectively.

2. **Incorporation of Domain Knowledge**: BN's allow the integration of expert knowledge into the model in a transparent and interpretable way.

3. **Cause-Effect Relationships**: BN's can capture causal relationships between variables, which is critical in understanding and predicting traffic incidents.

In the notebook, you will see 

## Data Description

The dataset used in this project includes traffic incident records with various attributes. The main target variable is 'Incident Duration'. The independent variables that influence the duration include:

1. `Incident Type`: Type of incident, such as an accident, roadwork, or breakdown.

2. `Time of Day`: The time when the incident occurred, divided into various time intervals.

3. `Weather Condition`: The weather condition during the incident.

4. `Road Type`: Type of road where the incident occurred, such as highway, arterial road, etc.

5. `Day of the Week`: The day of the week when the incident occurred.

Each record in the dataset represents a unique traffic incident.

**NOTE**: Ensure your data is clean and properly formatted before using it with Bayesian Networks. Missing or inconsistent data can lead to inaccurate predictions.

## Process of using Bayesian Networks for TID Prediction

Here are the steps to use Bayesian Networks for predicting Traffic Incident Duration:

1. **Data Preprocessing**: First, preprocess the data. This may involve cleaning the data, handling missing values, and converting categorical variables into a suitable numerical format.

2. **Network Structure Learning**: Next, learn the structure of the Bayesian Network. This involves defining the nodes (variables) and edges (dependencies) of the network. 

3. **Parameter Learning**: Once the structure is defined, learn the conditional probability tables (CPTs) for each node in the network. 

4. **Model Validation**: Validate the model by comparing the predictions with the actual values for a subset of data. Use appropriate metrics for evaluation.

5. **Prediction**: Finally, use the learned Bayesian Network to make predictions about Traffic Incident Duration. 

For a practical guide on how to implement these steps, refer to the associated Jupyter notebook and codebase in this repository.

Happy coding and good luck with your predictions!

## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file

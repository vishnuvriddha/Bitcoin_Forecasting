# BitPredict (Time-Series Project) Bitcoin Market Price Prediction

**NOTE** I've replicated this from the github page of mrdbourke, this is not my original work. I did this in his course where he taught me to do the same


Time series problems are those which deals with data over time. Such as growth of population in a country or the amount of electricity used by a nation. Timeline can either be very short and in seconds or be very long in decades. A forecasting problems like ours predicts future demands and settles the matter likewise.




We will import data and visualize it first, this is the price of bitcoin for almost a decade from 2014.

![image](https://user-images.githubusercontent.com/86077149/148679998-027326d6-2983-4a15-a661-daf4f55f9c0b.png)


We can then break the data into test and train set and visualize them like this:

![image](https://user-images.githubusercontent.com/86077149/148680118-e6e17bf8-6e9d-4736-a779-f5ca6d3dd8f9.png)

Before we discuss what modelling experiments we're going to run, there are two terms you should be familiar with, horizon and window.

* **horizon** = number of timesteps to predict into future
* **window** = number of timesteps from past used to predict horizon

Experiments we are running (Horizon/Window)

0. Naive model (baseline)
1. Dense model 1/7
2. LSTM 1/7
3. N-Beats 1/7
4. Ensemble (multiple models optimized on different loss functions) 1/7

### Model 0: Naive Baseline Model

This is what our naive forecast looks like :
![image](https://user-images.githubusercontent.com/86077149/148680372-c2d037a0-16a9-46f3-b0b0-21612be70ba4.png)

### Model 1: Dense model 

This is what our Dense model forecast with Horizon of 1 and Window of  7 looks like:

![image](https://user-images.githubusercontent.com/86077149/148680657-0fab6dca-1028-4e16-b774-71b74f262287.png)

#### Compare Dense model and Naive model :

Our naive model is better as compared to our dense model on the metrics of rmse and mae.

![image](https://user-images.githubusercontent.com/86077149/148681087-f88ef81f-eb20-40be-9869-5be7ad5e2ae1.png)

### Model 2 : Recurrent Neural Network (Long Short Term Memory) Model

This is what our RNN (LSTM) model (horizon = 1, window = 7) forecast looks like:

![image](https://user-images.githubusercontent.com/86077149/148681227-451fe2a9-878d-4fe6-a063-36e2ddfa9f05.png)


#### Comparing our models :

Our naive model outperforms both dense and RNN(LSTM) model:

![image](https://user-images.githubusercontent.com/86077149/148681135-e06175bd-8082-4f74-906c-04875d8455b3.png)


**Building a neural networks algorithm doesn't necessarily mean that it will outperform all other models.**

### Model 3 : N-BEATS 

lets now try to build the biggest time series forecasting model we've built so far.

More specifically, we're going to be replicating the algorithm in the following paper : https://arxiv.org/pdf/1905.10437.pdf

This is what our N-Beats model forecast looks like: 

![image](https://user-images.githubusercontent.com/86077149/148682279-8e338960-80f8-4742-a5b0-ebf527937c4b.png)


#### N-Beats Architecture 

![image](https://user-images.githubusercontent.com/86077149/148681631-5854767d-5e9e-4c0f-8af7-c2c687791d36.png)

#### Comparing our models :

Our naive model continues to outperform all other models :

![image](https://user-images.githubusercontent.com/86077149/148682286-022f6d17-b73d-45bb-bcdd-42d9e44f2791.png)



### Model 4 : Ensemble Model (stacks multiple models together)

Our ensemble model forecast looks like this :

![image](https://user-images.githubusercontent.com/86077149/148682618-ab6a7029-4a82-4df8-996f-0c591b242ad5.png)


#### Comparing our models :

Naive model continues to outperform all other models with ensemble model being the second close:

![image](https://user-images.githubusercontent.com/86077149/148682624-390afd5e-c0d0-44f8-aca1-12446c034912.png)


All our models are lagging, just like the naive model

> NOTE: These predicition intervals are estimates themselves and they've been created with the assumption that our model's data is from a normal distribution.


## Making a forecast onto the future with our model 






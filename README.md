# Energy consumption prediction for electric buses
## Overview
&emsp;&emsp;Electric buses (EBs) are widely recognized as an environmentally friendly and energy-efficient alternative to traditional diesel buses. However, the issue of driving range anxiety hinders their further adoption and popularity. This program predicts the average Energy Consumption Rate (ECR) of EBs driving different ranges in the future following predefined routes with machine learning algorithms. In the prediction models, many factors including vehicle conditions, vehicle kinametic characteristics, road conditions, weather, traffic conditions are considered to improve the prediction accuracy. We develop two prediction framework: one is a end-to-end framework based on Transformer and the other is a two-stage framework combining energy estimation and prediction. This program contains some main codes of model construction. Both frameworks are available online and a brief introduction is presented in the following parts.
## End-to-end prediction
&emsp;&emsp;This study is available online: https://www.sciencedirect.com/science/article/pii/S0306261924013242.  
&emsp;&emsp;This study proposes a transformer-based approach to predict the ECR of EBs based on driving distances by extracting implicit features from dynamic characteristics. First, high-resolution bus data is acquired and divided into trip segments, which are then fused with meteorological and road network data. Second, sliding windows are employed for different travel ranges to construct the dataset. Each sample in the dataset contains 12 historical dynamic feature time series and 12 predetermined features within the predicted range. The historical dynamic features are deeply extracted using the Transformer encoder module to obtain implicit features like driver behavior and bus kinematic characteristics. They are then fused with other factors, and the prediction of the ECR is performed using a fully connected neural network. Finally, a sensitivity analysis is conducted for each feature to demonstrate its impact and variations under different implicit features and travel distances.  
![image](end_to_end_prediction/end_to_end_framework.png)
## Two-stage framework
&emsp;&emsp;This study is available online: https://www.sciencedirect.com/science/article/pii/S1366554524004757.  
&emsp;&emsp;This study proposes a framework for predicting EB energy consumption, which is primarily divided into energy consumption estimation, kinematic feature prediction, and energy consumption prediction. The framework begins by fusing high-resolution real-world EB data with weather and road information, from which five types of influencing factors are extracted for different driving distances. An eXtreme Gradient Boosting (XGBoost) model is developed to evaluate feature importance and estimate the ECR. The SHapley Additive explanation (SHAP) method is then used to analyze the factors affecting the ECR. To predict important kinematic characteristics, spatial and temporal characteristics are captured using Long Short-Term Memory (LSTM) and a fully connected neural network. Finally, the predicted kinematic characteristics and the XGBoost model are combined to enable real-time prediction of the ECR.  
![image](two_stage_framework/two_stage_framework.png)

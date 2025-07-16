# RUL-prediction
Predict the Remaining Useful Life (RUL) of Each Type of Engines

## Predictive Maintenance (PdM)
- Use predictive tools to determine when maintenance action need to be taken
- Based on continuous monitor (e.g. sensor data from machine, process, …)

## Dataset Description
- id : type of machines
- cycle : the time unit 
- setting 1 ~ 3 : settings of machines
- s1 ~ s21 : sensor readings for each cycle
- RUL :  Remaining Useful Life

## Methods
### Exponentially Weighted Moving Average (EWMA)
Apply EWMA for smoothing : $y_t = \alpha \cdot x_t + (1 - \alpha) \cdot y_{t-1}$  
Through multiple experiments, best result achieed with alpha = 0.4
### CNN + LSTM
Simultaneously capture local features and long-term temporal dependencies. Using CNN to reduce input dimensionality and filter out irrelevant features, LSTM can focus more effectively on significant patterns and temporal structures.
### Depthwise Separable Convolution
Depthwise Separable Convolutions are adopted in the convolutional layers to replace standard convolution layers. Depthwise Separable Convolutions require fewer parameters and computational resources than regular convolution layers and have the distinct advantage of processing each feature channel independently through Depthwise Convolution. This approach avoids premature mixing of features across different channels. Subsequently, Pointwise Convolution (1x1 convolution) combines these features, integrating information across channels linearly. 
### Long Short-Term Memory (LSTM)
A well-known variant of RNNs designed to handle long-term dependencies in sequential data. Unlike traditional RNNs, LSTM uses a gating mechanism to control the flow of information, allowing it to retain important information over longer sequences while forgetting irrelevant details.
### Ensembling
Combine the predictions of multiple models to enhance overall generalization ability and stability. This part is not included in the code file.

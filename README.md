# Emotion_From_Speech
An edge computing model for emotion perception from speech. 

## Preprocessing
MFCC Feature extraction aided by https://studio.edgeimpulse.com
- Window size: 2000ms, window increase: 500ms
- Frequency: 16000Hz
- 4 classification feature: female_angry, female_fear, female_sad, neutral
- number of coefficients: 32, Frame length & Frame stride: 0.02
- Filter number: 32
- FFT length: 512

## Model Settings
**for edge computing, remember profile int8 model.**  
Input layer(3200 features) -> Reshape(80 columns) ->   
1D conv/pooling layer(8 neurons, 3 kernel size) -> Dropout(25%) ->   
1D conv/pooling layer(16 neurons, 3 kernel size) -> Dropout(25%) ->   
1D conv/pooling layer(16 neurons, 3 kernel size) -> Dropout(25%) ->   
1D conv/pooling layer(16 neurons, 3 kernel size) -> Dropout(25%) -> Flatten -> 
Output (4 classes)  

Accuracy: 97.7%

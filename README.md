# Motor-Imagery-based-BCI
A subject-dependent brain-computer interface based on motor imagery mental strategy


## Data preparation and Preprocessing
The dataset consists of EEG data from 9 subjects. The cue-based BCI paradigm 
consisted of four different motor imagery tasks, namely the imagination of 
movement of the left hand (class 1), right hand (class 2), both feet (class 3), 
and tongue (class 4). Two sessions on different days were recorded for each 
subject. Each session is comprised of 6 runs separated by short breaks. One 
run consists of 48 trials (12 for each of the four possible classes), yielding a 
total of 288 trials per session. 22 EEG channels, and 3 EOG channels
<br />

We apply 3 techniques for preprocessing the signals:
Band Pass Filter: Bandpass filtering is performed using a sixth order 
Butterworth bandpass filter with low cut of 8 Hz and high cut of 30 Hz. This 
choice is because of the fact that motor imagery features generally happen 
in the alpha and beta bands of EEG.
Common Average Referencing (CAR) Spatial Filtering: enhances the local 
activity at electrode I by subtracting the average over all electrodes.
Normalization: Each channel is used its own mean and standard deviation.
<br />
### Before Preprocessing
<img src="https://github.com/Abdelrahman-Rashad/Motor-Imagery-based-BCI/blob/main/images/Screenshot%20(101).png?raw=true" width="500">

### After Preprocessing
<img src="https://github.com/Abdelrahman-Rashad/Motor-Imagery-based-BCI/blob/main/images/Screenshot%20(102).png?raw=true" width="500">

## Feature extraction
The main idea is to use a linear transform to project the multichannel EEG 
data into low-dimensional spatial subspace with a projection matrix, of 
which each row consists of weights for channels. <br /><br />
1- We used Build in CSP from MNE library to extract features<br />
2- We used Wavelet to extract features<br />

## Classifier used and its parameters
<br />
1- Random Forest <br />
2- SVM ((decision_function_shape='ovo'), ( kernel='rbf',gamma=0.5,C=0.1), (kernel='poly',degree=3,C=1)) <br />
3- KNN (n_neighbors=4) <br />
4- Logistic Regression (multi_class='ovr', solver='liblinear') <br /><br />

## Classification results
<br />
In CSP, The best accuracy is Logistic Regression with 86% <br />
In wavelet, The best accuracy is Logistic Regression with 76% <br />

## Screenshots for the interface
<img src="https://github.com/Abdelrahman-Rashad/Motor-Imagery-based-BCI/blob/main/images/Screenshot%20(106).png?raw=true" width="300">
<img src="https://github.com/Abdelrahman-Rashad/Motor-Imagery-based-BCI/blob/main/images/Screenshot%20(107).png?raw=true" width="300">
<img src="https://github.com/Abdelrahman-Rashad/Motor-Imagery-based-BCI/blob/main/images/Screenshot%20(108).png?raw=true" width="300">
<img src="https://github.com/Abdelrahman-Rashad/Motor-Imagery-based-BCI/blob/main/images/Screenshot%20(109).png?raw=true" width="300">




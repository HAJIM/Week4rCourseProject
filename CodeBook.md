<h1></h1>
<h1>CodeBook</h1>
<p>This is the codebook for the tidy_data.txt data set generated after applying run_analysis.R</p>
<p>
The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz.

Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag).

Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Note the 'f' to indicate frequency domain signals).

The reasoning behind my selection of features is that the assignment explicitly states "Extracts only the measurements on the mean and standard deviation for each measurement." To be complete, I included all variables having to do with mean or standard deviation.

In short, for this derived dataset, these signals were used to estimate variables of the feature vector for each pattern:
'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.
</p>
<h1>These are the variables in the final data after applying the average funtion on each and every subject and feature</h1>
<p>
"subject" "activity" "TimeBodyAccelerometerMean()-X" "TimeBodyAccelerometerMean()-Y" "TimeBodyAccelerometerMean()-Z" "TimeBodyAccelerometerStandardDeviation()-X" "TimeBodyAccelerometerStandardDeviation()-Y" "TimeBodyAccelerometerStandardDeviation()-Z" "TimeGravityAccelerometerMean()-X" "TimeGravityAccelerometerMean()-Y" "TimeGravityAccelerometerMean()-Z" "TimeGravityAccelerometerStandardDeviation()-X" "TimeGravityAccelerometerStandardDeviation()-Y" "TimeGravityAccelerometerStandardDeviation()-Z" "TimeBodyAccelerometerJerkMean()-X" "TimeBodyAccelerometerJerkMean()-Y" "TimeBodyAccelerometerJerkMean()-Z" "TimeBodyAccelerometerJerkStandardDeviation()-X" "TimeBodyAccelerometerJerkStandardDeviation()-Y" "TimeBodyAccelerometerJerkStandardDeviation()-Z" "TimeBodyGyroscopeMean()-X" "TimeBodyGyroscopeMean()-Y" "TimeBodyGyroscopeMean()-Z" "TimeBodyGyroscopeStandardDeviation()-X" "TimeBodyGyroscopeStandardDeviation()-Y" "TimeBodyGyroscopeStandardDeviation()-Z" "TimeBodyGyroscopeJerkMean()-X" "TimeBodyGyroscopeJerkMean()-Y" "TimeBodyGyroscopeJerkMean()-Z" "TimeBodyGyroscopeJerkStandardDeviation()-X" "TimeBodyGyroscopeJerkStandardDeviation()-Y" "TimeBodyGyroscopeJerkStandardDeviation()-Z" "TimeBodyAccelerometerMagnitudeMean()" "TimeBodyAccelerometerMagnitudeStandardDeviation()" "TimeGravityAccelerometerMagnitudeMean()" "TimeGravityAccelerometerMagnitudeStandardDeviation()" "TimeBodyAccelerometerJerkMagnitudeMean()" "TimeBodyAccelerometerJerkMagnitudeStandardDeviation()" "TimeBodyGyroscopeMagnitudeMean()" "TimeBodyGyroscopeMagnitudeStandardDeviation()" "TimeBodyGyroscopeJerkMagnitudeMean()" "TimeBodyGyroscopeJerkMagnitudeStandardDeviation()" "FrequencyBodyAccelerometerMean()-X" "FrequencyBodyAccelerometerMean()-Y" "FrequencyBodyAccelerometerMean()-Z" "FrequencyBodyAccelerometerStandardDeviation()-X" "FrequencyBodyAccelerometerStandardDeviation()-Y" "FrequencyBodyAccelerometerStandardDeviation()-Z" "FrequencyBodyAccelerometerMeanFreq()-X" "FrequencyBodyAccelerometerMeanFreq()-Y" "FrequencyBodyAccelerometerMeanFreq()-Z" "FrequencyBodyAccelerometerJerkMean()-X" "FrequencyBodyAccelerometerJerkMean()-Y" "FrequencyBodyAccelerometerJerkMean()-Z" "FrequencyBodyAccelerometerJerkStandardDeviation()-X" "FrequencyBodyAccelerometerJerkStandardDeviation()-Y" "FrequencyBodyAccelerometerJerkStandardDeviation()-Z" "FrequencyBodyAccelerometerJerkMeanFreq()-X" "FrequencyBodyAccelerometerJerkMeanFreq()-Y" "FrequencyBodyAccelerometerJerkMeanFreq()-Z" "FrequencyBodyGyroscopeMean()-X" "FrequencyBodyGyroscopeMean()-Y" "FrequencyBodyGyroscopeMean()-Z" "FrequencyBodyGyroscopeStandardDeviation()-X" "FrequencyBodyGyroscopeStandardDeviation()-Y" "FrequencyBodyGyroscopeStandardDeviation()-Z" "FrequencyBodyGyroscopeMeanFreq()-X" "FrequencyBodyGyroscopeMeanFreq()-Y" "FrequencyBodyGyroscopeMeanFreq()-Z" "FrequencyBodyAccelerometerMagnitudeMean()" "FrequencyBodyAccelerometerMagnitudeStandardDeviation()" "FrequencyBodyAccelerometerMagnitudeMeanFreq()" "FrequencyBodyAccelerometerJerkMagnitudeMean()" "FrequencyBodyAccelerometerJerkMagnitudeStandardDeviation()" "FrequencyBodyAccelerometerJerkMagnitudeMeanFreq()" "FrequencyBodyGyroscopeMagnitudeMean()" "FrequencyBodyGyroscopeMagnitudeStandardDeviation()" "FrequencyBodyGyroscopeMagnitudeMeanFreq()" "FrequencyBodyGyroscopeJerkMagnitudeMean()" "FrequencyBodyGyroscopeJerkMagnitudeStandardDeviation()" "FrequencyBodyGyroscopeJerkMagnitudeMeanFreq()" "Angle(TimeBodyAccelerometerMean,Gravity)" "Angle(TimeBodyAccelerometerJerkMean),GravityMean)" "Angle(TimeBodyGyroscopeMean,GravityMean)" "Angle(TimeBodyGyroscopeJerkMean,GravityMean)" "Angle(X,GravityMean)" "Angle(Y,GravityMean)" "Angle(Z,GravityMean)"

</p>
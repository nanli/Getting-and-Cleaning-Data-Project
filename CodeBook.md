## CodeBook for the cleaned data (tidy1.csv and tidy2.csv)

#### Description of data
From the raw dataset, we have extracted only the measurements on the mean and standard deviation for each measurement.In the cleaned dataset, we have 82 variables in total, which includs:

1. 3 experimental ***factor*** features

"subject": the person id recruited for the experiment
           30 levels (1-30)
"activity": what the person was doing 
            6 levels ("WALKING","WALKING_UPSTAIRS","WALKING_DOWNSTAIRS","SITTING","STANDING","LAYING")
            
"data.type": whether the data is from the trainning set or the testing set
            2 levels ("TRAIN","TEST")

2. 79 sensor ***numeric*** features

 [1] "tBodyAcc.mean.X"               "tBodyAcc.mean.Y"               "tBodyAcc.mean.Z"               "tBodyAcc.std.X"               
 [5] "tBodyAcc.std.Y"                "tBodyAcc.std.Z"                "tGravityAcc.mean.X"            "tGravityAcc.mean.Y"           
 [9] "tGravityAcc.mean.Z"            "tGravityAcc.std.X"             "tGravityAcc.std.Y"             "tGravityAcc.std.Z"            
[13] "tBodyAccJerk.mean.X"           "tBodyAccJerk.mean.Y"           "tBodyAccJerk.mean.Z"           "tBodyAccJerk.std.X"           
[17] "tBodyAccJerk.std.Y"            "tBodyAccJerk.std.Z"            "tBodyGyro.mean.X"              "tBodyGyro.mean.Y"             
[21] "tBodyGyro.mean.Z"              "tBodyGyro.std.X"               "tBodyGyro.std.Y"               "tBodyGyro.std.Z"              
[25] "tBodyGyroJerk.mean.X"          "tBodyGyroJerk.mean.Y"          "tBodyGyroJerk.mean.Z"          "tBodyGyroJerk.std.X"          
[29] "tBodyGyroJerk.std.Y"           "tBodyGyroJerk.std.Z"           "tBodyAccMag.mean"              "tBodyAccMag.std"              
[33] "tGravityAccMag.mean"           "tGravityAccMag.std"            "tBodyAccJerkMag.mean"          "tBodyAccJerkMag.std"          
[37] "tBodyGyroMag.mean"             "tBodyGyroMag.std"              "tBodyGyroJerkMag.mean"         "tBodyGyroJerkMag.std"         
[41] "fBodyAcc.mean.X"               "fBodyAcc.mean.Y"               "fBodyAcc.mean.Z"               "fBodyAcc.std.X"               
[45] "fBodyAcc.std.Y"                "fBodyAcc.std.Z"                "fBodyAcc.meanFreq.X"           "fBodyAcc.meanFreq.Y"          
[49] "fBodyAcc.meanFreq.Z"           "fBodyAccJerk.mean.X"           "fBodyAccJerk.mean.Y"           "fBodyAccJerk.mean.Z"          
[53] "fBodyAccJerk.std.X"            "fBodyAccJerk.std.Y"            "fBodyAccJerk.std.Z"            "fBodyAccJerk.meanFreq.X"      
[57] "fBodyAccJerk.meanFreq.Y"       "fBodyAccJerk.meanFreq.Z"       "fBodyGyro.mean.X"              "fBodyGyro.mean.Y"             
[61] "fBodyGyro.mean.Z"              "fBodyGyro.std.X"               "fBodyGyro.std.Y"               "fBodyGyro.std.Z"              
[65] "fBodyGyro.meanFreq.X"          "fBodyGyro.meanFreq.Y"          "fBodyGyro.meanFreq.Z"          "fBodyAccMag.mean"             
[69] "fBodyAccMag.std"               "fBodyAccMag.meanFreq"          "fBodyBodyAccJerkMag.mean"      "fBodyBodyAccJerkMag.std"      
[73] "fBodyBodyAccJerkMag.meanFreq"  "fBodyBodyGyroMag.mean"         "fBodyBodyGyroMag.std"          "fBodyBodyGyroMag.meanFreq"    
[77] "fBodyBodyGyroJerkMag.mean"     "fBodyBodyGyroJerkMag.std"      "fBodyBodyGyroJerkMag.meanFreq"

The numeric feature names are all self-explanatory.


#### How the cleaning was performed

The cleaned data was transformed from the following files:

1. "features.txt": This file lists all the 561 features, but we selected only those "mean" or "std" features
2. "X_train.txt" and "X_test.txt" : The 561-feature vector with time and frequency domain variables are in this file, we chose only the 79 selcted features from "features.txt"
3. "y_train.txt" and "y_test.txt": 6 training activity labels. These 79 feature vectors are mapped to the training activity labels in these files. 
4. "subject.test.txt" and "subject_train.test": maps to who performed the experiments
5. "activity_labels.txt": from this we know which activity each dummy number (1-6) represented in the data

The raw datafile that is available here http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones also include raw inertial signal measurements,but we did not use these data. (the project requirements only asked us to extract mean and std from the 561-feature vectors) .


NOTE: tidy2.csv is even further cleaned from tidy1.csv, because we are asked to "Creates a second, independent tidy data set with the average of each variable for each activity and each subject". So the each observation in this data set is an average for each activity and subject.





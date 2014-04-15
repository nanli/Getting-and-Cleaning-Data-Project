Getting-and-Cleaning-Data-Project
=================================

In this README file, I will go through the code, in order to demonstrate how I imeplented the parsing script. Of course you can always check the comments in the script, but they should be complementary to each other.

#### Step 1 - Set the Workspace
This should be adapted to someone's own computer setting (where the data is located). We put all the txt files directly under the workspace folder.

#### Step 2 - Select features from the 561 feature spaces
  - We first read the features list as a dataframe, 
  - then we perform string operations to select those features that contain "mean" or "std". 
  - After that, we have the features that need to be extracted (79 out of 561), save these features as a variable called "featureToExtract"
  - Then change the original feature names by removing brackets and changing "-" to "."
  
#### Step 3 - Parse the training data as well as the testing data
   - Read subject list
   - Read all feature variables, but we subset only the variables that are in "featureToExtract"
   - Change variable names to that in the "featureToExtract" 
   - Read activities list (y_test or y_train)
   - subject list, activity list and the feature list should be of the same length, so we can bind them together using cbind()
   - We change the non-feature varabiles to "subject","activity" and "data.type". This dataset is the tidy1.csv
   
#### Step 4 - Take average per subject per activity (required by the 5th requirement)
   - Use a convinient function aggregate() to group the variables in one line. This dataset is the tidy2.csv 
   
   
 
### NOTE: Running the script
Simply select all the content of the script run_analysis.R in Rstudio, and click run, you will get the two files. However, you need to change the workspace to the corresponding data folder on your computer. 
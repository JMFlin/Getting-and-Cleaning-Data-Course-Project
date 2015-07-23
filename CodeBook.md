The run_analysis.R script performs the following steps to clean the data:


 1. Read X_train.txt, y_train.txt and subject_train.txt from "./Data/train" folder 
 and store them in train_X, train_Y and train_Subject variables.
    
 2. Read X_test.txt, y_test.txt and subject_test.txt from "./Data/test" folder 
 and store them in test_X, test_Y and test_Subject variables.
    
 3. Merge test_X and test_X to form join_X, which is a 10299x561 data frame. 
 Merge test_Y and train_Y to form join_Y, which is a 10299x1 data frame. 
 Merge test_Subject and train_Subject to form join_Subject, which is a 10299x1 data frame
    
 4. Read the features.txt file from the "Data" folder and store the data 
 in a variable called features. Extract only the measurements on the mean 
 and standard deviation for each measurement.  The result is a 10299x66 data frame.
    
 5. Use descriptive activity names to name the activities in the data set. 
 I remove the "-" and "()" symbols from the names and capitalize the first letter of "mean" and "std".
    
 6. Read the activity_labels.txt file from the "Data"" folder and store the data in a variable called activity.
 I clean the activity names in the second column of this data set. 
 I take out the "_" symbol from the names. 
 I make all the letters in the words lowercase. 
 I then capitalize "Down" and "Up" to make the names easier to read. 
 Transform the values of join_Y according to the activity data frame. 
 Name the column name "activity".
    
 7. Name the column of join_Subject to "subject". 
 Combine the join_Subject, join_Y and join_X by column to get a new cleaned data frame called cleanMerge. 
 The "subject" column contains integers that range from 1 to 30 inclusive. 
 The "activity" column contains 6 kinds of activity names. 
 The last 66 columns contain measurements that range from -1 to 1 exclusive. 
 Write the cleanMerge out to "merged_data.txt" file.
    
 8. Create a second independent tidy data set with the average of each measurement for each activity and each subject.
 I aggregate the data by subject and activity to form a data frame that is a combination of the two. 
 For each combination, I calculate the mean of each measurement. 
 Then, I arrange the data by subject and activity. The end result is a 180x68 data frame. Write the result out to       "tidy_merged_data.txt" file.

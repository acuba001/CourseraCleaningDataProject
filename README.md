# Coursera Cleaning Data Course Project

This project required the creation of a `run_analysis.R` file that does the following:

* Merges the training and the test sets to create one data set.
* Extracts only the measurements on the mean and standard deviation for each measurement. 
* Uses descriptive activity names to name the activities in the data set
* Appropriately labels the data set with descriptive variable names. 
* From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

## run_analysis.R details

The way the code merges the data is by the following:


`"features.txt"`|"Subject"|"Activity"
------------|---------|----------
`"X_train.txt"`|`"subject_train.txt"`|`"activity_train.txt"`
`"X_test.txt"`|`"subject_test.txt"`|`"activity_test.txt"` 

Where, features.txt, "Subject", and "Activity" will determine the column names of the data table that satisfies the third requirement. Also, the body of the data table will essentially be appending the gathered test data to the train gathered data. However, the activity column of both train and test observations must be factorized by `activity_labels.txt` so that the third requirement is satisfied. All of this is stored in the variable `data` which finishes the first requirement. 

Then, to extract the mean and standard deviation columns of `data`, we first obtain the column names of `data` that contain the strings `"mean"` and `"std"` using the `grepl`. After obtaining that logic vector and recording it to `meanNstdData`, the  `which` function is used to subset the `data` table according to `meanNstdData` to obtain the desired extracted data. The extracted data is then stored in the variable `extractedData` which finishes the second requirement.

Finally, to obtain the tidy data for the fifth requirement, what is simply used is the function `aggregate` that creates a new table with the mean of each variable from `data` (per instance of `Subject` and `Activity`). The result is stored in the variable `tidy_data` and then written in a file called `"tidy data.txt"`.
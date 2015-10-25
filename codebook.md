# Code book for run_analysis.R

The following is a list of variables used in `run_analysis.R`:

* `train`: the data retrived from the `"UCI HAR Dataset/train/X_train.txt"` using the `read.table`
* `test`: the data retrived from the `"UCI HAR Dataset/test/X_test.txt"` using the `read.table`
* `subject_train`: the data retrived from the `"UCI HAR Dataset/train/subject_train.txt"` using the `read.table`
* `subject_test`: the data retrived from the `"UCI HAR Dataset/test/subject_test.txt"` using the `read.table`
* `activity_train`: the data retrived from the `"UCI HAR Dataset/train/y_train.txt"` using the `read.table`
* `activity_test`: the data retrived from the `"UCI HAR Dataset/test/y_test.txt"` using the `read.table`
* `activity_labels`: the data retrived from the `"UCI HAR Dataset/activity_labels.txt"` using the `read.table`
* `factivity`: this is the factorized activity column by it's numbers which is `activity_train` and `activity_test` combined.
* `activity`: this is the factorized activity column by `activity_labels` of `factivity`
* `variable_names`: this is the column names of `data`
* `col_block1`: this is the block of the data table that appends the `test` table to the end of the `train` table.
* `col_block2`: this is the block of the data table that appends the `subject_test` column to the end of the `subject_train` column.
* `col_block3`: this is the block of the data table that is the `activity` column
* `data`: this is `col_block1`, `col_block2`, and `col_block3` all column binded into one table with column names `variable_names` which is the table for requirement 1, 3, and 4.
* `meanNstdData`: this is a logic vector containing the value for the `grepl` function that determines which columns of `data` contain `mean` or `std`.
* `extractedData`: this is the the table containing the extracted data for requirement 2.
* `tidy_data`: this is the table which is the result of the `aggregate` function which is the table for requirement 5.
# gettingandcleaningdata
module3courseproject

Code Book

Downloaded the dataset
Dataset downloaded under the folder UCI HAR Dataset

Assigned each data frame to variable names
features <- features.txt : 561 rows, 2 columns
The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.
activities <- activity_labels.txt : 6 rows, 2 columns
List of activities performed when the corresponding measurements were taken and its codes (labels)
subject_test <- test/subject_test.txt : 2947 rows, 1 column
contains test data of 9/30 volunteer test subjects being observed
x_test <- test/X_test.txt : 2947 rows, 561 columns
contains recorded features test data
y_test <- test/y_test.txt : 2947 rows, 1 columns
contains test data of activities’code labels
subject_train <- test/subject_train.txt : 7352 rows, 1 column
contains train data of 21/30 volunteer subjects being observed
x_train <- test/X_train.txt : 7352 rows, 561 columns
contains recorded features train data
y_train <- test/y_train.txt : 7352 rows, 1 columns
contains train data of activities’code labels

Merged the training and test datasets to create one data set
x (10299 rows, 561 columns): created by merging x_train and x_test using rbind() function
y (10299 rows, 1 column): created by merging y_train and y_test using rbind() function
Subject (10299 rows, 1 column): created by merging subject_train and subject_test using rbind() function
Merged.Data (10299 rows, 563 column): created by merging Subject, y and x using cbind() function

Taking the mean and standard deviation for each measurement
TidyData (10299 rows, 88 columns): created by subsetting Merged.Data, selecting only columns: subject, code and the measurements on the mean and standard deviation (std) for each measurement

Labeled the data set with variable names
Renamed activities in TidyData
Acc in column’s name replaced by Accelerometer
Gyro in column’s name replaced by Gyroscope
BodyBody in column’s name replaced by Body
Mag in column’s name replaced by Magnitude
Character f in column’s name replaced by Frequency
Character t in column’s name replaced by Time

From the data set in step 4, created a second, independent tidy data set with the average of each variable for each activity and each subject
Final_Data (180 rows, 88 columns) is created by sumarizing TidyData taking the means of each variable for each activity and each subject, after groupped by subject and activity.
Exported Final_Data into Final_Data.txt file.

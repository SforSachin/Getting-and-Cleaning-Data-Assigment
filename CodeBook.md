# 1) Introduction

The script run_analysis.R consist of 5 steps described in the course project's definition.

- First, read the similar data files test, train and Subject into respective tables and merged using the rbind() function. 
By similar, we address those files having the same number of columns and referring to the same entities.
- Then, columns with names containing mean() and standard deviation std() are retrieved from the whole dataset. 
After extracting these columns, those column name assigned to X_data.
- As activity data is addressed with values 1:6, we take the activity names and IDs from activity_labels.txt 
and after extracting the labels those are assigned to Y_data dataset.
- On the whole dataset, those columns with vague column names are corrected.
- Finally, we generate a new dataset with all the average measures for each subject and activity type (30 subjects * 6 activities = 180 rows).
The output file is called averages_data.txt, and uploaded to this repository.

# 2) Variables

- x_train, y_train, x_test, y_test, subject_train and subject_test contain the data from the downloaded files.
- x_data, y_data and subject_data merge the previous datasets to further analysis.
- features contains the correct names for the x_data dataset, which are applied to the column names stored in mean_and_std_features,
  a numeric vector used to extract the desired data.
- A similar approach is taken with activity names through the activities variable.
- all_data merges x_data, y_data and subject_data in a big dataset.
- Finally, averages_data contains the relevant averages which will be later stored in a .txt file. 
ddply() from the plyr package is used to apply colMeans() and ease the development.

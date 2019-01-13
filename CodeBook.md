###Introduction

The script run_analysis.R performs the 5 steps described in the course project's description.

1. All similar data is merged by the use of the rbind() function. Similar files were addressed by having the same number of columns and referring to the same entities.
2. Only columns with the mean and standard deviation measures are taken from the whole data set. The columns are given the correct names, taken from features.txt after extraction.
3. Activity names and IDs from activity_labels.txt are substituted in the dataset as activity data is addressed with values 1:6.
4. Columns with vague column names are corrected.
5. Lastly, a new dataset is generated with all the average measures for each subject and activity type (30 subjects * 6 activities = 180 rows). The output file is called tidy_data_set.txt, and are uploaded to this repository.

###Variables

1. x_train, y_train, x_test, y_test, subject_train and subject_test contains data from the downloaded files.
2. x_data, y_data and subject_data merge the previous datasets to provide further analysis.
3. correct names are inside features for the x_data dataset, which are applied to the column names stored in mean_and_std_features, a numeric vector which is used to extract the desired data.
4. A similar approach is done with activity names through the activities variable.
5. all_data merges x_data, y_data and subject_data into a big dataset.
6. Lastly, relevant averages are in the averages_data which will be later deposited in a .txt file. ddply() from the plyr package is used to apply colMeans() to develop the corresponding activity with ease.
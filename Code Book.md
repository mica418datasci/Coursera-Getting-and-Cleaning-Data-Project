# Code book for Getting and Cleaning Data Project
Author: Micaela R. Tullao


The data set "tidy_data.txt" described in this Codebook is located in the repository "Coursera Getting and Cleaning Data Project".


Further description of the commands and their actions can be viewed in the run.analysis.R file of this repository. 

The zip file containing the source data is located at https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip.

## Identifiers
~ subject

Subject identifier, integer, ranges from 1 to 30.

~ activity

Activity identifier, string with 6 possible values:

* WALKING: subject was walking
* WALKING_UPSTAIRS: subject was walking upstairs
* WALKING_DOWNSTAIRS: subject was walking downstairs
* SITTING: subject was sitting
* STANDING: subject was standing
* LAYING: subject was laying


## Actions
The following actions were applied to the source data:

1. The training and test sets were merged to create one data set.
1. The measurements on the mean and standard deviation were extracted for each measurement, and the others were discarded.
1. The activity identifiers  were replaced with descriptive activity names.
1. The variable names were replaced with descriptive variable names, using the following set of rules:
	- Special characters (i.e. `(`, `)`, and `-`) were removed
	- The initial `f` and `t` were expanded to `frequencyDomain` and `timeDomain` respectively.
	- `Acc`, `Gyro`, `Mag`, `Freq`, `mean`, and `std` were replaced with `Accelerometer`, `Gyroscope`, `Magnitude`, `Frequency`, `Mean`, and `StandardDeviation` respectively.
	- Replaced (supposedly incorrect as per source's `features_info.txt` file) `BodyBody` with `Body`.
1. From the data set in step 4, the final data set was created with the average of each variable for each activity and each subject.

The collection of the source data and the transformations listed above were implemented by the `run_analysis.R` R script (see `README.md` file for usage instructions).

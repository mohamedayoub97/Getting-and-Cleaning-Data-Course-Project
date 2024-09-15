## CodeBook: Data Science Specialization course series: Getting and Cleaning Data Course Project

============================================================================================
### Original raw data sets: Human Activity Recognition Using Smartphones Dataset Version 1.0:

Jorge L. Reyes-Ortiz, Davide Anguita, Alessandro Ghio, Luca Oneto.
Smartlab - Non Linear Complex Systems Laboratory
DITEN - Università degli Studi di Genova.
Via Opera Pia 11A, I-16145, Genoa, Italy.
activityrecognition@smartlab.ws

A full description is available at the site www.smartlab.ws where the data was obtained: 
http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones 

-------------------------------------------------------------------------------------------------
#### List of the original data sets inside the downloaded zip file:

 	 - 'README.txt': describes about the general information and background related to the data sets within the zip file.
	
 	 - 'features_info.txt': Shows information about the variables used on the feature vector.

   	 - 'features.txt': List of all features.

   	 - 'activity_labels.txt': Links the class labels with their activity name.

   	 - 'train/X_train.txt': Training set.

   	 - 'train/y_train.txt': Training labels.

   	 - 'test/X_test.txt': Test set.

   	 - 'test/y_test.txt': Test labels.
   
    	 - 'train/subject_train.txt':   Each row identifies the subject who performed the activity for each window sample.
            Its range is from 1 to 30. (for training set)
   
  	 - 'test/subject_test.txt':  Each row identifies the subject who performed the activity for each window sample.
  	    Its range is from 1 to 30. (for test set)
      
   	  The following data sets are not been used in the current project. 

   	 - 'train/Inertial Signals/total_acc_x_train.txt'; 'train/Inertial Signals/body_acc_x_train.txt';
   	   'train/Inertial Signals/body_gyro_x_train.txt'. More information related to these three data sets can be
   	    found in 'README.txt', 'feature_info.txt' and 'feature.txt' and the original website.
    
-------------------------------------------------------------------------------------------------------------
#### Background: feature selection, feature vector variables and unit

The following information is the hightlights/summary of the 'feature_info.txt' and 'feature.txt'

>The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years.
>Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING)
>wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope,
>they captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz.
>The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly
>partitioned into two sets, where 70% of the volunteers was selected for generating the training data
>and 30% the test data.
>
>The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ 
>and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. 
>Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency
>of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration
>signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz. 
>
>Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals
>(tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated 
>using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag). 
>
>Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ,
>fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. 
>(Note the 'f' to indicate frequency domain signals). 

>These signals were used to estimate variables of the feature vector for each pattern:  
>'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.
>
>		tBodyAcc-XYZ
>		tGravityAcc-XYZ
>		tBodyAccJerk-XYZ
>		tBodyGyro-XYZ
>		tBodyGyroJerk-XYZ
>		tBodyAccMag
>		tGravityAccMag
>		tBodyAccJerkMag
>		tBodyGyroMag
>		tBodyGyroJerkMag
>		fBodyAcc-XYZ
>		fBodyAccJerk-XYZ
>		fBodyGyro-XYZ
>		fBodyAccMag
>		fBodyAccJerkMag
>		fBodyGyroMag
>		fBodyGyroJerkMag
>
>	Additional vectors obtained by averaging the signals in a signal window sample. 
>	These are used on the angle() variable:
>
>		gravityMean
>		tBodyAccMean
>		tBodyAccJerkMean
>		tBodyGyroMean
>		tBodyGyroJerkMean
>
>	The set of variables that were estimated from these signals are: 
>
>		mean(): Mean value
>		std(): Standard deviation
>		mad(): Median absolute deviation 
>		max(): Largest value in array
>		min(): Smallest value in array
>		sma(): Signal magnitude area
>		energy(): Energy measure. Sum of the squares divided by the number of values. 
>		iqr(): Interquartile range 
>		entropy(): Signal entropy
>		arCoeff(): Autorregresion coefficients with Burg order equal to 4
>		correlation(): correlation coefficient between two signals
>		maxInds(): index of the frequency component with largest magnitude
>		meanFreq(): Weighted average of the frequency components to obtain a mean frequency
>		skewness(): skewness of the frequency domain signal 
>		kurtosis(): kurtosis of the frequency domain signal 
>		bandsEnergy(): Energy of a frequency interval within the 64 bins of the FFT of each window.
>		angle(): Angle between to vectors.

##### Unit:

Features are normalized and bounded within [-1,1]. In other words, they are unitless.

------------------------------------------------------------------------------------------------
#### Original data sets: selected input data variables

Based on the requirement of the course project, I only selected those input variables
related to the measurements on the mean and standard deviation for each measurement.
(see the section of "Instruction and Requirements" in README.md)

They are the following:

	tBodyAcc-mean()-X           tBodyAcc-mean()-Y           tBodyAcc-mean()-Z           tBodyAcc-std()-X           
	tBodyAcc-std()-Y            tBodyAcc-std()-Z            tGravityAcc-mean()-X        tGravityAcc-mean()-Y       
	tGravityAcc-mean()-Z        tGravityAcc-std()-X         tGravityAcc-std()-Y         tGravityAcc-std()-Z        
	tBodyAccJerk-mean()-X       tBodyAccJerk-mean()-Y       tBodyAccJerk-mean()-Z       tBodyAccJerk-std()-X       
	tBodyAccJerk-std()-Y        tBodyAccJerk-std()-Z        tBodyGyro-mean()-X          tBodyGyro-mean()-Y         
	tBodyGyro-mean()-Z          tBodyGyro-std()-X           tBodyGyro-std()-Y           tBodyGyro-std()-Z          
	tBodyGyroJerk-mean()-X      tBodyGyroJerk-mean()-Y      tBodyGyroJerk-mean()-Z      tBodyGyroJerk-std()-X      
	tBodyGyroJerk-std()-Y       tBodyGyroJerk-std()-Z       tBodyAccMag-mean()          tBodyAccMag-std()          
	tGravityAccMag-mean()       tGravityAccMag-std()        tBodyAccJerkMag-mean()      tBodyAccJerkMag-std()      
	tBodyGyroMag-mean()         tBodyGyroMag-std()          tBodyGyroJerkMag-mean()     tBodyGyroJerkMag-std()     
	fBodyAcc-mean()-X           fBodyAcc-mean()-Y           fBodyAcc-mean()-Z           fBodyAcc-std()-X           
	fBodyAcc-std()-Y            fBodyAcc-std()-Z            fBodyAccJerk-mean()-X       fBodyAccJerk-mean()-Y      
	fBodyAccJerk-mean()-Z       fBodyAccJerk-std()-X        fBodyAccJerk-std()-Y        fBodyAccJerk-std()-Z       
	fBodyGyro-mean()-X          fBodyGyro-mean()-Y          fBodyGyro-mean()-Z          fBodyGyro-std()-X          
	fBodyGyro-std()-Y           fBodyGyro-std()-Z           fBodyAccMag-mean()          fBodyAccMag-std()          
	fBodyBodyAccJerkMag-mean()  fBodyBodyAccJerkMag-std()   fBodyBodyGyroMag-mean()     fBodyBodyGyroMag-std()     
	fBodyBodyGyroJerkMag-mean() fBodyBodyGyroJerkMag-std() 

The complete list of variables of each feature vector is available in 'features.txt'


---------------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------
### Tidy data sets

#### Tiday data set: new variable names

* New variable names were from selected input data variables (see previous section)
* The names were modified mainly to avoid any unnecessary errors in R when this tidy data set 
  is used as an input data during any data analysis in the future. The methods and reasons are 
  based on the instruction from the course video-sildes (Week 4: Editing text variables).
  
  + The following were modified:
    -- lower cases; removed bad characters "()"; replaced "-" to "."

* The activity names are also be modified such as: lower cases; removed "_"
  new activity names: laying, sitting, standing, walking, walkingdownstairs and walkingupstairs.
  
-------------------------------------------------------------------------------------------------------------
#### Tidy data set: data structure

* There are 180 observations of 68 variables.

		'data.frame':	180 obs. of  68 variables:
		 $ activity                 : chr  
		 $ subject                  : int  
		 $ tbodyacc.mean.x          : num 
		 $ tbodyacc.mean.y          : num  
		 $ tbodyacc.mean.z          : num  
		 $ tbodyacc.std.x           : num  
		 $ tbodyacc.std.y           : num 
 		 $ tbodyacc.std.z           : num  
		 $ tgravityacc.mean.x       : num   
		 $ tgravityacc.mean.y       : num  
		 $ tgravityacc.mean.z       : num   
		 $ tgravityacc.std.x        : num  
		 $ tgravityacc.std.y        : num  
		 $ tgravityacc.std.z        : num  
		 $ tbodyaccjerk.mean.x      : num  
		 $ tbodyaccjerk.mean.y      : num 
 		 $ tbodyaccjerk.mean.z      : num  
		 $ tbodyaccjerk.std.x       : num  
		 $ tbodyaccjerk.std.y       : num  
		 $ tbodyaccjerk.std.z       : num  
		 $ tbodygyro.mean.x         : num  
		 $ tbodygyro.mean.y         : num  
		 $ tbodygyro.mean.z         : num  
		 $ tbodygyro.std.x          : num  
		 $ tbodygyro.std.y          : num  
		 $ tbodygyro.std.z          : num  	 
		 $ tbodygyrojerk.mean.x     : num  
		 $ tbodygyrojerk.mean.y     : num  
		 $ tbodygyrojerk.mean.z     : num  
		 $ tbodygyrojerk.std.x      : num  
		 $ tbodygyrojerk.std.y      : num  
		 $ tbodygyrojerk.std.z      : num  
		 $ tbodyaccmag.mean         : num  
		 $ tbodyaccmag.std          : num  
		 $ tgravityaccmag.mean      : num  
		 $ tgravityaccmag.std       : num  
		 $ tbodyaccjerkmag.mean     : num  
 		 $ tbodyaccjerkmag.std      : num  
 		 $ tbodygyromag.mean        : num  
		 $ tbodygyromag.std         : num  
		 $ tbodygyrojerkmag.mean    : num  
		 $ tbodygyrojerkmag.std     : num  
		 $ fbodyacc.mean.x          : num   
		 $ fbodyacc.mean.y          : num  
		 $ fbodyacc.mean.z          : num  
		 $ fbodyacc.std.x           : num  
		 $ fbodyacc.std.y           : num  
		 $ fbodyacc.std.z           : num  
		 $ fbodyaccjerk.mean.x      : num  
		 $ fbodyaccjerk.mean.y      : num  
		 $ fbodyaccjerk.mean.z      : num  
		 $ fbodyaccjerk.std.x       : num  
		 $ fbodyaccjerk.std.y       : num  
 		 $ fbodyaccjerk.std.z       : num  
		 $ fbodygyro.mean.x         : num  
		 $ fbodygyro.mean.y         : num  
		 $ fbodygyro.mean.z         : num  
		 $ fbodygyro.std.x          : num  
		 $ fbodygyro.std.y          : num  
		 $ fbodygyro.std.z          : num  
		 $ fbodyaccmag.mean         : num  
		 $ fbodyaccmag.std          : num  
		 $ fbodybodyaccjerkmag.mean : num  
		 $ fbodybodyaccjerkmag.std  : num  
		 $ fbodybodygyromag.mean    : num  
		 $ fbodybodygyromag.std     : num  
		 $ fbodybodygyrojerkmag.mean: num  
		 $ fbodybodygyrojerkmag.std : num  
 
---------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------
### Study Design Summary
 
 * How to collect the data
 
   This is a course project. The location of this original raw data set for this course project 
   is provided via the link (see the section of Data Resources in README.md)
   https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 
   
   
 * The purposes/goal of this study design
 
   The first priority of this study design is fulfiled  all the purposes and requirements
   of this project (see the sections of "Purpose and Goal" and "Instructions and Requirements")
   in README.md.
 
---------------------------------------------------------------------------------------
### Instruction list to reproduce the tidy data set

This section is also in the section of "My work to the project" in README.md

#### Obtain the raw data sets and put them in the working directory (via Rstudio)

 * The following steps were performed in a PC running the operation system Window 8.1.
      The data cleaning processes were performed in Rstudio with R version 3.1.0
     
     + download the raw data from the following website:
      https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
      
     + using the following R command to download the data:
     
      		 >setInternet2(TRUE)   
      		 >url_proj <- "https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip"
      		 >download.file(urlproj, destfile="Dataset.zip", mode="wb")
      
     + unzip the raw data sets
      
   			>unzip("Dataset.zip")
      
     + put the raw data sets in the selected working directory called "datacleaningproject"
       that is same name as in a repo in my Github account. 
       (In other words, my working directory: "C:/Users/SJ/datacleaningproject")
        
     		  >getwd()
        
     		  [1] "C:/Users/SJ/datacleaningproject"
        
#### Create a tidy data via a R script called run_analysis.R
      
 * Preparation:  data sets and script
     + The data sets and run_analysis.R must be in same the working directory.
           (It is based on one of the requirements this project: The code should have 
            a file run_analysis.R in the main directory that can be run as long as the Samsung
            data is in your working directory. 
            (see "Instructions and Requirements" section in README.md)
      
     + The input raw data for the run_analys.R are:
        
            ./train/X_train.txt, ./train/y_train.txt, subject_train.txt;
            ./test/X_test.txt, ./test/y_test.txt,  subjecct_test.txt;
            ./activity_labels.txt, ./features.txt
        
     + The output tidy data created from run_analysis.R are:
            ./tidy_average_data.txt (180 rows)
            ./combinedcleaningdata.txt (optional)
        
 * How the script run_analysis.R works via Rstudio
     + usage:
     
      		     > source("run_analysis.R") ## load the script
      		     > run_analysis() ##run the script
       
     + There are 5 main steps in run_analysis.R to process the raw data sets and create the tidy data set.

         Step-0: Reminder -- to install special package "reshape2".
                 It is necessary to install and to load the package "reshape2" before to perform
                  any processes.      
                  
         Step-1: Merges the training and the test data sets to create one data set (such as):
              Load and read the input raw sets; merge three pairs data set (e.g.: X_train.txt, X_test.txt;
              y_train.txt, y_test.txt; subject_train.txt, subject_text.txt) into three single data set
              via "rbind" function.
            
         Setp-2: Extracts only the measurements on the mean and standard deviation for each measurement.
              This step is mainly done by the "grep" function by providing the key search patterns
              "-mean\\(\\)|-std\\(\\)".
            
            ++ column names from the data sets were changed into lower-case to avoid any uncessary typos
               (based on the intruction from the "Week4 slide-notes: Editing Text Variables" from 
               Coursera course Getting and Cleaning Data); characters "()" were replaced "" and
               characters "-" was replaced to "." via "gsub" function.
               
         Step-3: Uses descriptive activity names to name the activities in the data set.
              This step is mainly to produce a one-column data frame called "joinlabel" containing
              descriptive activity names.
            
         Step-4: Appropriately labels the data set with descriptive activity names.
              The step is mainly to combine three joined data frames into one data frame called
              "cleandata". This is the first cleaned data frame toward to the final tidy data set.
              An (optional/temporary) output file is created called "combinedcleandata.txt" just in case
              for an emergency.
            
         Step-5: Creates a second, independent tidy data set with the average of each variable
              for each activity and each subject.
                          
              + The final tidy data frame called "tidydfrm" via "melt" function and then "dcast" function.
            
              + Finally, a file called "tidy_average_data.txt" was created via "write.table" function.
                This is the final output tidy processed data.
              
              + The detailed description of "tidy_average_data.txt" and the given raw data set
                are in the sections of "Tidy data set" and "Original raw data sets" respectively.

-------------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------------
#### R code: run_analysis.R

	## run_analysis.R
	## author: sjchan-ds (gitHub username)
	## 
	## The purpose of this project is to demonstrate course students' ability to collect,
	## work with, and clean a data set. The goal is to prepare tidy data that can be used
	## for later analysis.
	## This script is written for creating a tidy data file that can be used for later analysis.
	## There are five main steps to fulfill the above goal.
	##
	## input files: x_train.txt,x_test.txt,y_train.txt,y_test.txt,subject_train.txt,subject_test.txt
	##              features.txt, activity_labels.txt
	## output files: tidy_average_data.txt, combinedcleaningdata.txt
	##
	## required special package: reshape2
	##
	## usage in R:
	## Requirement: the data files and run_analysis.R should be in the same working directory in Rstudio
	##
	## > source("run_analysis.R")
	## > run_analysis()
        ##  OR
	## > ra <- run_analysis()
	## > ra
	## [1] "TRUE" ## re-confirm the cleaning process has been performed and a tidy data file
	##               has been created.
	##
	#########################################################################################
	#########################################################################################
	##
	run_analysis <- function() {
	## 
	#########################################################################################
	## Step 0: load the required special package: reshape2 (to use melt fuction and dcast function)
	##         melt function and dcast function will be used in Step 5
	##
	     if (!("reshape2" %in% rownames(installed.packages())) ) {
	        stop ("Please install required package: reshape2!\n")
	     } 
	
	## Load the required package: reshape2
	     library(reshape2)
	
	#########################################################################################
	## Step 1: Merges the training and the test sets to create one data set
	##
	## Three pairs of data (training and test data sets) need to be merged together
	## They are: X_train.txt, X_test.txt; (data set)
	##           y_train.txt, y_test.txt; (label-data set)
	##           subject_train.txt, subject_test.txt (subject-data set)
	##   
	
	## load/read the data sets and then merge the data sets
	     cat("\n")
	     cat("Step1: Merges the training and the test set to create on data set.\n")
	####### read and merge data set pair##################################
	     traindata <- read.table("./train/X_train.txt")
	     testdata  <- read.table("./test/X_test.txt")
	     joindata  <- rbind(traindata, testdata) 
	
	## cross-check dimensions: (observations/rows, variables/columns)
	     dim(traindata) ##  (7352, 561)
	     dim(testdata)  ##  (2947, 561)
	     dim(joindata)  ## (10299, 561)
	
	####### read and merge label-data set pair ##############################
	     trainlabel <- read.table("./train/y_train.txt")
	     testlabel  <- read.table("./test/y_test.txt")
	     joinlabel  <- rbind(trainlabel, testlabel)
	
	## cross-check dimensions: (observations/rows, variables/columns)
	     dim(trainlabel) ## (7352, 1)
	     dim(testlabel)  ## (2947, 1)
	     dim(joinlabel)  ##(10299, 1)
	
	### read and merge subject-data set pair #################################
	     trainsubject <- read.table("./train/subject_train.txt")
	     testsubject  <- read.table("./test/subject_test.txt")
	     joinsubject  <- rbind(trainsubject, testsubject)
	
	##  cross-check dimensions: meanStdIndex <- grep("-mean\\(\\) | -std\\(\\)", features[, 2])
	     dim(trainsubject) ##  (7352, 1)
	     dim(testsubject)  ##  (2947, 1)
	     dim(joinsubject)  ## (10299, 1)
	
	#########################################################################################
	## Step 2: Extracts only the measurements on the mean and standard deviation for 
	##      each measurement.
	##
	
	     cat("\n")
	     cat("Step2: Extracts only the measurements on the mean and standard deviation for each measurement.\n")
	##
	### In order to extract the measurements on the mean and standard deviation,
	##  I need locate variable names (column names) related to "mean" and
	##  "standard deviation" stored in the file "features.txt" via the command grep
	
	     features <- read.table("features.txt") ##read/load the file
	## cross-check dimensions: (rows, columns)
	     dim(features) ## (561, 2)
	
	## locate column names with "-mean()" or "-std()" in any rows in column 2
	     meanstdindex <- grep("-mean\\(\\)|-std\\(\\)", features[, 2])
	
	##cross-check length(meanstdindex)
	     length(meanstdindex) ## 66 variables
	
	## only select those columns/measurements on the mean and standard deviation
	## make a new data frame called joindatanew
	     joindatanew <- joindata[, meanstdindex] 
	
	## cross-check dimensions: (rows, columns)
	     dim(joindatanew)  ##(10299,66)
	
	## put the column names into the new data frame joindatanew
	     colnames(joindatanew) <- features[meanstdindex, 2] 
	
	## remove the bad characters such as "()", "-" in colnames, also lower the case if possible
	##   in order to avoid any unnecessary errors in later analysis
	##
	     colnames(joindatanew) <- gsub("\\(|\\)", "", colnames(joindatanew)) 
	     colnames(joindatanew) <- gsub("-", ".", colnames(joindatanew))
	     colnames(joindatanew) <- tolower(colnames(joindatanew))
	
	#########################################################################################
	## Step 3: Uses descriptive activity names to name the activities in the data set.
	
	     cat("\n")
	     cat("Step3: Uses descriptive activity names to name the activities in the data set.\n")
	
	## Firstly, it is necessary to load/read the file containing full activity names
	     activity <- read.table("activity_labels.txt")
	
	## Remove bad characters such as "_" and also lower case in the activity names/row names
	     activity[, 2] <- tolower(gsub("_", "", activity[, 2]))
	
	## Create a new activitylabel vector containing descriptive activity names with
	## the length of rows of joinlabel[, 1] 
	     activitylabel <- activity[joinlabel[, 1], 2]
	
	## Replace the 'activity numbers' to descriptive activity names in joinlabel data frame
	     joinlabel[, 1] <- activitylabel 
	
	## Give a column name to the column in the joinlabel data frame (one column data frame)
	    colnames(joinlabel) <- "activity"
	
	#########################################################################################
	## Step 4: Appropriately labels the data set with descriptive activity names.
	##      (i.e.: create a "clean" data set with labels (colnames and rownames))
	
	     cat("\n")
	     cat("Step4: Appropriately labels the data set with descriptiv activity names.\n")
	
	##  Firstly, give a column name to the column of the joinsubject data frame (one column data frame)
	     colnames(joinsubject) <- "subject"
	
	##  Combine three working dataframes (joinsubject, joinlabel and joindatanew) into one 
	##  single data frame via command cbind
	
	     cleandata <- cbind(joinsubject, joinlabel, joindatanew)
	
	## Cross-check dimensions: (nrows, ncolumns)
	     dim(cleandata) ## (10299    68)
	
	
	##  Optional: produce an output file that is stored the the above 'merged data set with labels'
	##            in case it will be useful.
	
	     write.table(cleandata, "combinedcleandata.txt")
	
	#########################################################################################
	## Step 5: Creates a second, independent tidy data set with the average of each variable
	##      for each activity and each subject. 
	##
	     cat("\n")
	     cat("Step5: Creates a independent tidy data set with the average of each variable for each activity and each subject.\n")
	
	## Reshape the data: generate skinny data via melt function
	## Melt the cleadata data set before decasting
	     meltdfrm <- melt(cleandata, id=c("activity", "subject"))
	
	## Cast the melt dataset based on the average of each variable for each activity and each subject
	     tidydfrm <- dcast(meltdfrm, activity + subject ~ variable, mean)
	
	## Create a file containing the tidy data set
	     write.table(tidydfrm, "tidy_average_data.txt", row.names = F, col.names= T, sep = "\t")
	
	     cat("")
	     cat("DONE: a tidy data file has been created in the working directory!\n")
	     cat("")
	     workdone <- "TRUE"
	
	} ##end of run_analysis
	###### End of R script ##################################################################
	#########################################################################################


=============================================================================================================








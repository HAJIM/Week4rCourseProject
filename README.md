*******************************************************************
Project content:                                                  *  
                                                                  *
run_analysis.R : Script of R for the data set                     *  
Tidy_Data.txt : the final data after applying run_analysis.R      *
                                                                  * 
CodeBook.md : the referencebook forTidy_Data.txt                  *
                                                                  *
README.md : comments and discription of the script run_analysis.R *
******************************************************************
<p><h1>First steps:<h1></p>

<p> We download the zip file and unzip it and then load the necessary libraries </p>
```{r eval=FALSE}
f<-"~/Data_science/Getting_and_Cleaning_Data/Activity_Recognition/"
setwd(f)

library(dplyr)
library(data.table)

link<-"https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip"
download.file(link,destfile = "Activity_Recognition.zip")
unzip ("Activity_Recognition.zip", exdir = "f")
```

<p> Reading the Metadata:</p> 

```{r eval=FALSE}
features_names  <- tbl_df(read.table("UCI HAR Dataset/features.txt"))
activity_labels <- tbl_df(read.table("UCI HAR Dataset/activity_labels.txt"))
```
<h1> Read test & training data </h1> 
```{r eval=FALSE}
subject_train<-tbl_df(read.table("UCI HAR Dataset/train/subject_train.txt"))
subject_test<-tbl_df(read.table("UCI HAR Dataset/test/subject_test.txt"))

features_train <- tbl_df(read.table("UCI HAR Dataset/train/X_train.txt"))
features_test  <- tbl_df(read.table("UCI HAR Dataset/test/X_test.txt"))

activity_train <-tbl_df(read.table("UCI HAR Dataset/train/y_train.txt"))
activity_test  <-tbl_df(read.table("UCI HAR Dataset/test/y_test.txt"))

```
<p> Creating one data set from the train and test data sets </p> 
```{r eval=FALSE}
subject <-  rbind(subject_train, subject_test)
activity <- rbind(activity_train, activity_test)
features <- rbind(features_train, features_test)

```
<p> Proper naming for columns </p> 
```{r eval=FALSE}
colnames(features) <- t(features_names[2])
colnames(activity)<-"activity"
colnames(subject) <- "subject"

```
<p> Merging the data</p>
```{r eval=FALSE}
merged_data <- cbind(features,activity,subject)
```

<h1>Extracting the measurements on the mean & and std</h1>
```{r eval=FALSE}
columns_of_mean_and_std <- grep(".*[Mm]ean.*|.*[Ss]td.*", names(merged_data))
columns_needed <- c(columns_of_mean_and_std, 562, 563) #how many colums we need
extract <- merged_data[,columns_needed]
```
<h1>Discriptive activity names for data set</h1>
```{r eval=FALSE}
extract$activity <- as.character(extract$activity) #change as character in order to accept the names
for (i in 1:6)
             {
  extract$activity[extract$activity == i] <- as.character(activity_labels[i,2])
            }

extract$activity <- as.factor(extract$activity)#Make it a factor with levels

#Repalce with with discreptive names
names(extract)<-gsub("Acc", "Accelerometer", names(extract))
names(extract)<-gsub("Gyro", "Gyroscope", names(extract))
names(extract)<-gsub("BodyBody", "Body", names(extract))
names(extract)<-gsub("Mag", "Magnitude", names(extract))
names(extract)<-gsub("^t", "Time", names(extract))
names(extract)<-gsub("^f", "Frequency", names(extract))
names(extract)<-gsub("tBody", "TimeBody", names(extract))
names(extract)<-gsub("-mean()", "Mean", names(extract), ignore.case = T)
names(extract)<-gsub("-std()", "StandardDeviation", names(extract), ignore.case = T)
names(extract)<-gsub("-freq()", "Frequency", names(extract), ignore.case = T)
names(extract)<-gsub("angle", "Angle", names(extract))
names(extract)<-gsub("gravity", "Gravity", names(extract))
```
<h1>Creating a tidy data set</h1>
```{r eval=FALSE}

extract$subject <- as.factor(extract$subject)#Turn the subject to factor with levels
extract <- data.table(extract)

final_data <- aggregate(. ~subject + activity, extract, mean) #Average for each activity and subject
final_data <- final_data[order(final_data$subject,final_data$activity),]
write.table(final_data, file = "Tidy_Data.txt", row.names = F)
```
```{r echo=FALSE}
head(final_data)
```

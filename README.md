Getting and Cleaning Data - Course Project for Week 4
=====================================================

I included the download of the complete data (the zip file). Therefore the data set in the working directory is not necessary. If the download of the zip file doesn't work though you will have to move the Samsung data into a sub directory /pdata inside your working directory though. Thanks and have fun :)

This file describes how my run_analysis.R script works.
+ put run_analysis.R in your working directory
+ run run_analysis.R (eg working with RStudio open the file, mark all and click Run)
+ the script will then do the following:
        # download zip-file (from "https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip") to folder "pdata" and extract it there -> folder "UCI HAR Dataset" is inside "pdata"
        # read test data and add subjects and activities as further columns (by using cbind)
        # read training data and add subjects and activities as further columns (by using cbind)
        # merge test and train data by using rbind (trainData is added "below" testData)
        # read activity labels
        # read features and make them "nicer"
        # we only want mean and standard deviation values plus the columns subject(=562) and acitivity(=563)
        # now we really choose the mean+std+subject+activity columns from the merged dataset
        # add column names
        # make them all lower case to be more tidy
        # we replace the index of the activity with its real name by means of a for loop that runs through all 6 activities
        # subject and activity are made into factor variables to be able to group by them (function aggregate)
        # aggregate the data by subject and activity -> mean of every variable considering every subject and every activity of that subject are calculated
        # since we grouped by subject and activity the last two columns don't make sense anymore and we make them NULL
+ in the step before the last step the TIDY DATASET IS SAVED AS tidy.txt in your working directory (not in /pdata)
+ the last step shows the head of tidy

Generally speaking this script expects the data structure of the given data set not to change.

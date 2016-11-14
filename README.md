# Hadoop-File-Word-Count
This porject counts the occurence of a word in all the files present in the hadoop directory.

## Design Description:
•	There are two jobs in wordcount class file.  
•	First job takes the input files and returns intermediate output where count of words for each file is visible. The first job uses mapper 1 and reducer 1.   
•	Mapper 1, read the input file per line. The line is first converted into lowercase and the words are extracted from the line. The words are checked to see if it only contains characters, there are no spaces and no special characters.   
•	Mapper 1 returns a string that consist of word and the filename and 1 to the Reducer 1. The Reducer 1 calculates the occurrence of a word per file and store the result to an intermediate file.   
•	The second job takes the intermediate input file and returns final output file where the count for word for all files is present. The second job uses mapper2 and reducer2.   
•	The mapper 2 extracts the word from the string sent to it from the intermediate file send the word and 1 to reducer 2.  
•	The reducer 2 calculates the sum of a word in all files and the final output is then written to the hadoop output folder.  

### Install standalone hadoop single node cluster
Refer to installation steps in the repository

### Steps to execute are 
• To start single node custer :   
 /home/user/hadoop-2.7.3/sbin/start-all.sh  

• To check status type:  
jps  

• To stop single node custer :  
/home/user/hadoop-2.7.3/sbin/stop-all.sh  

• To start executing files go to :  
cd ../hadoop-2.7.3/bin

• To create directory :  
hadoop dfs -mkdir /wordcount

• To copy file from local to network :  
hadoop dfs -put /home/user/hadoop_spark_scala/files /wordcount/input

• To check all files are present on hadoop server :  
hadoop dfs -ls /wordcount

• To compile jar of hadoop code :  
hadoop jar /home/user/hadoop_spark_scala/WordCountCode.jar WordCountClass /wordcount/input /wordcount/output

• To see the output:  
hadoop dfs -cat /wordcount/output/part-r-00000

• To remove the all intermediate and output file  
hadoop dfs -rm -r /wordcount/intermediate  
hadoop dfs -rm -r /wordcount/output



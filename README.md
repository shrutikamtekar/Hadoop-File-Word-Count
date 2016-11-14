# Hadoop-File-Word-Count
This porject counts the occurence of a word in all the files present in the hadoop directory.

## Design Description:
•	There are two jobs in wordcount class file,
•	First job takes the input files and returns intermediate output where count of words for each file is visible. The first job uses mapper 1 and reducer 1. 
•	Mapper 1, read the input file per line. The line is first converted into lowercase and the words are extracted from the line. The words are checked to see if it only contains characters, there are no spaces and no special characters. 
•	Mapper 1 returns a string that consist of word and the filename and 1 to the Reducer 1. The Reducer 1 calculates the occurrence of a word per file and store the result to an intermediate file. 
•	The second job takes the intermediate input file and returns final output file where the count for word for all files is present. The second job uses mapper2 and reducer2. 
•	The mapper 2 extracts the word from the string sent to it from the intermediate file send the word and 1 to reducer 2.
•	The reducer 2 calculates the sum of a word in all files and the final output is then written to the hadoop output folder.

### Install hadoop standalone single cluster
Refer to installation steps in the repository

### Steps to execute are 



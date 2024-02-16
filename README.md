# HadoopWordCount
This project contains a Hadoop MapReduce job for counting the frequency of words in a given input text file.

## Components

- `WordCount.java`: This is the main driver class that configures and runs the MapReduce job. It sets up the job's name, the input and output data formats, and the mapper and reducer classes.

- `WordCountMapper.java`: This mapper class extends `Mapper` and overrides the `map` method. It tokenizes the input text into words and writes each word to the context with an initial count of one.

- `WordCountReducer.java`: This reducer class extends `Reducer` and overrides the `reduce` method. It sums up the counts for each word and writes the final result to the context.

## Usage

To run this MapReduce job, you will need a Hadoop cluster set up and configured. Compile these classes and create a JAR file.

## Steps

- After creating a jar, follow the steps to run the wordcount job on a hadoop container

- 1. Copy the jar from local file to the name node
-    docker cp [PATH_TO_JAR] namenode:/tmp


- 2. Access the terminal of hadoop master container using the command below:

- docker exec -it namenode /bin/bash

- 3. Once you login to the namenode, create a directory to store the inputs.
-   hdfs dfs -mkdir /input

- 4. Copy the file to HDFS using the hdfs dfs -put command

-  hdfs dfs -put /path/to/your/localfile.txt /input

-  hadoop jar averageTempCalculator-1.0-SNAPSHOT.jar org.example.Temperature input/2024.csv output1







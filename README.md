# Apache Kafka - Stock Market Simulated

Technology used: Python, AWS (EC2, S3, Crawler, Amazon Athena)

## Abstract

The goal of this project was to understand how Apache Kafka Streams works. For training purposes, I used an AWS free t2.micro instance and simulated the stream of data to avoid memory problems on the AWS instance. Each event in the simulated stream was created as a sample JSON file from an existing dataset. The streamed data was uploaded to an S3 bucket and analyzed by a Crawler, which created a table schema in the AWS Glue Data Catalog. This allowed me to perform queries in Amazon Athena.

## Process

Setup Kafka server on EC2 machine:

1. Created a free AWS t2.micro instance and ran it using secure shell.  
2. Downloaded the actual versions of Kafka and Java on the instance.  
3. Accessed the EC2 machine outside the network using the public IPv4 address listed in the AWS instance description.  
4. Started the Zookeeper and Kafka servers on top of the public IPv4 address (each on a different shell).  
5. Added inbound security rules.  
6. Created a topic and ran the producer on another shell.  
7. Started the consumer on another shell.  

Jupyter Notebooks with producer and consumer configurations:

[*kafka-producer.ipynb*](https://github.com/Zandersan/Apache-Kafka/blob/main/kafka-producer.ipynb)

[*kafka-consumer.ipynb*](https://github.com/Zandersan/Apache-Kafka/blob/main/kafka-consumer.ipynb)  

## Output

As long as the servers and both scripts were running, new data were uploaded to the S3 bucket and made available for querying in Amazon Athena.

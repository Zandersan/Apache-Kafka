# Apache Kafka - Stock Market Simulated

Technology used: *AWS (EC2, S3, Crawler, Amazon Athena), python*


## Abstract
The goal of the project was to get to know how Apache Kafka Streams works. For training purposes, I used an AWS free t2.micro machine and simulated the stream of the data to avoid memory problems on the AWS instance. Each event in the simulated streaming was created as a sample JSON file from an existing dataset. The streamed data was uploaded to an S3 bucket and analyzed by a Crawler, which created a table schema in the AWS Glue Data Catalog. That allowed me to perform queries in Amazon Athena.

## Process

Setup Kafka server on EC2 machine:

1. Creating free AWS instance t2.micro and running it using secure shell
2. Dowloading actual versions of kafka and java on the instance
3. Accessing EC2 machine outside the network using public IPv4 address listed in AWS instance description
4. Starting zookeeper and kafka servers on top of public IPv4 address (each on other shell)
5. Adding inbound security rules
6. Creating topic and running the producer on the another shell
7.  Starting consumer on the another shell


Jupyter Notebooks with producer and consumer configurations:

[*kafka-producer.ipynb*](https://github.com/lucjankonopka/kafka-stock-market/blob/main/kafka-producer.ipynb)

[*kafka-consumer.ipynb*](https://github.com/lucjankonopka/kafka-stock-market/blob/main/kafka-consumer.ipynb)


## Output

As long as the servers and both scripts were running, new data were uploaded to the S3 bucket and made available for querying in Amazon Athena.

collect and process streaming data
eg: Application logs, Metrics, Click streams, IoT telemetry data

1. Kinesis Data streams - capture, process and store data streams, retention is between 1 and 365 days, billing is per shard, replay data, data is immutable. Producers: AWS SDK, Kinesis Producer Library, Kinesis Agent. Consumers: Kinesis Client Library, AWS SDK, [[Lambda]], Kinesis Data fire hose, Kinesis data analytics
2. Kinesis Data Firehose - load data into AWS data stores Consumers: Kinesis data streams, CLoudwatch, AWS IOT. Can use [[Lambda]] to transform. Can write to AWS destinations like [[S3]], Elastic search, Redshift, splunk, momgodb etc. Full managed, no admin, autoscale, serverless, near real time, can send data [[S3]] bucket, No data store, cant replay
4. Kinesis Data Analytics - analyse data streams with SQL or Apache Flink. Producers : data streams and fire hose, consumers: data streams and fire hose, server less, real time, autoscaling, used for dashboards
5. Kinesis Video Streams -  capture, process and store video streams
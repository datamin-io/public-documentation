# AWS S3

**Integration type**:  `Push`

AWS Lambda allows you to listen to new file arrivals on AWS S3 buckets of your choice. Therefore these data can immediately be streamed to Ylem by triggering our [API for pipelines](../../api/api-endpoints.md#run-pipeline).

You can write a basic AWS Lambda function on your own and stream data from AWS S3 to Ylem in real time.

Or use our [open-source trigger library](https://github.com/ylem-co/s3-lambda-trigger) which has a full installation and usage guide in the README file.


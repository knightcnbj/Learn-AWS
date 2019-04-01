# Learn-AWS
guided by CMSC389L at UMD

a useful link: https://www.expeditedssl.com/aws-in-plain-english

Structures:
1. Compute
    1. EC2: computing cores, multi VM running on a single server managed by hypervisor (similar to OS supervisor) provides OS isolation

    2. Lambda: run code without provisioning / managing new servers. Only pay for the compute time.

    3. ECS + Docker: cluster of EC2 in containers

2. Data + Storage
    1. S3 

    2. Cloudfront: CDN

    3. DynamoDB: key-val / document NoSQL in-memory DB with primary key supporting indexing (secondary indexing (sort key))

    4. ElasticSearch: search engine, DB is not good for searching complex query. Search engine supports 1. find doc with certain terms and phrases, 2. score and sort by relevance, 3. perform complex query ops

3. Networking
    1. ALBs: Load Balancer to avoid single point failure and distribute traffic uniformly to multi server. needs to able to 1. detect dead server, 2. avoid heavy load on one server, 3. spin up new server when too much load. Using Round Robin / Metric-based / hashing. LB on many layer (App / Network / classic)

    2. SQS: message queue enables async comm of message between processes, guarantee at least delivered once (use timeout to prevent multi delivery). Short polling: immediately return if no message available VS Long polling: wait until a message is available 

    3. API Gateway: managed infra used to build out web based REST API

4. Infra Management
    1. Auto Scaling

    2. CloudFormation: manage your cloud infra. it supports: 1. specify the state you want to achieve and let tool figure how, 2. roll back, 3. abstract away the AWS API, 3. reproducible (staging -> prod), 4. versionable (git). Using YAML or JSON format config file.
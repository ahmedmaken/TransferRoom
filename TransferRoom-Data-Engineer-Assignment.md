<img width="390" alt="image" src="https://github.com/user-attachments/assets/abae246a-5bdf-42ef-9d15-dacac5cab744" />

# Data Engineer Assignment

## Objective
Design a scalable and efficient data architecture that seamlessly ingests large volumes of data for both OLTP and OLAP use cases. Emphasize best practices to enhance performance, optimize costs, and uphold the highest security standards


## Current Solution

* Customers leverage the platform via conventional native web and mobile experiences.
* In addition, large and expensive OLAP and OLTP processes run on a continuous basis as well as a large number of scheduled processes and jobs.
* All these processes connect to the primary production SQL Server database.

<img width="800" alt="image" src="https://github.com/user-attachments/assets/a8cae9ec-9c15-4283-9c40-60ec2d95c843" />

## Issues with current solution
* SQL server is not inherently horizontally scaleable which means that as the volume of data increase, it will become difficult of manage operationally
* Prod server is being used for all analytical usecases without having prod realtime replica. This can severely degrade the prod server performance and can cause queries to fail and even data loss
* No data modelling is done on SQL server optimised for data extraction
* No role based access management is in place
* No PII and sensitive data handling in place
* No Data testing and validation in place
* No monitoring and alerting in place for job completion, Failure notifications, cost alerts and resource consumption alerts
* No infrastructure as a code present


## What we need?
* Data warehouse capable of ingesting realtime and batch data
* Medallion architecture to separate ingestion layer from reporting layer
* Config driven data pipelines to enable code reusing
* CICD
* PII and sensitive data handelling
* Monitoring and alerting
* Infrastructure as a code


## Proposed Solution: Architecture
<img width="992" alt="image" src="https://github.com/user-attachments/assets/3dc875be-ec78-4fbc-9b35-fb750178a272" />

## Realtime data ingestion
* DLT Pipelines
* Delta live streaming tables

## Handling PII and sensitive data
* Pulling sensitive and PII columns in separate schema in bronze
* Masking sensitive and PII data using encryption techniques and dynamic functions
* Limit access to sensitive datasets using roles-based access management

## Version Control
* One repo per data source
* Config driven data pipelines
* Single repo for infrastructure

## Platform Engineering
* Infrastructure as a code using terraform / azure resource manager

## CICD
Implementation of CICD using GitHub actions
* Formatting
* Linting
* Opensource vulnerability scan
* Infrastructure plan and deploy
* Unit tests
* Integration tests
* Preprod deployment
* Production release

## Monitoring and alerting
* Monitoring platform using Azure application insights
* Monitoring data pipelines using Monitoring framework
* Ingest pipelines attributes against tags in the transactional database
* Create Grafana dashboards
* Create slack/teams alerts for airflow jobs











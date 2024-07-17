# Gorgeous Cupcakes App

## Introduction

This is sample application that is showcasing infrastructure as a code. It will deploy php application to and connect it to the RDS database through private network.

## The package contents

- cupcakes.zip - a source code of the PHP Web App
- ngnix.conf - configuration file for nginx web server
- gorgeous_cupcakes_v1.sql - mysql dump file of the project database
- cf_vpc.yaml - template for creating network resources
- cf_rds.yaml - template for creating RDS database
- cf_ec2.yaml - template fpr creating EC2 instance

## How to deploy a project

1. Create AWS account
2. Create an S3 bucket for storing static files (cupcakes.zip and nginx.conf)
3. Upload cupcakes.zip and nginx.conf to your S3 bucket
4. Deploy cf_vpc.yaml through CloudFormation
5. Deploy cf_rds.yaml through CloudFormation (database name, user, password)
6. Deploy cf_ec2.yaml through CloudFormation (providing RDS host, database name, user, password and 3s bucket)

## Restore gorgeous_cupcakes_v1.sql dump file

`Please note that this is one time only operation after RDS database is created`

Using your EC2 instance, you can connect to RDS database and restore gorgeous_cupcakes_v1.sql using the following command:

`mysql -h [your-rds-hostname] -u yourusername -p yourpassword yourdatabase < gorgeous_cupcakes_v1.sql`

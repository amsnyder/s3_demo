# Read/Write to AWS S3 with boto3
This repository gives a simple demonstation of how to read and write data to an S3 bucket using boto3 in Python. It also covers how to get the version number of data you write to S3, as well as how to retreive a specific version number of a dataset.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Note: boto3 is and AWS SDK for Python. Find the docs [here](https://boto3.amazonaws.com/v1/documentation/api/latest/index.html).

## Prerequisites
This tutorial was set up for working with a bucket that requires credentials to access. It assumes that you have:
- an AWS account set up for you
- stored your AWS credentials file in `~/.aws/credentials`
- a bucket created that you can read and write to, with versioning enabled

For help setting up your account and credentials, please see [these instructions](https://github.com/amsnyder/s3_demo/blob/main/usgs_access.md).

### A quick note:

There are two main ways to interact with AWS through boto3: with a 'client' or with a 'resource'. To see an example of each, you can refer to [this short explainer](https://www.learnaws.org/2021/02/24/boto3-resource-client/). A quick summary of the differences:
- Clients are available for all AWS services, but sometimes the code is slightly more complicated to write.
- Resources are not available for all AWS services, but the code is sometimes simpler or more user-friendly to write.

In practice, I have not had any challenges understanding the client methods, and I have prepared this tutorial with that approach. You will commonly find either or both approaches in StackOverflow code, so it is important to be aware of the difference and know which approach you are using.

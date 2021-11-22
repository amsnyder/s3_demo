# S3 Account Set-up

1. Create an S3 account. You can submit a ticket for CTek in Jira to request an account. Please reach out if you would like an example of a ticket.

2. Install required software:

    a. **AWS CLI**: instructions to install are [here](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html). We won’t actually be using this, but it might become useful down the road if you want to interface with AWS through your command line.

    b. **Chocolatey** (only needed if you are on Windows): I followed [these instructions](https://docs.chocolatey.org/en-us/choco/setup#non-administrative-install) for non-admin install because I don’t have a pr account and they worked for me, but feel free to install however you like!

    c. **saml2aws**: you can install this using chocolatey if you are on Windows. Installation instructions can be found in the [‘Install’ section of the README](https://github.com/Versent/saml2aws#install).

    d. **boto3**: python package that can be installed using conda or pip

3. Create an S3 bucket. You can create a bucket using the [AWS CLI](https://docs.aws.amazon.com/cli/latest/reference/s3api/create-bucket.html), or follow these instructions to use the web GUI:

    a. Log in to the AWS web GUI [here](https://signin.aws.amazon.com/saml). You will want to select the option to log in to the dev environment with a developer role.

    b. Find the S3 Storage Service in the list of AWS services and click on it.

    c. Click the orange **Create bucket** button.

    d. Fill in the required information and create the bucket. Enable versioning if you would like to track versions of your data files. You **must** have a `wma:project_id` tag set that points to a billable project in [this list](https://code.chs.usgs.gov/ctek/assets/aws/mappings/-/blob/master/projects.yml).

    e. After you have created your bucket, you can add any sub-directories that you want to use with the web GUI as well. Note: You have read/write access to all of the buckets in S3 by default, so be careful not to tamper with other users' buckets.

4. Set up your S3 credentials on your local computer for programmatic access.

    a. Make sure you are connected through VPN.

    b. Open your command line, and configure your saml2aws by typing `configure saml2aws`. This will prompt you with a series of questions, and the responses will be stored in a file called ` ~\.saml2aws`. Here is a screenshot of my configuration:

    c. Create a new temporary access token by typing `saml2aws login`. Choose the option to work in the dev environment with the developer access. This will store a temporary set of credentials in your `~\.aws\credentials` file. Note that you will have to regenerate this token every hour by doing a saml2aws login, unless you change the aws_session_duration in your ` ~\.saml2aws` file.

5. You are ready to do the tutorial in the ipynb!
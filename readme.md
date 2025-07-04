# AWS Glue PySpark - Delta Lake (delta.io) Quick Start Guide

## Disclaimer:
This is a quick start guide for the Delta Lake (delta.io) Python Spark connector, running on AWS Glue.

It's also specifically configured for the following Glue version:
- AWS Glue 3.0  
    * Spark 3.1.1
    * Python 3.7
    * Delta Lake 1.0.0

Glue Configuration Reference: https://docs.aws.amazon.com/glue/latest/dg/add-job.html

Delta.io Reference: https://delta.io/ and  for more information

### Prerequisites:
    - Python 3.6 or higher
    - AWS CLI - Profile named 'dev' with Administrator Access (https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-profiles.html)
    
### Folder Structure:

```
glue-hudi-hello
├── README.md
├── cloud-formation
│   ├── command.md
│   └── GlueJobPySparkDelta.yaml
├── jars
│   ├── command.md
│   ├── delta-core_2.12-1.0.0.jar
│   └── upload_jar.py
├── job
│   ├── command.md
│   └── job.py
│   └── upload_job.py
├── requirements.txt

```

### Step 1: Create and activate a virtualenv:

Create a new virtual environment for the project in its root directory:

```
python3 -m venv venv
```

Activate it:

```
source venv/bin/activate
```

Run from the root directory the pip install to get boto3.

```
pip install -r requirements.txt
```

### Step 2: Create the AWS Resources:

Now, with a aws configured profile named as dev, cd into the cloud-formation folder and run the command in command.md.

As a AWS Cloud Formation exercise, read the command Parameters and how they are used on the GlueJobPySparkDelta.yaml file to dynamically create the Glue Job and S3 Bucket.

### Step 3: Upload the Job and Jars to S3:
cd into the job folder and run the command in command.md.

cd into the jars folder and run the commands in command.md. Note: There is one command for each jar.

### Step 4: Check AWS Resources results:

Log into aws console and check the Glue Job and S3 Bucket.

On the AWS Glue console, you can run the Glue Job by clicking on the job name.

After the job is finished, you can check the Glue Data Catalog and query the new database from AWS Athena.

On AWS Athena check for the database: delta_demo and for the table: delta_employee.



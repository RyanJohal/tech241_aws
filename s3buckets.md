# CLI commands for s3 buckets
1. Login to aws via gitbash
``` aws configure ```
2. Enter details
3. Make s3 bucket 
``` aws s3 mb s3://tech241-ryan-bucket --region eu-west-1 ```
4. Check if bucket has been made
``` aws s3 ls ```
5. Upload file to bucket
``` aws s3 cp testfile.txt s3://tech241-ryan-bucket ```
6. Download file from bucket
``` aws s3 sync s3://tech241-ryan-bucket s3_download ```
7. Delete file from bucket
``` aws s3 rm s3://tech241-ryan-bucket/testfile.txt ```
8. Delete all files in bucket
``` aws s3 rm s3://tech241-ryan-bucket --recursive ```
9.  Delete bucket
``` aws s3 rb s3://tech241-ryan-bucket ```

# Python scripts for the same steps
boto3 needs to be installed using ``` pip install boto3 ``` on the command line.

### Creating a bucket using python script
```python
# first thing is to import boto3 library
import boto3

# set up a s3 connection
s3 = boto3.client("s3")

# create a bucket, in the eu-west-1 region
bucket_name = s3.create_bucket(Bucket= "tech241-ryan-python-bucket", CreateBucketConfiguration={"LocationConstraint":"eu-west-1"})

# print bucket name to confirm working script
print(bucket_name)

```
### Uploading to bucket using python script
```python
# set up a s3 connection
s3 = boto3.client("s3")

# Upload file to S3
s3.upload_file(r"C:\Users\tazjo\PycharmProjects\Tech241\s3buckets\testfile.txt", "tech241-ryan-python-bucket", "testfile.txt")


# Print upload file to confirm working script
print("Succesfully Uploaded File")

```

### Read/download from bucket using python script
```python
# first thing is to import boto3 library
import boto3

# set up an S3 connection
s3 = boto3.client("s3")

# Download the file from S3
s3.download_file("tech241-ryan-python-bucket", "testfile.txt", "downloaded_file.txt")

# Print successfully uploaded to confirm working script
print("Successfully downloaded file")

```

### Deleting file from bucket using python script
```python
# Delete File
# Import boto3
import boto3

# Set up S3 connection
s3 = boto3.client("s3")

# Delete file from S3
s3.delete_object(Bucket="tech241-ryan-python-bucket", Key="testfile.txt")

# Print successfully uploaded to confirm working script
print("Successfully Deleted File")
```

### Deleting bucket using python script
```python
import boto3

s3 = boto3.resource("s3")

bucket = s3.Bucket("tech241-ryan-python-bucket")
response = bucket.delete()

print(response)
```



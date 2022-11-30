# Devops-Assignment

LOOM LINK: https://www.loom.com/share/8bd7b9b98a144178842ca8b57f3434dd

## Problem 1: Write IAM Policies
Usecase: You’re an Admin for an AWS account, you’ve to give permissions to the users based on their role in the project, so write IAM Policies for the following use cases:

For Project Owner:
Code Commit:
Should be able to do the following:
Update repo configuration.
Push code to any branch.
Create/Update/Close pull requests of any branch.
Create/Delete any branch.
Code Build:
Should be able to do the following:
Update Build configuration.
start/stop builds.
Lambda Function:
Should be able to do the following:
Update function code, and layers.
Update function configuration.
Update permissions.
API Gateway:
Should be able to do the following:
Create/update resources for the given API.
Cloud Watch:
Should be able to View/Query logs and metrics of the above resources.

For Developers:
Code Commit:
The User should be able to do the following prefixes
Push code to all branches, except branches with certain prefixes, let’s say "prod” and “staging”.
Create pull requests for all the branches.
Create/update/close pull requests for all branches, except branches with certain prefixes.
Cloud Watch:
Should be able to View/Query logs and metrics of the above resources.

Share policies for the above use cases with the names “project_owner_iam_policy.json”, and “developer_iam_policy.json” respectively.

## Problem 2: Serverless Django Deployment

Requirement: Deploy the Django app in AWS Lambda.


Instructions:

You must configure AWS RDS MySQL Database as Database for your Django project.
Make sure your app has an API that reads data from and writes data to MySQL Database.
You must host static files in AWS S3.
And your deployment stack should include below services (not limited to):
AWS API Gateway
AWS Lambda
AWS RDS
Note:

You can either use your personal project or any publicly available projects for this assignment, like Django Poll App
You can use any third-party tool like Zappa for deploying the project.

Explain your approach and show the demo of the deployed app in the loom video, push the application code to GitHub and share the link.

https://ry8rkus10k.execute-api.us-east-1.amazonaws.com/dev

## Problem 3: Rewrite Git History

Usecase: Remove all files and sub-folders within a given folder from the entire commit history of a git repository, while maintaining the commit structure and branches.


Motivation: It has been observed that some of the devs have committed creds to the repo, and some have committed their virtual environments to the repo. Now we need to purge all this info from the repository (entire commit history) while preserving the branches and commit history


Remove the following folder paths from the history of https://github.com/django/django

docs/
django/forms/

Explain your approach to your solution and provide a link to the modified repo.

## Problem 4: API Gateway to S3

Requirement: We need a PUT API in API Gateway which writes the request body of the API directly to the S3.


Write a script to automate the creation of the required AWS infrastructure using any of the following:

Serverless
AWS CDK
AWS Cloudformation
AWS SDKs

More details about the API:


Create an API such that a PUT request to the API should create an s3 object in the public-readable s3 bucket <s3_bucket> with the path <object_path> considering the request body as file content.


s3_bucket: should get it from the API stage variables.
object_path: should be prepared from the requested URL path.

        The URL pattern should be like https://example.com/api/{object_path}.


If the requested URL is https://example.com/api/users/1/articles/article_1.json then the object_path will be “users/1/articles/article_1.json”.


Example:


API Requested URL: https://example.com/api/users/1/articles/article_1.json


Request Body:


{

        "user_id": "1",

        "post_id": "123456",

        "post_title": "My New Article",

        "post_created_date": "2020-01-01 00:00:00",

        “last_updated_date”: "2020-01-01 00:00:00"

}


The above request should create an s3 object with the path “users/1/articles/article_1.json” in the s3_bucket configured.


Note:

You’ve to use only the below services for this API:
AWS API Gateway
AWS S3
AWS IAM
AWS Cloudformation
Make sure s3 objects in this bucket are publicly accessible.

 Invoke URL: https://xv3p5t18t6.execute-api.ap-south-1.amazonaws.com/dev
 
Upload process via CURL:
 curl --request PUT -H "Content-Type: application/json"  --data-binary "@myrequest.json" https://xv3p5t18t6.execute-api.ap-south-1.amazonaws.com/dev/apigtw-s3/myrequest.json


![image](https://user-images.githubusercontent.com/48557380/203707360-d9c26365-8bf8-46c7-a2d2-29ca29834d18.png)

LOOM LINK: https://www.loom.com/share/8bd7b9b98a144178842ca8b57f3434dd

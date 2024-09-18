# mlflow-twitter-sentiments-and-AWS
### MLflow on AWS
MLflow on AWS Setup:

    Login to AWS console.
    Create IAM user with AdministratorAccess
    Export the credentials in your AWS CLI by running "aws configure"
    Create a s3 bucket
    Create EC2 machine (Ubuntu) & add Security groups 5000 port

Run the following command on EC2 machine

sudo apt update

sudo apt install python3-pip

sudo pip3 install pipenv

sudo pip3 install virtualenv

mkdir mlflow

cd mlflow

pipenv install mlflow

pipenv install awscli

pipenv install boto3

pipenv shell


## Then set aws credentials
aws configure


#Finally 
mlflow server -h 0.0.0.0 --default-artifact-root s3://mlflow-twitter-bucket

#open Public IPv4 DNS to the port 5000


#set uri in your local terminal and in your code 
export MLFLOW_TRACKING_URI=http://ec2-18-234-243-105.compute-1.amazonaws.com:5000/
# For Ec2 
If you want to access the ec2 using the key.pem then make sure you create the key first before actually creating the ec2 using clf
## Create and save the key pair
aws ec2 create-key-pair \
  --key-name my-main-key \
  --query 'KeyMaterial' \
  --output text > my-main-key.pem

## Set secure permissions
chmod 400 my-main-key.pem

## Now run the command
$ aws cloudformation create-stack \
> --stack-name openserverstack \
> --template-url https://s3.us-east-2.amazonaws.com/cf-templates-pvztciwhb1n-us-east-2/2025-10-14T160101.756Zkrd-ec2main.yml

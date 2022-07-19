# Stacks Results
aws cloudformation list-stacks  
StackSummaries:
- CreationTime: '2022-07-19T20:55:16.414000+00:00'
  DriftInformation:
    StackDriftStatus: NOT_CHECKED
  StackId: arn:aws:cloudformation:us-east-1:257183649175:stack/uda-app/177d2870-07a5-11ed-ac09-121f400c2d29
  StackName: uda-app
  StackStatus: CREATE_COMPLETE
  TemplateDescription: Udacity CloudFormation Project to create HA application
- CreationTime: '2022-07-19T20:44:39.467000+00:00'
  DriftInformation:
    StackDriftStatus: NOT_CHECKED
  StackId: arn:aws:cloudformation:us-east-1:257183649175:stack/uda-infra/9bd6e950-07a3-11ed-b359-0acee5af9ba1
  StackName: uda-infra
  StackStatus: CREATE_COMPLETE
  TemplateDescription: Udacity CloudFormation Project to create Network of HA application

## Exports
aws cloudformation list-exports 
Exports:
- ExportingStackId: arn:aws:cloudformation:us-east-1:257183649175:stack/uda-app/177d2870-07a5-11ed-ac09-121f400c2d29
  Name: UdagramUdacityProject-Alb-Url
  Value: http://UdagramUdacityProject-Alb-2085056295.us-east-1.elb.amazonaws.com
- ExportingStackId: arn:aws:cloudformation:us-east-1:257183649175:stack/uda-infra/9bd6e950-07a3-11ed-b359-0acee5af9ba1
  Name: UdagramUdacityProject-BastionSecurityGroupId
  Value: sg-0a0e90091ca172d1c
- ExportingStackId: arn:aws:cloudformation:us-east-1:257183649175:stack/uda-infra/9bd6e950-07a3-11ed-b359-0acee5af9ba1
  Name: UdagramUdacityProject-BastionkeyPair
  Value: key-07699a80972c58a90
- ExportingStackId: arn:aws:cloudformation:us-east-1:257183649175:stack/uda-infra/9bd6e950-07a3-11ed-b359-0acee5af9ba1
  Name: UdagramUdacityProject-PrivateSubnet1
  Value: subnet-0470fd24048eb5676
- ExportingStackId: arn:aws:cloudformation:us-east-1:257183649175:stack/uda-infra/9bd6e950-07a3-11ed-b359-0acee5af9ba1
  Name: UdagramUdacityProject-PrivateSubnet2
  Value: subnet-07de7daad1d5f96ea
- ExportingStackId: arn:aws:cloudformation:us-east-1:257183649175:stack/uda-infra/9bd6e950-07a3-11ed-b359-0acee5af9ba1
  Name: UdagramUdacityProject-PrivateSubnets
  Value: subnet-0470fd24048eb5676,subnet-07de7daad1d5f96ea
- ExportingStackId: arn:aws:cloudformation:us-east-1:257183649175:stack/uda-infra/9bd6e950-07a3-11ed-b359-0acee5af9ba1
  Name: UdagramUdacityProject-PublicSubnet1
  Value: subnet-00b6bc184b2e7599b
- ExportingStackId: arn:aws:cloudformation:us-east-1:257183649175:stack/uda-infra/9bd6e950-07a3-11ed-b359-0acee5af9ba1
  Name: UdagramUdacityProject-PublicSubnet2                                                                                                                                                                                          
  Value: subnet-0feffc6830253b5f5
- ExportingStackId: arn:aws:cloudformation:us-east-1:257183649175:stack/uda-infra/9bd6e950-07a3-11ed-b359-0acee5af9ba1
  Name: UdagramUdacityProject-PublicSubnets
  Value: subnet-00b6bc184b2e7599b,subnet-0feffc6830253b5f5
- ExportingStackId: arn:aws:cloudformation:us-east-1:257183649175:stack/uda-infra/9bd6e950-07a3-11ed-b359-0acee5af9ba1
  Name: UdagramUdacityProject-VpcId
  Value: vpc-0c27ed7dee5631b46
- ExportingStackId: arn:aws:cloudformation:us-east-1:257183649175:stack/uda-app/177d2870-07a5-11ed-ac09-121f400c2d29
  Name: UdagramUdacityProject-WebServerkeyPairId
  Value: key-061b1f9403d616e4a
  
## Application
![image](https://user-images.githubusercontent.com/6891966/179848259-40c790bf-5374-4407-8bd1-d402493b9e69.png)
  
![image](https://user-images.githubusercontent.com/6891966/179848316-5f4b2cab-fb9f-4ef2-b01b-e45a7e59116c.png)
  
![image](https://user-images.githubusercontent.com/6891966/179848380-ad35cefc-fc72-468b-a402-3b8f941e0122.png)
  
![image](https://user-images.githubusercontent.com/6891966/179848415-7c96f765-ef01-4a36-9c42-b5acb105d72e.png)

## AWS S3
aws s3 ls
2022-07-19 22:55:23 alb-access-logs-udacity-project-2122345
2022-07-19 22:43:05 s3websitecontenettest12aq12443333

aws s3 ls s3://s3websitecontenettest12aq12443333
2022-07-19 22:44:05        157 index.html

cat index.html
<!DOCTYPE html>
<html>
<body>
<h2>Udagram HA application</h2>
<h1>Hello From CloudFormation</h1>
<p>home page from S3 bucket</p>
</body>
</html>

aws s3 ls s3://alb-access-logs-udacity-project-2122345/ALB-Access-Logs/AWSLogs/257183649175/elasticloadbalancing/us-east-1/2022/07/19/
2022-07-19 23:05:04        500 257183649175_elasticloadbalancing_us-east-1_app.UdagramUdacityProject-Alb.f829d0e48857e6fc_20220719T2105Z_34.194.197.50_vydl5ykk.log.gz
2022-07-19 23:05:04        386 257183649175_elasticloadbalancing_us-east-1_app.UdagramUdacityProject-Alb.f829d0e48857e6fc_20220719T2105Z_54.82.107.114_39xcffxu.log.gz
2022-07-19 23:10:04        538 257183649175_elasticloadbalancing_us-east-1_app.UdagramUdacityProject-Alb.f829d0e48857e6fc_20220719T2110Z_34.194.197.50_4dpwrpi0.log.gz

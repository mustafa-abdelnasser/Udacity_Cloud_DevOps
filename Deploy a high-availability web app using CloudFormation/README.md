# Deploy a High-Availability Web App using CloudFormation
Using CLoudFormation Templates and Parameters to create highly available web application running on Apache
- Cross AZ with Autoscaling and Application Load Balancer.
- Application code can be downloaded from S3 bucket using IAM Roles.
- Backend WebServers use NAT Gatways to get updates.
- Bastion host to manage our servers with custom security group and SSH Port.
- ALB access logs to S3 using S3 Bucket Policy

## Architecture
![image](https://user-images.githubusercontent.com/6891966/179841997-af683afb-9761-4e70-8a3d-80f14b0af67e.png)

## Templates
### udagram-udacity-infra.yaml with Udagram-udacity-infra-parameters.json
to create the required Infrastructure
- custom VPC with private subnets, public subnets, route tables
- Internet Gateway
- NAT Gatways with Elastic IPs
- KeyPairs to be generated and saved to SSM Systems Manager Parameter Store
- Bastion Host
    - customized SSH Port using userdata and security group with specific allowed source IP address.
    - IAM Role to acess SSM and Get Parameter
- Resource Tags with environment name.
- Export Stack outputs to be used by other templates


### udagram-udacity-app.yaml with Udagram-udacity-app-parameters.json
- Use the Exported outputs from infra template.
- Autoscaling group with ELB health checks to create webservers on different private subnets cross multiple AZs.
- Launch configuration with userdata and IamInstanceProfile to download the application from S3 bucket with needed GetObject IAM Policies and Roles.
- Application Load Balancer Internet facing wih multiple public subnets.
- Target Group with HTTP Health Checks.
- ALB security groups to accept HTTP traffic from the internet.
- webserver security group to only accept HTTP traffic from Application Load Balancer security group.
- ALB Listeners for HTTP
- Create new S3 bucket for ALB Access logs with the required Bucket Policy to write to S3.
- Output the application URL using ALB DNS name.

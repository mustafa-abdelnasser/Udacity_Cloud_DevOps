# Deploy Static Website on AWS Project1

## 1. S3 static website

### 1.1. create bucket
bucket_name: "udacity-static-website-s3-cloudfront-demo12345"

![](./vx_images/339155320226945.png =742x)

### 1.2. Bucket permissions (allow public access)

![](./vx_images/519423921232089.png =742x)

### 1.3. Configure Bucket Policy (allow public read)

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::udacity-static-website-s3-cloudfront-demo12345/*"
            ]
        }
    ]
}
```

![](vx_images/153104721249969.png =742x)

![](vx_images/4573222237438.png =742x)

### 1.4. Enable static website hosting
Bucket_webist_endpoint:
http://udacity-static-website-s3-cloudfront-demo12345.s3-website-us-east-1.amazonaws.com

![](vx_images/492015520247111.png =742x)

### 1.5. Upload the content of udacity-starter-website
using aws cli

```
$ cd udacity-starter-website
$ ls
css  img  index.html  __MACOSX  README.txt  vendor
$ aws s3 cp ./ s3://udacity-static-website-s3-cloudfront-demo12345 --recursive --exclude '__MACOSX/*' --exclude README.txt

$ aws s3 ls s3://udacity-static-website-s3-cloudfront-demo12345
                           PRE css/
                           PRE img/
                           PRE vendor/
2022-06-11 19:31:11        382 README.txt
2022-06-11 19:31:11       6285 index.html
```

![](vx_images/100833321236335.png =742x)


### 1.6. Test the bucket website endpoint
http://udacity-static-website-s3-cloudfront-demo12345.s3-website-us-east-1.amazonaws.com

![](vx_images/140855121247573.png =750x)


## 2. Distribute Website via CloudFront
### 2.1. Create CloudFront distribution
Distribution domain name
https://d3v06xgchlqf9h.cloudfront.net


![](vx_images/497840522245075.png =841x)

![](vx_images/331630722226316.png =841x)

![](vx_images/36290822248756.png =841x)

### 2.2. Check distribution domain name
https://d3v06xgchlqf9h.cloudfront.net
![](vx_images/202990922243892.png =841x)


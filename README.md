# resize-image-function
Here's an updated `README.md` file reflecting your use of Node.js for the Image Resizing project.

---

# Image Resizing using AWS Lambda

## Project Overview
This project is a serverless application built using AWS Lambda with Node.js to automatically resize images uploaded to an S3 bucket. When an image is uploaded, the Lambda function is triggered, and the image is resized to a predefined size. The resized image is then saved back to the S3 bucket. This solution is cost-effective and scalable, making it ideal for handling dynamic image resizing requirements.

## Features
- **Serverless Architecture**: The entire process is handled by AWS Lambda and S3 without the need for any servers.
- **Automated Image Resizing**: Automatically resizes images to a specified dimension upon upload.
- **Cost-Efficient**: Optimized for minimal cost using AWS's pay-as-you-go pricing model.
- **Scalability**: Leverages AWS's infrastructure to handle large-scale image resizing without manual intervention.

## Technologies Used
- **AWS Lambda**: The serverless compute service to run the image resizing function.
- **Amazon S3**: Used to store the original and resized images.
- **AWS IAM**: Configured roles and permissions to securely manage access to S3 and Lambda.
- **Node.js**: Used to write the Lambda function

## Prerequisites
- AWS Account with appropriate permissions to create and manage S3 buckets and Lambda functions.
- Basic knowledge of Node.js and AWS services.
- Familiarity with AWS CLI (optional).

## Project Structure
```
├── index.js             # Node.js script for the Lambda function
├── package.json         # Node.js dependencies
├── package-lock.json    # Node.js lock file for dependencies
└── README.md            # Project documentation
```

## Setup Instructions

### 1. Create an S3 Bucket
1. Sign in to your AWS Management Console.
2. Go to **S3** and create a new bucket (e.g., `my-image-bucket`).
3. Enable the bucket to trigger Lambda functions on object creation.

### 2. Configure AWS Lambda
1. Navigate to the **Lambda** service in the AWS Management Console.
2. Create a new Lambda function (e.g., `ImageResizerFunction`).
3. Choose **Node.js** as the runtime.
4. Upload the `index.js` code.
5. Set up a trigger for your S3 bucket to invoke the Lambda function on `ObjectCreated` events.
6. Assign the necessary IAM role with permissions to access S3 and CloudWatch.

### 3. Deploy the Lambda Function
1. Install dependencies using `npm install` (this will install `sharp` and any other required packages).
2. Deploy the Lambda function by uploading the code directly via the AWS Console or using the AWS CLI.

### 4. Testing the Application
1. Upload an image to the S3 bucket.
2. Check the resized image in the same or another S3 bucket folder.

## Usage
- To resize images, simply upload an image to the designated S3 bucket. The Lambda function will automatically resize the image and save the output in the specified location.

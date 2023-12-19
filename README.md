# Static-Website-on-S3-with-Terraform
## Overview
This project demonstrates how to create an S3 bucket and set up a static website on AWS using Terraform. 

## Prerequisites
AWS Account

Terraform Installed

## Project Steps
Follow these steps to create a static website on AWS using Terraform:

### Step 1: Create a Project Folder

mkdir my_S3_static_website

cd my_S3_static_website

### Step 2: Define AWS Provider
### Create a file named providers.tf to define the AWS provider.

provider "aws" {

  region = "us-east-1"
  
}

### Step 3: Initialize Terraform
### Run the following command to initialize Terraform:

terraform init

### Step 4: Create S3 Bucket
### Create a file named main.tf and define the S3 bucket resource.

resource "aws_s3_bucket" "mybucket" {
  
  bucket = var.bucket_name

}

### Create a file named variables.tf to define the bucket name variable.

variable "bucket_name" {

  default = "mys3bucketproject2023"

}

### Step 5: Upload Website Files
Add resources in main.tf to upload index.html, error.html, and profile.png.


### Step 6: Make the Bucket Public
Add resources in main.tf to set ownership controls and public access block.

### Step 7: Enable Static Website Hosting
Add resource in main.tf to configure static website hosting.

### Step 8: Outputs
### Create a file named outputs.tf to define the website endpoint output.

output "website_endpoint" {

  value = aws_s3_bucket.mybucket.website_endpoint

}

### Step 9: Apply Changes
### Apply the changes using the following command:

terraform apply -auto-approve

### Testing the Website

Visit the provided website endpoint to view the static website.

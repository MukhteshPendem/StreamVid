# StreamVid
A video streaming platform built with React, Spring Boot, AWS S3, and MySQL for scalable uploads and streaming.


# What to do before running the project -> AWS S3 Configuration for facilitating the BACKEND (Spring Boot Project)

## 1. Create an S3 Bucket
- Go to the **S3** service in the AWS Console.
- Click **Create bucket**.
- Provide a unique name for the bucket (e.g., `videostream-1325`).
- Choose the region (e.g., `ap-south-1`).
- Click **Create**.

## 2. Set Bucket Permissions
- Go to the **Permissions** tab of your bucket.
- **Bucket Policy** (for public access):
  ```json
  {
    "Version": "2012-10-17",
    "Statement": [
      {
        "Sid": "PublicReadGetObject",
        "Effect": "Allow",
        "Principal": "*",
        "Action": "s3:GetObject",
        "Resource": "arn:aws:s3:::<YOUR BUCKET NAME>/*"
      }
    ]
  }

## 3. Deselect the Block all Public access in the s3 bucket settings (for developing) 

## 4. Update application.properties
In your Spring Boot project, add the following configuration in the application.properties file:

cloud.aws.credentials.accessKey=_**your-access-key**_

cloud.aws.credentials.secretKey=_**your-secret-key**_

cloud.aws.region.static=_**your-region**_

cloud.aws.s3.bucket=_**your-bucket-name**_

## This repository combines two essential submodules, frontend and backend, that together form the complete project. To make sure everything works as intended, follow the instructions below to properly clone and update this repository.

# Cloning the Repository
This repository uses Git submodules to manage its dependencies (frontend and backend). Cloning with submodules ensures all necessary components are included.

# Steps to Clone

## Clone the repository along with its submodules using the following command:

_git clone --recurse-submodules **THISREPOLINK**_

# Why Use Submodules?
Git submodules allow us to maintain frontend and backend as separate, version-controlled projects within this repository. This structure provides:

**Consistency:** Each submodule is set to a specific commit compatible with this project.

**Modularity:** Submodules remain independent, making them easy to update or reuse in other projects.
# Updating Submodules
To fetch and apply any updates from the original repositories for frontend or backend, run:

**_git submodule update --remote --merge_**

This ensures you’re working with the latest versions of each submodule while keeping them in sync with the main project.

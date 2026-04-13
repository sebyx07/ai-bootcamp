# Teaching: What Is S3

## Context
The student may wonder "why not just save files on the server?" This challenge explains why cloud storage exists and introduces S3 concepts. This is an exposure module -- understanding is the goal.

## The challenge
Understand what S3 is, why it exists, and how it works conceptually. No actual S3 account needed.

## Your approach
1. Ask: "If users upload profile photos to your blog, where should those files go?"
2. Explain why NOT to store files in the database or on the server:
   - Database: files are too large, slows everything down
   - Server: if the server dies, files are lost; if you have multiple servers, files are only on one
3. Explain S3:
   - S3 = Simple Storage Service (by Amazon Web Services)
   - It stores files (called "objects") in containers (called "buckets")
   - Files are stored in the cloud -- reliable, scalable, accessible from anywhere
   - Every file gets a URL you can use to access it
4. Key S3 concepts:
   - **Bucket**: a container for files (like a folder)
   - **Object**: a file stored in a bucket (image, PDF, video, etc.)
   - **Key**: the path/name of the object within the bucket
   - **URL**: every object has a URL for access
5. Explain pre-signed URLs: temporary URLs that allow upload/download without sharing credentials
6. Mention alternatives: Google Cloud Storage, Azure Blob Storage, DigitalOcean Spaces (same concept)
7. Introduce LocalStack:
   - LocalStack is an open-source tool that emulates AWS services locally
   - We use it instead of paying for actual AWS — same API, runs on your machine
   - It runs as a Docker container (they already know Docker from Phase 02)
   - Set it up together:
     ```bash
     docker run -d -p 4566:4566 localstack/localstack
     ```
   - Create a bucket with the AWS CLI:
     ```bash
     aws --endpoint-url=http://localhost:4566 s3 mb s3://my-bootcamp-bucket
     ```
   - Install AWS CLI if needed: `pip install awscli-local` or `pip install awscli`
8. In Rails: Active Storage handles file uploads and can use S3 (or LocalStack) as the backend

## Prompting coaching
- "what is S3" -- ask for explanations
- "why not store files in the database" -- understand the problem
- "what is a bucket" -- learn S3 terminology

## Quiz questions
- What does S3 stand for?
- What is a "bucket" in S3?
- Why should you not store user-uploaded files directly in your database?
- What is a pre-signed URL?

## Hints (only if stuck)
1. Think of S3 as Dropbox for your application -- a place in the cloud to store files
2. A bucket is like a top-level folder; an object is a file inside that folder
3. Pre-signed URLs are like temporary access passes -- they expire after a set time

# Hosting the Accountable Website on AWS S3 Bucket

![alt text](Accountable.png)

# Steps to Host a Static Website on AWS S3

Follow these steps to easily host your static website using Amazon S3.

## 1. Create an S3 Bucket:

- Go to your AWS S3 dashboard and click on `Create bucket`.
- Name your bucket (e.g., `accountable-aws` if you're using a custom domain).
- Ensure you uncheck "Block all public access" if you plan to make your site public.

## 2. Upload Static Files:

- Upload your static files such as `index.html` and any other necessary files (e.g., images, CSS, JS).
- Simply drag and drop your files into the bucket or use the `Upload` button.

## 3. Configure Static Website Hosting:

- Go to the `Properties` tab of your S3 bucket.
- Scroll down to `Static website hosting` and click `Edit`.
- Enable static website hosting.
- Set your `Index Document` (e.g., `index.html`) and `Error Document` (e.g., `404.html`).
- Save your changes.

## 4. Update Bucket Policy:

- Go to the `Permissions` tab.
- Under `Bucket Policy`, click `Edit`.
- Add the necessary bucket policy to allow public access to the objects in your bucket. Example policy:
  ```json
  {
    "Version": "2012-10-17",
    "Statement": [
      {
        "Effect": "Allow",
        "Principal": "*",
        "Action": "s3:GetObject",
        "Resource": "arn:aws:s3:::your-bucket-name/*"
      }
    ]
  }
  ```

Replace your-bucket-name with your actual S3 bucket name.

## 5. Access the Website:

- Once everything is set up, you will receive a URL to access your static website.
- Go to the Properties tab and find the Static website hosting section.
- Copy the provided S3 website URL and paste it into your browser to access your site.

## 6. Optional: Custom Domain Setup

##### If you have a custom domain, follow these steps to configure it with your S3 bucket:

- Go to your domain registrar (e.g., GoDaddy, Namecheap).
- Set up a CNAME record pointing to your S3 bucket URL.
- Make sure your bucket name matches the domain (e.g., www.example.com should be the bucket name if you're setting up www.example.com).

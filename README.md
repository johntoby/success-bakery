# Success Bakery

A responsive, static website for Success Bakery in Port Harcourt. It uses the included bakery photos and has no build step or runtime dependencies.

## Preview locally

Open `index.html` in a browser, or serve the repository root with any local static web server.

## Deploy to Amazon S3 static website hosting

1. Create an S3 bucket for the website and enable **Static website hosting** in the bucket's Properties.
2. Set the index document to `index.html` and the error document to `error.html`.
3. Upload the site files to the bucket root. With the AWS CLI installed and configured, run this from the repository:

   ```powershell
   aws s3 sync . s3://YOUR_BUCKET_NAME --exclude ".git/*" --exclude "README.md" --exclude "LICENSE"
   ```

4. For a public S3 website endpoint, configure the bucket's public-access settings and bucket policy to allow `s3:GetObject` for the website files. Use the S3 website endpoint shown in the bucket's Static website hosting settings to visit the site.

S3 website endpoints serve public content over HTTP. For HTTPS or a custom domain, place Amazon CloudFront in front of the bucket.

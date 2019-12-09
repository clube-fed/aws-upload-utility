# aws-upload-utility
A simple node based upload utility for deploying files to the Clubessential s3 storage service. 

## Getting Started

- Install the javascript aws-sdk and dotenv packages to your folder (npm install --save-dev aws-sdk dotenv)
- Copy/clone variables.env and s3-upload.js files
- Run `node s3-upload` or add the `deploy-s3` npm script to your project
- Deploy files to s3 servers

## Quick notes

This package contains boilerplate code to deploy files to Clubessential's s3 storage buckets. The configuration happens in the `variables.env` folder, where you will be setting up the paths to and for your files. These files should exist in the root directory of your project.

Local paths would look something like this "./css/myfilename.css" (include the filename here)

Because s3 stores files as an object key for a bucket you can declare a "path" in the variables.env that will map your file to. This path will be created on the first run of this script and will allow you to simply overwrite the file on each run of the script. 

s3 paths would look something like this "sites/my-site-name/css" (do not include the filename here)

If you need help getting your s3 credentials, view the following guide:
https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/getting-your-credentials.html

# aws-upload-utility
A simple node based upload utility for deploying files to the Clubessential s3 storage service. 

## Getting Started

- Install the javascript `aws-sdk` and `dotenv` packages to your folder (npm install --save-dev aws-sdk dotenv)
- Copy/clone `variables.env` and `s3-upload.js` files
- Configure local and s3 routes for your project
- Run `node s3-upload` or use npm scripts in `package.json` and deploy files to the s3 server

## Quick notes

This package contains boilerplate code to deploy files to Clubessential's s3 storage buckets. The configuration happens in the `variables.env` folder, where you will be setting up the paths to and for your files. These files should exist in the root directory of your project.

Local paths would look something like this "./MYFOLDER/css

The s3-upload utility has been updated to accept node arguments that deploy specific files (i.e. you can deploy your CSS file only) and the `package.json` has some updated deploy scripts that you can utilize. If you want to customize these scripts or create your own, make sure your argument is updated in the s3-upload.js file and package.json. By default, the s3-upload utility uploads the CSS, bundled JS, and a login bundle JS (which is meant to exist on login pages and devoid of any axis scripts).

Because s3 stores files as an object key for a bucket you can declare a "path" in the variables.env that will map your file to. This path will be created on the first run of this script and will allow you to simply overwrite the file on each run of the script. The configuration automatically sets the files to be public so everything happens all at once without need for the AWS GUI or a file upload utility.

s3 paths would look something like this "sites/my-site-name/css" (do not include the filename here)

If you need help getting your s3 credentials, view the following guide:
https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/getting-your-credentials.html

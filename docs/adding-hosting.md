# Adding Hosting

The AWS Amplify CLI makes it easy to deploy our app to an Amazon S3 bucket and CloudFront.

## 1. Adding hosting, build and publish our application

1.1\. Using the Amplify CLI add hosting for the application and use the following values.

``` bash
amplify add hosting
```

? Select the environment setup: **PROD (S3 with CloudFront using HTTPS)**

? hosting bucket name **react-my-todos-20190709233955-hostingbucket** (Use default name)

? index doc for the website **index.html**

? error doc for the website **index.html**

1.2\. Publish your React application.

``` bash
amplify publish
```

? Are you sure you want to continue? **Yes**

1.3\. After your app is published, use the endpoint resulted to get into your application.
# Preparing your development environment

## 1. Create an IAM user with administrator privileges

1.1\. Open the IAM console at https://console.aws.amazon.com/iam/.

1.2\. Choose **Users**, then **Add user**.

1.3\. Type a name for your user `AmplifyWorkshopAdmin`, choose **Programmatic access** and click **Next: Permissions**.

![IAM User name](images/iam-user-name.png)

1.4\. Click **Attach permissions policies** and select **Administrator Access**, choose **Next: Tags**.

![User Policy](images/iam-user-policy.png)

1.5\. For **Add tags (optional)** section choose **Next: Review**.

1.6\. Click on **Create user**.

1.7\. To save the credentials, choose **Download .csv** and then save the file to a safe location, and **Close**.

![User Created](images/iam-user-created.png)

## 2. Create HTTPS Git credentials for AWS CodeCommit

2.1\. From the users list, click on **AmplifyWorkshopAdmin** user.

![IAM User select](images/iam-developer-user.png)

2.2\. On the user details page, choose the **Security Credentials** tab, and in **HTTPS Git credentials for AWS CodeCommit**, choose **Generate**.

![IAM User generate](images/iam-generate-git.png)

2.3\. Copy the user name and password that IAM generated for you, either by showing, copying, and then pasting this information into a secure file on your local computer, or by choosing **Download credentials** to download this information as a .CSV file.

![IAM User download](images/iam-git-credentials.png)

## 3. Create a Cloud9 instance for development

[!embed?max_width=1200](https://www.youtube.com/watch?v=JDHZOGMMkj8)

3.1\. Open the AWS Cloud9 console at https://console.aws.amazon.com/cloud9/.

3.2\. Click on **Create environment**.

![Cloud9 Create environment](images/cloud9-create.png)

3.3\. For the **Name** type `amplify-workshop`, and choose **Next step**.

![Cloud9 name environment](images/cloud9-name.png)

3.4\. For the **Configure settings** section, select the instance type **t2.small** and choose **Next step**.

![Cloud9 Settings](images/cloud9-settings.png)

3.5\. For the **Review** section click on **Create environment**.

3.6\. Wait a few seconds until your development environment is ready, you will see the following screen.

![Cloud9 Env](images/cloud9-env.png)

3.7\. For this lab is required to see hidden files, click on preference icon and click on **Show Hidden Files**.

![Show Hidden Files](images/cloud9-show-hidden-files.png)

## 4. Configure your AWS CLI with your IAM credentials

4.1\. Inside the Cloud9 environment, click on **AWS Cloud9** and **Preferences**.

![Cloud9 Preferences](images/cloud9-preferences.png)

4.2\. Select **AWS SETTINGS** and turn off **AWS managed temporary credentials**.

![AWS SETTINGS](images/cloud9-aws-settings.png)

4.3\. In the **bash** terminal we are going to configure the AWS CLI as follows:

``` bash
aws configure
```

- Configuration:
    - AWS Access Key ID: **(Type your Access key ID)**
    - AWS Secret Access Key: **(Type your Secret access key)**
    - Default region name [None]: **(Use your region code, example: us-east-1)** [All Regions](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-regions-availability-zones.html#concepts-available-regions)
    - Default output format [None]: **json**

![AWS Configure](images/cloud9-aws-configure.png)

4.4\. Remove **aws_session_token** variable from aws credentials.

``` bash
sed -i 's/aws_session_token =//g' ~/.aws/credentials
```

## 5. Configure and run the base React application

5.1\. Inside your **environment** folder clone the repository project from GitHub.

``` bash
cd ~/environment/
git clone --single-branch --branch start https://github.com/aurbac/react-my-todos.git
cd react-my-todos
git branch master
git checkout master
```

![Cloud9 git](images/cloud9-git.png)

5.2\. Install the Node.js dependencies.

``` bash
npm install
```

5.3\. Run the project.

``` bash
npm start
```

![Run project](images/cloud9-run-project.png)

5.4\. Once the web server has started, click the **Preview** menu and select **Preview Running Application**.

![Cloud9 preview](images/cloud9-preview.png)

5.5\. If you’d like, you can also pop the preview to a new window.

![Cloud9 pop](images/cloud9-pop.png)

5.6\. Finally, open another terminal window. We’ll leave this first terminal alone since it’s running the web server process.

![Cloud9 new terminal](images/cloud9-new-terminal.png)
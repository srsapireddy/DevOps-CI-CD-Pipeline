# DevOps-CI-CD-Pipeline

Exactly! Continuous Integration (CI) and Continuous Deployment (CD) are crucial practices in modern software development. Let's break down the key concepts: </br>

1. **Continuous Integration (CI):** It involves automatically integrating code changes from multiple contributors into a shared repository multiple times a day. The primary goal is to detect and address integration issues early in the development process. CI ensures that the codebase is always in a consistent and working state. </br>

2. **Continuous Deployment (CD):** This extends the CI process to automatically deploy code changes to production or staging environments after passing through the CI pipeline. Continuous Deployment helps in delivering new features or bug fixes to end-users more rapidly and consistently. </br>

A CI/CD pipeline typically includes the following stages:

- **Code Commit:** Developers push their code changes to a version control system (e.g., Git). </br>

- **Build:** The CI server automatically builds the application based on the latest code changes, ensuring that the code can be compiled successfully. </br>

- **Automated Testing:** The CI/CD pipeline runs automated tests (unit tests, integration tests, etc.) to verify that the code changes haven't introduced new bugs and that the application functions as expected. </br>

- **Artifact Generation:** The pipeline generates deployable artifacts, such as compiled binaries or packages, based on the successfully built and tested code. </br>

- **Deployment:** In the CD phase, the pipeline deploys the artifacts to a staging or production environment. This could involve activities like provisioning servers, configuring databases, and deploying the application. </br>

- **Monitoring and Logging:** Continuous monitoring and logging help detect and address issues in the deployed application. It ensures that the application remains healthy and performs well in production.

The CI/CD pipeline facilitates a more efficient and reliable software development process by automating repetitive tasks, reducing manual errors, and enabling rapid and reliable delivery of software updates. It is a fundamental aspect of DevOps, promoting collaboration between development and operations teams to achieve faster and more reliable software delivery. </br>

## Use Case</br>
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/eb34157e-6ad7-47ab-bb9c-804a751155d4)

## Amazon S3 introduction</br>
### To create an Amazon S3 bucket:

#### Sign in to the AWS Management Console and open the Amazon S3 console at https://console.aws.amazon.com/s3/
* Choose Create bucket
* Enter the Bucket name
* Choose the Region where you want to create the bucket
* In the Block Public Access settings for the bucket section, uncheck the box for Block all public access
* Accept the remainder default settings and create the bucket, choose Create

#### Enable website hosting for your S3 bucket:
* Click on your newly created bucket and then click the Properties tab
* Scroll to the bottom and choose edit on the Static website hosting section
* Select Enable: Static website hosting
* Fill in the index.html and error.html fields
* Accept the remainder of default settings and choose Save changes****

### Bucket Creation
* Use a bucket policy that grants public read access:

* Click the Permissions tab for your S3 bucket
Under Bucket Policy, Click Policy Generator and find the Action for GetObject, and Click Generate Policy and the following code will be generated:

![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/a089be21-6275-47cf-a31d-31ae555d861a)
Editing Bucket Policy
```
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Sid": "PublicRead",
			"Effect": "Allow",
			"Principal": "*",
			"Action": "s3:GetObject",
			"Resource": "arn:aws:s3:::mlops-now/*"
		}
	]
}
```

* Click the Permissions tab again and erase the current policy and replace it with the code from above. *Note: if you’re following along with this project, replace the ARN with the name of your bucket. Do not forget to add the /* after your bucket name!
* Click Save changesClick the Permissions tab again and erase the current policy and replace it with the code from above. *Note: if you’re following along with this project, replace the ARN with the name of your bucket. Do not forget to add the /* after your bucket name!
* Click Save changes

### Enable Static website hosting for S3 
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/77dc124f-a55f-4512-902d-c8ec09bb4343)
You’ll see that the bucket is now publicly accessible/has public access. We can move on to setting up our pipeline! </br>

## Amazon S3 for Machine Learning 
### Creating CodePipeline (Initial Version)
* Navigate to CodePipeline in the AWS console
* Click Create pipeline, type the name of your new pipeline, and click Next

![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/00bfd8ff-fbc3-4b0c-a3fc-3ab999270c22)

## Create a connection to GitHub:

* Sign in to the AWS Management Console, and open the Developer Tools console at 
 </br> https://console.aws.amazon.com/codesuite/settings/connections.
* To create a connection to a GitHub, under Select a provider, choose GitHub
* Under GitHub connection settings, your connection name appears in the Connection name. Choose Connect to GitHub. The access request page appears as the following:

![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/e9137910-2385-49d4-88de-e5744a03b5a3)

#### Once you have authorized GitHub — navigate back to CodePipeline, and input the following:

* Under Source provider, select GitHub (Version 2)
* Select your existing GitHub connection in the dropdown menu
* Select the Repository name in your GitHub account
* Select the Branch name
* Click Next.
* Select AWS CodeBuild as the build provider.
* Click Create Project. *As instructed from AWS: Create a build project in the AWS CodeBuild console and then return to this task.
Once you click Create Project, a CodeBuild window will launch.

## Use AWS CodeBuild for the build stage:
### We will use the following configurations in CodeBuild:

* Environment Image: Managed Image
*  Operating System: Amazon Linux
* Runtime: Standard
* Image: aws/codebuild/standard:4.0
* Image Version: Always use the latest image for this runtime version
* Environment Type: Linux
* Service Role: Create a New service role

* Click Continue to Pipeline
* Navigate back to CodePipeline in the AWS console
  
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/f88b5ae9-293f-4f0d-a80e-56f3525561a3)

## Deploy Pipeline stage:
* For the deploy stage, select your S3 bucket as shown in the following image:
* Click Next to review your pipeline, and lastly, click Create pipeline. This step will take a few minutes, be patient!!

### Pipeline Running in Console
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/63b9f1b4-a527-4440-bc28-1bd999e5fa62)

### Checking for S3 Buckets Created
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/49c24f1c-9084-4751-a842-2bbf5fd80a96)
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/d66284d7-32cc-4750-a422-5d746dc2aba1)

### Check for the End Point
```
[http://mlops-now.s3-website-us-east-1.amazonaws.com](http://mlops-now.s3-website-us-east-1.amazonaws.com/prod)
```

### Final Application of DevOps Pipeline
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/0f21c1b4-a678-42e2-ab36-0b4d3c34178a)

Source: WHERE WE ARE FETCHING OUR CODE
BUILDING OUR ARTIFACT
AND DEPLOYING OUT WEBAPP

### Making changes in GitHub code to check pipeline process
#### Commit Changes
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/0909def0-3fca-4268-bbb4-d35ecda93a3a)
#### Pipeline will trigger from start build process
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/3331a5a7-859a-4f4b-95a1-f00dca34c183)

#### Updated WebApp Page
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/a49f6ad6-9dda-40fc-b018-a6969899ac6b)

### Making changes to Pipeline
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/e83fc634-7d5d-4f4b-9e88-5e444339742d)
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/25f8d62e-ceba-45e4-ab7b-dbd9c12f8ccf)

Make changes in GitHub again. </br>
After a few seconds, the pipeline will start executing. </br>
It shows that dev-approval is in progress. </br>
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/44e85980-abf8-4987-a53a-b3dd2e983f5d)

Approving Review for Dev
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/8287b92d-43b0-4b1a-bb17-19ad5c70411a)
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/aecd22e2-048c-4fde-805a-6cb3bd13c568)

### S3 Bucket 
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/b76d6d03-4642-4094-92b7-e09975a893a2)

### Dev-Deploy WebApp
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/aa953c0c-4c4d-44e6-b341-d707105be646)

However, the production server will be serving the old app. After we approve the prod to be deployed, we get the updated prod web app server with new features.
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/61a6ad6d-8962-4389-b91e-34e0749824d3)

### Prod-Deploy WebApp
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/595a72bb-fe7f-4d74-a644-7f7d3e3101cb)

### Checking GitHub Commits
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/f5b36b73-1578-4b55-b77b-09cebdf75b91)
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/7160ab32-ecc9-42db-83a6-0b778375b499)

### Reference Code: https://github.com/srsapireddy/mlops-nov

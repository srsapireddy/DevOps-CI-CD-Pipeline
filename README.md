# DevOps-CI-CD-Pipeline


## Use Case</br>
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/eb34157e-6ad7-47ab-bb9c-804a751155d4)


## Getting started with AWS for Machine Learning
## AWS Machine Learning & AI Platforms Introduction</br>
## Amazon S3 introduction</br>
### Bucket Creation
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
Enable Static website hosting for S3 </br>]
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/77dc124f-a55f-4512-902d-c8ec09bb4343)
Enabling the bucket to be Public. </br>

## Amazon S3 for Machine Learning 
### Creating CodePipeline (Initial Version)
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/00bfd8ff-fbc3-4b0c-a3fc-3ab999270c22)
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/e9137910-2385-49d4-88de-e5744a03b5a3)
![image](https://github.com/srsapireddy/AWS-Machine-Learning-Operations-MLOps/assets/32967087/f88b5ae9-293f-4f0d-a80e-56f3525561a3)

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

## Reference Code: https://github.com/srsapireddy/mlops-nov

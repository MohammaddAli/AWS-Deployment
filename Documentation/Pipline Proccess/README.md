## I used Udagram project to be deployed
> - I haven't hard-coded any environment variables but i added them to CircleCI and passed them through the code to the deployment environment using the following command in the deploy.sh file :                     `eb setenv POSTGRES_USERNAME=$POSTGRES_USERNAME POSTGRES_DB=$POSTGRES_DB POSTGRES_PASSWORD=$POSTGRES_PASSWORD PORT=$PORT POSTGRES_HOST=$POSTGRES_HOST JWT_SECRET=$JWT_SECRET`
AWS_ACCESS_KEY_ID	AWS_DEFAULT_REGION	AWS_SECRET_ACCESS_KEY	PORT	POSTGRES_DB	POSTGRES_HOST	POSTGRES_PASSWORD	POSTGRES_USERNAME	URL
> - The configuration files are updated to set the environment variables to the project code , for example , setting the server port and the server url and the database port the database url ,user and password. it's in udagram-api/scr/config/config.ts.
> - I added all the scripts inside the package.json file. i added the scripts for installation , building, testing and deployment for both the frontend and the backend to automate all the steps.
> - i added the screenshots for all the aws resources and environments.
> i linked the project in github to circleci and added the config.yml file in the circleci containing all the orbs and jobs for runnung the scripts automatically.
> - for accessing the application please visit `http://udagram-frontend1.s3-website-us-east-1.amazonaws.com/` but please make sure you are using a browser that **doesn't enforce CORS policy** or blocking the user of the EB aws URL by the S3 URL ....................
> - for accessing my GitHub repository which is linked to circleci , please visit : `https://github.com/MohammaddAli/AWS-Deployment` 


## Pipline proccess inside circleci. 
## Continuous Integration :
> - First i added all the commands needed for the installing , building and testing the application in the as scripts in package.json files in the frontend and the backend then called these scripts inside the package.json file in the root of application folder.
>  - i added the  jobs inside the CircleCi config.yml file for installing all the dependencies on both the frontend and  backend of the application using the `npm install` command inside package.json files.
> - then i added the jobs for building the frontend and the backend by calling the corresponding scripts and run it using `npm run`.

## Continuous Deployment : 
> - First i added all the commands needed for deploying the application in the as scripts in package.json files in the frontend and the backend then called these scripts inside the package.json file in the root of application folder.
>  - i added the the Elastic Beanstalk and aws in the CircleCi orbs for setting them up and installing them for the deployment.
>  - i added the jobs inside the CircleCi config.yml file for deploying both the frontend and backend just by calling the deploy script added to the main package.json file wich correspondingly calls the deploy command added to the backage.json file of both the frontend and the backend.
> - > i linked my github application to circleci and specified the branch of interest which is the main branch to circleci is only trigged if the code pushed to the main branch.
> `https://app.circleci.com/pipelines/github/MohammaddAli/AWS-Deployment`


## All the screenshots for the EB and the S3 and the DB and CircleCi are added to the zip file and to the corresponding directories.
## I also added the architicture diagram inside the infrastructure folder and the pipline diagram inside the pipline procces folder, showing all the relationships and the communication between the different services.
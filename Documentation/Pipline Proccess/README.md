## I used Udagram project to be deployed
> - I haven't hard-coded any environment variables and No environment variables that change from the development environment but i added them to CircleCI and passed them through the code to the AWS deployment servises environment using the following command in the deploy.sh file : `eb setenv AWS_ACCESS_KEY_ID=$AWS_ACCESS_KEY_ID AWS_DEFAULT_REGION=$AWS_DEFAULT_REGION AWS_SECRET_ACCESS_KEY=$AWS_SECRET_ACCESS_KEY PORT=$PORT POSTGRES_DB=$POSTGRES_DB POSTGRES_HOST=$POSTGRES_HOST POSTGRES_PASSWORD=$POSTGRES_PASSWORD POSTGRES_USERNAME=$POSTGRES_USERNAME URL=$URL JWT_SECRET=$JWT_SECRET`
> - The configuration files are updated to set the environment variables to the project code in the central configuration file is used make the environment variables available to the code. it's in udagram-api/scr/config/config.ts.
> - I added all the scripts inside the package.json file. i added the scripts for for running: installation , building, testing and deployment for both the frontend and the api to automate all the steps and a project-level package.json file in the project root folder. 
Any new dependencies is located in the devDependencies section of the package.json.
> - i added the screenshots for all the aws resources and environments and a screenshot of the last build shows that my CircleCi account is authorized to access my repo on Github and is detecting changes each time i am adding , committing and pushing to the main branch.
> i linked the project in github to circleci and added the config.yml file in the circleci containing all the orbs and jobs for runnung the environments configurations and packages.
> - All the secrets found in the application are configured inside CircleCi and passed to the production application, A screenshot of the configuration screen is present to show where secrets were added.
> - for accessing the application please use this URL `http://udagram-frontend1.s3-website-us-east-1.amazonaws.com/`.
 

## Pipline proccess inside circleci. 
## Continuous Integration :
> - First i added all the commands needed for the installing , building and testing the application as scripts in package.json files in the frontend and the backend then called these scripts inside the package.json file in the root of application folder.
>  - i added in the job inside the CircleCi config.yml file for installing Node and the frontend and api dependencies on both the frontend and backend of the application using the `npm install` command inside package.json files.
> - then i added building commands for the frontend and the api by calling the corresponding scripts and run it using `npm run`.

## Continuous Deployment : 
> - First i added all the commands needed for deploying the application as scripts in package.json files in the udagram-frontend folder and the udagram-api then called these scripts inside the package.json file in the root of application folder.
>  - i added the the Elastic Beanstalk , aws and node in the CircleCi orbs for installing them for the deployment.
>  - i added the jobs inside the CircleCi config.yml file for deploying the frontend and backend just by calling the deploy script added to the main package.json file in the root directory wich correspondingly calls the deploy command added to the backage.json file of both the udagram-frontend file and the udagram-api file.
> - i linked my github application to circleci and specified the branch of interest which is the main branch here to circleci is trigged everytime the code pushed to the main branch.
> `https://app.circleci.com/pipelines/github/MohammaddAli/AWS-Deployment`


### All the screenshots for the EB (API) and the S3 (Front-End) and the RDS (DB) and CircleCi (CI/CD Pipline) are added to the zip file and to the corresponding directories.
### I also added the architicture diagram inside the infrastructure folder and the CircleCI Pipline diagram inside the pipline procces folder, showing all the relationships and the communication between the different services.
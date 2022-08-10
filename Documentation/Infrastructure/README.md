## About the Application:
> - First i added all the commands needed for the installing , building and testing the application in the as scripts in package.json files in the frontend and the backend then called these scripts inside the package.json file in the root of application folder.
>  - i added the  jobs inside the CircleCi config.yml file for installing all the dependencies on both the frontend and  backend of the application using the `npm install` command inside package.json files.
> - then i added the jobs for building the frontend and the backend by calling the corresponding scripts and run it using `npm run`.

## About AWS deployment:
> - RDS Postgres database instance that has the database structure with all the data content and is linked to the backend code (inside Elastic Beanstalk)
> - Elastic Beanstalk that handles the application environment and sends requests to RDS database and reseives the response to be sent to the front end inside the S3 Bucket to display the relevant web pages to the user.
> - S3 that holds the frontend files wich also sends the requests to the backend to be handled and renders the HTML pages returned as a response to be displayed to the user.
> - I created IAM user that has associated credentials and permissions to be able to access and  use AWS CLI and EB CLI. 

### The architecture diagram is added showing the communication between these different services and infrastructure
### The screenshots of the instances created in the AWS services are added to the infrastructure directory as well.
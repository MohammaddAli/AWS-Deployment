## About AWS deployment:
> - RDS : instantiate a Postgres database instance called "database-1" that has the database schema with all the data content and is linked to the backend code (inside Elastic Beanstalk) using the instance Endpoint (`database-1.cakjcae0jq7l.us-east-1.rds.amazonaws.com`) and the other Configurations in the .env file.
> - Elastic Beanstalk: an environment that i uploaded the application api on and handles the application environment and sends requests to RDS database and reseives the response to be sent to the front end inside the S3 Bucket to display the relevant HTML web page to the user, and irt's Health has to be "OK".
> - S3 : the bucket name in my application is "udagram-frontend1" that holds the frontend files and objects wich also sends the user requests to the backend through the EB URL to be handled and renders the HTML web page returned as a response to be displayed to the user through this URL `http://udagram-frontend1.s3-website-us-east-1.amazonaws.com `.
> - I created IAM user that has associated credentials and permissions to be able to access and  use AWS CLI and EB CLI. 

### The architecture diagram is added showing a simple diagram giving a high-level overview of the infrastructure representating the communication between these different services.
### The screenshots of the AWS console of the instances created in the AWS services are added to the infrastructure directory as well showing that thes servises are properly set up, i.e. healthy and accessible, The app is accessible via the link provided (s3 Link).



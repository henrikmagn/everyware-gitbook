# Deployment

Deployments are normally done with Jenkins \([https://jenkins.io/](https://jenkins.io/)\), there is different jobs for test, stage and production environments. The Jenkins job will run composer, npm, gulp and any other project dependencies, it will also upload static resources to an S3 bucket.

When the static upload is finished the code will be zipped in to a file that will be deployed to the Elastic Beanstallk environment.


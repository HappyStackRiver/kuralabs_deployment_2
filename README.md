# Deployment 2
## The Process
1. First we created an IAM User under Jenkins to enable AWSEB web services.
2. Second, on our server with our jenkins service, make sure all dependencies are installed to run AWS Cli and AWS EB Cli
3. Initialize the EB client with proper settings and create the cloudformation
4. Deploy onto environment using Jenkins
## Issues
In the documentation, there were some shortcomings in the steps like having to call eb --version despite our jenkins created user not having their own .bashrc file or a profile file of some sort to keep track of installed paths. There were a few ways to solve this problem. You could create a profile file that sourced the path of the installed eb client, or you could switch into the ec2 root user and install EB, therefore giving all users access to EB commands. Either one works.
## What's next?
This deployment was a process of building the pipeline in Jenkins, and deploying it into an environment for either staging or production. I was able to install an alarm in the environment to alert after a certain threshold was met for the resources, because EB installs a cloudwatch agent. I would like to build my own tests, and perhaps add a linter successfully to ensure that the code is functional and passes any unit test thrown at it before implementing intergration tests. 

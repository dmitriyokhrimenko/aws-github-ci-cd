# Users and roles

## AWS access user from GitHub Action

### Add User "project-deployer" (AWS console)
```bash
$ Set checkbox programmatic access
$ Attach existing policies directly (AmazonS3FullAccess и AWSCodeDeployDeployerAccess) in Permissions section
```

## AWS EC2 instances service role

### AWS IAM
```bash
$ Role -> Add role
$ AWS Service -> EC2
$ Add policy AmazonEC2RoleforAWSCodeDeploy
$ Role name ProjectXCodeDeployInstanceRole
```

### AWS CodeDeploy service role

```bash
 $ Role -> Add Role
 $ AWS Service -> CodeDeploy
 $ AWSCodeDeployRole politic (will be add automatically)
 $ Role name ProjectXCodeDeploy
 ```

## AWS EC2 instance

```bash
 $ Attach ProjectXCodeDeployInstanceRole (what we created abowe)
 $ Install CodeDeploy agent for instance (https://docs.aws.amazon.com/codedeploy/latest/userguide/codedeploy-agent-operations-install-ubuntu.html)
 $ sudo service codedeploy-agent restart (if codedeploy agent was installed before attaching ProjectXCodeDeployInstanceRole)
 ```
## AWS CodeDeploy configuration
```bash
$ Go to AWS CodeDeploy console
$ Go to Deploy -> Applications -> Create application
$ App name projectx
$ Compute platform EC2/On-Premises
$ Create deployment group (develop)
$ Attach role ProjectXCodeDeploy (what we created abowe)
$ Deployment type In place
$ In Environment configuration select Amazon EC2 Instances (find by tag, etc.)
````

## AWS S3 bucket
```bash
$ Go to AWS S3
$ Create bucket (projectx-codedeploy-deployments), set checkbox Block all public access
```

# Users and roles

## AWS access user from GitHub Action

### Add User project-deployer (AWS console)
```bash
Set checkbox programmatic access
```

### Attach existing policies directly (AmazonS3FullAccess и AWSCodeDeployDeployerAccess) in Permissions section

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
 

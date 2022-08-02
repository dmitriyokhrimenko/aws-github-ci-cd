# Users and roles

## AWS access user from GitHub Action

### Add User project-deployer
```bash
Set checkbox programmatic access
```

### Attach existing policies directly (AmazonS3FullAccess и AWSCodeDeployDeployerAccess) in Permissions section

## AWS EC2 instances service role

### AWS IAM
```bash
$ Role -> Add role
$ AWS Service -> EC2
$ Add policy **AmazonEC2RoleforAWSCodeDeploy**
$ Role name **ProjectXCodeDeployInstanceRole**
```

### Add user to group 

```bash
 $ sudo usermod -a -G groupName userName / adduser username groupName 
 ```

### Check which group a certain user belongs to

```bash
 $ groups [username]
 ```

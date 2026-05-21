# AWS CLI on the raspberry pi

Playing with the raspberry pi is fun. So I decided to use it for all my AWS development.

**Install python3 Pip3**

```
1. sudo apt-get install python3-pip
```

### nstall the AWS CLI

```
2. pip3 install awscli --upgrade --user
```

### Add AWS CLI executable to your Command Line Path

```
3. edit ~/.bashrc and add the following at the end of the file:

   export PATH=/home/pi/.local/bin:\$PATH

4. from the command line type source ~/.bashrc
```

### Confirm that the installation is successful

```
5. aws --version
```

## Configure the AWS CLI

### Configure the default AWS CLI

From the command line type the followings (assuming you have the following information):

```
6. aws configure
```

### (Recommended) Configure with multiple profiles

```
aws configure --profile myuser
```

## Testing time using the CLI

From the command line Type

```
aws s3 ls

  - This will use the “default” profile with no user specified

aws s3 ls --profile myuser

  - you can also use this to specify the “myuser” profile to run

aws ec2 describe-instances
```

### Things you should know

The AWS CLI configuration files are located here

```
  ~/.aws/credentials #User credentials
  ~/.aws/config #Profile settings
```

## Reference

```
sudo apt-get install awscli
```

## EC2 User Data Script Explanation

When launching an EC2 instance, the user data script can be passed in as part of the launch configuration. The script is typically passed in as plain text or as base64-encoded data. When the instance starts up, the script is executed automatically, usually as the root user.

The user data script can be used to automate many different tasks that are required to configure an EC2 instance, such as setting up a web server, installing monitoring tools, or configuring network settings. The script can be written in any language that is supported by the instance's operating system.

Overall, the user data script is a powerful tool for automating the initial configuration of EC2 instances, which can save time and reduce the risk of errors when launching new instances.

This [example](./userData.sh) of an EC2 user data script performs the following actions:

1. Updates the system software to the latest available version using the `yum update -y` command. The `-y` option automatically answers yes to prompts.

2. Installs the Apache web server using the `yum install -y httpd` command. The `-y` option again automatically answers yes to prompts.

3. Starts the Apache web server using the `systemctl start httpd` command.

4. Enables the Apache web server to start at boot time using the `systemctl enable httpd` command.

5. Creates a default index page for the Apache web server with the text `<h1>Hello world from $(hostname -f)</h1>` in the file `/var/www/html/index.html`. `$(hostname -f)` will be replaced with the fully-qualified domain name of the EC2 instance when the script is run.

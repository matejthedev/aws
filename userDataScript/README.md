## EC2 User Data Script Explanation

This EC2 user data script performs the following actions:

1. Updates the system software to the latest available version using the `yum update -y` command. The `-y` option automatically answers yes to prompts.

2. Installs the Apache web server using the `yum install -y httpd` command. The `-y` option again automatically answers yes to prompts.

3. Starts the Apache web server using the `systemctl start httpd` command.

4. Enables the Apache web server to start at boot time using the `systemctl enable httpd` command.

5. Creates a default index page for the Apache web server with the text `<h1>Hello world from $(hostname -f)</h1>` in the file `/var/www/html/index.html`. `$(hostname -f)` will be replaced with the fully-qualified domain name of the EC2 instance when the script is run.

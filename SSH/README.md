# How to SSH into an EC2 (using Mac or Linux)

## To SSH into an EC2 instance on AWS from a Mac, follow these steps:

1. Open the Terminal app on your Mac.
Locate the private key file (.pem) you downloaded when you launched your EC2 instance.

2. In the Terminal, change the permissions of the private key file by running the following command: 
`chmod 400 /path/to/your/key.pem`

3. Connect to your EC2 instance using SSH by running the following command: 
`ssh -i /path/to/your/key.pem ec2-user@public-dns-name-of-instance`

Replace "/path/to/your/key.pem" with the actual path to your private key file.
Replace "ec2-user" with the appropriate user name for your instance (e.g. ubuntu for Ubuntu instances).
Replace "public-dns-name-of-instance" with the public DNS name of your EC2 instance, which you can find in the AWS Management Console.

4. If prompted, type "yes" to confirm that you want to connect to the instance.

Once connected, you can interact with your EC2 instance through the Terminal as if you were logged in to a remote server.
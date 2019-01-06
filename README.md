To connect to your EC2 instance and install the Apache web server with PHP

[1] To connect to the EC2 instance that you created earlier, follow the steps in Connect to Your Instance.

[2] To get the latest bug fixes and security updates, update the software on your EC2 instance by using the following command:

Note

The -y option installs the updates without asking for confirmation. To examine updates before installing, omit this option.

[ec2-user ~]$ sudo yum update -y

[3] [ec2-user ~]$ sudo yum install -y httpd24 php56 php56-mysqlnd

[4] Start the web server with the command shown following.

[ec2-user ~]$ sudo service httpd start
                
You can test that your web server is properly installed and started by entering the public DNS name of your EC2 instance in the address bar of a web browser, for example: http://ec2-42-8-168-21.us-west-1.compute.amazonaws.com. If your web server is running, then you see the Apache test page. If you don't see the Apache test page, then verify that your inbound rules for the VPC security group that you created in Tutorial: Create an Amazon VPC for Use with an Amazon RDS DB Instance include a rule allowing HTTP (port 80) access for the IP address you use to connect to the web server.

Note

The Apache test page appears only when there is no content in the document root directory, /var/www/html. After you add content to the document root directory, your content appears at the public DNS address of your EC2 instance instead of the Apache test page.

[5] [ec2-user ~]$ sudo chkconfig httpd on


link:       (https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Tutorials.WebServerDB.CreateWebServer.html)

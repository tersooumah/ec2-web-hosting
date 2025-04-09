# ec2-web-hosting
## Create an EC2 Instance

Sign in to AWS Management Console and search for EC2
![Artboard 2](https://github.com/user-attachments/assets/125ae40f-a85d-4e44-b560-87fadc11a1c1)


Click on 'Instances' on the left pane and click 'Launch Instances'
![Artboard 3](https://github.com/user-attachments/assets/bcfa4e29-d4b7-4feb-bc81-12e1e176733b)



Choose a name for your instance, select 'Amazon Linux' for 'Application and OS Images', and maintain the settings for AMI (free tier eligible), Architecture (64-bit (x86)), and instance type (free tier eligible).
![Artboard 4](https://github.com/user-attachments/assets/bf7d8d68-06b8-4cb3-87fd-10a30ec672b9)
![Artboard 5](https://github.com/user-attachments/assets/76cc0340-dba6-4bb2-a72f-7cb30ead3ce9)


Create key pair (the key pair file will be automatically downloaded once created)
![Artboard 6](https://github.com/user-attachments/assets/9a197b4f-458b-4dbb-86c3-8e5d924c8371)
![Artboard 7](https://github.com/user-attachments/assets/96665a84-7476-496b-84f3-af2511f0c4f2)



Configure security group to allow SSH, HTTP, and HTTPS traffic and click launch instance
![Artboard 9](https://github.com/user-attachments/assets/d7793398-f226-430a-92fd-7de50b10b3be)


Head back to Instances dashboard and Refresh Instances, and wait for a few minutes for the status to update, then highlight the newly created instance and click "connect"
![Artboard 10](https://github.com/user-attachments/assets/cbb6e820-bae8-4552-af1f-53efc0b7b982)
![Artboard 11](https://github.com/user-attachments/assets/9a8599ec-572d-4e45-b460-bb7b366f8bae)



Click on the SSH client tab and see the instructions on connecting to the instance via Unix/Linux using SSH. (Copy the ssh command and keep it aside)
![Artboard 12](https://github.com/user-attachments/assets/20a9112d-eee2-4161-9025-36ef465f483d)



## Install and Configure a Web Server

Head to your Linux terminal, switch to root user (sudo su-), and open the folder where the Key pair file is located (cd Downloads)
![Artboard 13](https://github.com/user-attachments/assets/d25bf9bf-1819-453c-9c94-445be99300fa)


Run the saved command: ssh -i 'css-test-key.pem' ec2-user@ec2-52-91-87-15.compute-1.amazonaws.com from the "Connect to instance" page and select yes to continue
![Artboard 14](https://github.com/user-attachments/assets/ed71feb9-0b2b-4b8e-a552-97a5400855e6)


Become root user (sudo su-) and update the system with 'yum update -y' command
![Artboard 15](https://github.com/user-attachments/assets/e2772fb5-3c33-491e-ad41-995c61edfa07)


Install the web server with 'yum install -y httpd' command
![Artboard 16](https://github.com/user-attachments/assets/1a7b18ea-ce0b-4029-be35-801f42d97f48)


Create a new 'temp' directory (mkdir temp) and the open that directory (cd temp)
![Artboard 17](https://github.com/user-attachments/assets/fbb492bd-fe3f-4540-815f-779edbbc2d9a)


Head to free-css.com and copy the link address of your desired css template
![Artboard 18](https://github.com/user-attachments/assets/09ca45c2-ad4b-4ce6-9c60-5dcc2767245f)


Download the file on the terminal using the wget command 'wget' command
![Artboard 19](https://github.com/user-attachments/assets/76ffa909-a5bc-409d-b391-506aff7b2f3e)


Unzip the file (unzip oxer.zip) and open the folder from the unzipped file
![Artboard 20](https://github.com/user-attachments/assets/d45cf483-942a-44ac-9f8f-458f884d2438)
![Artboard 21](https://github.com/user-attachments/assets/d2b00746-e62a-44f0-8028-2f8f24f84af0)

Move the content of the folder to this directory /var/www/html/
![xxxxx](https://github.com/user-attachments/assets/3e2078da-4267-47f1-ba66-d56f85c61a51)

To activate the html server use the 'systemctl enable httpd' command and then use 'systemctl start httpd' command to start the service
![Artboard 22](https://github.com/user-attachments/assets/af6c10a5-e814-4969-9d3e-f68882b7dc1d)


Go to Instance page and copy the public ipv4 address, and paste it on your search engine
![Artboard 23](https://github.com/user-attachments/assets/ec2ee031-0069-4f24-ac3b-72f37674d3ca)
![Artboard 24](https://github.com/user-attachments/assets/81c41494-a03a-4f7d-af38-4038fb7f13a5)










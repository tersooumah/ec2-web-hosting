# ec2-web-hosting
## Create an EC2 Instance

Sign in to AWS Management Console and search for EC2
![1](https://github.com/user-attachments/assets/ce5faf61-cf27-4976-82dc-81c0850055d0)


Click on 'Instances' on the left pane and click 'Launch Instances'
![2](https://github.com/user-attachments/assets/d94cb69d-5f69-4e3a-b0aa-961718cd30ba)


Choose a name for your instance, select 'Amazon Linux' for 'Application and OS Images' and maintain the settings for AMI (free tier eligible), Architecture (64-bit (x86)) and instance type (free tier eligible).
![3](https://github.com/user-attachments/assets/d530ee77-89be-4cb2-a530-523aca01d05d)
![4](https://github.com/user-attachments/assets/e8fddaad-9657-49c8-9b84-d15422c03895)


Create key pair (the key pair file will be automatically downloaded once created)
![5](https://github.com/user-attachments/assets/29374652-3998-4e6a-ab85-aa3d39ea0619)
![6](https://github.com/user-attachments/assets/fe3946ed-385a-4e17-a352-23ecff05c281)


Configure security group to allow SSH, HTTP and HTTPS traffic and click launch instance
![7](https://github.com/user-attachments/assets/8db2f5d0-e2d4-47fe-aa8f-ac9b269fb2b5)
![8](https://github.com/user-attachments/assets/1cc2eca8-56c7-408a-ba4d-e3956d591f12)


Head back to Instances dashboard and Refresh Instances, and wait for a few minutes for the status to update, then highlight the newly created instance and "connect"
![10](https://github.com/user-attachments/assets/1fe6c348-7742-4b9c-96eb-cec2126f9fd8)

Click on SSH client and see the instructions on how to connect to the service via unix/Linux using ssh.
![11](https://github.com/user-attachments/assets/fdd70bfc-3f66-4aad-ab02-e03fb98c7329)


## Install and Configure a Web Server

Head to you Linux terminal and switch to root user (sudo su-) and open the folder the folder where the Key pair file is located (cd Downloads)
![Screenshot from 2025-04-01 21-06-00](https://github.com/user-attachments/assets/1e6cdeed-29c4-4cf7-b518-e1b741003de7)

Run the command: ssh -i 'css-test-key.pem' ec2-user@ec2-52-91-87-15.compute-1.amazonaws.com from the "Connect to instance" page and select yes to continue
![Screenshot from 2025-04-01 21-10-39](https://github.com/user-attachments/assets/931cb089-1e7a-48a9-844b-8aa3d5f97930)

Become root user (sudo su-) and update the system with 'yum update -y' command
![Screenshot from 2025-04-01 21-13-53](https://github.com/user-attachments/assets/c80edb86-3ec0-40de-8237-affc1007db6e)

Install the web server with 'yum install -y httpd' command
![Screenshot from 2025-04-01 11-41-21](https://github.com/user-attachments/assets/2315361d-e9a0-4559-850a-d18b0f204c85)
![Screenshot from 2025-04-01 21-15-27](https://github.com/user-attachments/assets/5c3782d1-447c-4fff-933b-f3b6213048e3)

Create a new 'temp' directory (mkdir temp) and the open that directory (cd temp)
![Screenshot from 2025-04-01 21-32-55](https://github.com/user-attachments/assets/bbbbd72a-8ff1-4523-be3f-4cabd1a6e659)

Head to free-css.com and copy the link address of your desired css template
![Screenshot 2025-04-01 213339](https://github.com/user-attachments/assets/43734e88-f69d-482d-b0be-d693735a993b)

Download the file on the terminal using the wget command 'wget' command
![Screenshot from 2025-04-01 21-34-52](https://github.com/user-attachments/assets/1cd4c0c1-ef2e-4065-92e8-9166d1ad4bee)

Unzip the file (unzip oxer.zip) and open the folder from the unzipped file
![Screenshot from 2025-04-01 21-36-08](https://github.com/user-attachments/assets/68224bbe-4aff-46c2-b208-1089e9f9f695)
![Screenshot from 2025-04-01 21-37-12](https://github.com/user-attachments/assets/9ccfd9ab-ff87-46cb-875f-2b7d1630b146)
![Screenshot from 2025-04-01 21-37-44](https://github.com/user-attachments/assets/244eab0b-323c-4533-984f-0c1d645f10d2)

To activate html server use the 'systemctl status httpd' command and then use 'systemctl start httpd' command to start the service
![Screenshot from 2025-04-01 21-41-46](https://github.com/user-attachments/assets/eb81eb1d-0fcd-4f9c-8bcb-0ca06f249171)

Go to instance page and copy the public ipv4 address past it on your search engine
![Screenshot 2025-04-01 214509](https://github.com/user-attachments/assets/4da7d008-a341-4c36-89eb-1507a52d4658)
![Screenshot 2025-04-01 214658](https://github.com/user-attachments/assets/940d96b3-6468-45d3-91fe-28895d77bb07)








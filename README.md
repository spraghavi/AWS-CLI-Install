I installed and configured the AWS CLI on a Red Hat Linux instance because this instance type does not have the AWS CLI pre-installed. Some instance types, such as Amazon Linux, do come pre-installed with the AWS CLI. 
I established a Secure Shell (SSH) connection to the instance. You configure the installation with an access key that can connect to an AWS account. Finally, using the AWS CLI to interact with AWS Identity and Access Management (IAM).

![image](https://github.com/spraghavi/AWS-CLI-Install/assets/117675078/c047cc3a-c171-4e66-a7e8-0afdcc7f9d8f)

In the preceding diagram, you can access the AWS Cloud through an SSH connection. Within the AWS Cloud, a virtual private cloud (VPC) with a Red Hat EC2 instance is configured with the AWS CLI. IAM is configured, and you use the AWS CLI to interact with IAM.


1.To write the downloaded file to the current directory, run the following curl command with the -o option:
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

2.run the following unzip command with the -u option
unzip -u awscliv2.zip

3.run the install program, run the following command. This sudo command grants write permissions to the directory. The installation command in the code snippet uses a file named install in the unzipped aws directory to install the AWS CLI. 
sudo ./aws/install

4. To confirm the installation, run the following command:
   aws --version
5.To verify that the AWS CLI is now working, run the following aws help command. The help command displays the information for the AWS CL
6.In the AWS Management Console, in the Search box, enter IAM and choose IAM. This option takes you to the IAM console page.
7.In the navigation pane, choose Users, and then choose awsstudent.
8. You are now in the Permissions tab. Next to lab_policy, choose the arrow icon, and then choose the {} JSON button.
9. Choose the Security credentials tab. In the Access keys section, locate the awsstudent user's access key ID.
10. In the SSH session terminal window, run the configure command for the AWS CLI:
11. At the prompt, configure the following:

AWS Access Key ID: Choose the Details dropdown list, and choose Show. Copy and paste the AccessKey value into the terminal window.
AWS Secret Access Key: Copy and paste the SecretKey value into the terminal window.
Default region name: Enter us-west-2
Default output format: Enter json
12. In the terminal window, test the IAM configuration by running the following command:  aws iam list-users
13. In the IAM AWS CLI Command Reference documentation page, the following command lists IAM policies and filters customer managed policies:

aws iam list-policies --scope Local
14.use the version number Arn information and DefaultVersionId found inside the lab_policy document to retrieve the JSON IAM policy. Use the > command to save the file. 

 aws iam get-policy-version --policy-arn arn:aws:iam::038946776283:policy/lab_policy --version-id v1 > lab_policy.json
   

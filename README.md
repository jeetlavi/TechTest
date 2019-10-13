# TechTest
Tech Test Solution
This solution contains YAML based AWS cloud formation template that luanches a single Windows 2012 R@ EC2 instance with no RDP/SSH access.
The EC2 instance has public ip assigned and displays an HTML page providing its instance ID on both port 80 and 443.
The Output can be access at:
http://<Public IP address of the instance>/ID.html
  
Requirements:
Windows command prompt with AWS CLI profile setup. Use 'AWS configure' cmdlet to setup a new default profile.

Here are the pre-requisites/assumption made in the case:
1) The account from which CF template is being executed has access to luanch VPC,Subnets, EC2 instances and so on.
2) At any point, int he given problem we do not require RDP/SSH access to our EC2 instance.
3) User can obtain public IP address of the EC2 instance from the cloud formation stack-output.

Bit about the template:
Input required:
1) InputInstanceType - t2.micro (default)
2) InputCIDRBlock - 10.11.12.0/24 (default)
3) InputKeyName - To be provided by user

Output:
1) Instance ID
2) Instance public IP

To access output:

Go to - http://<Instance public IP>/ID.html or https://<Instance public IP>/ID.html
where <Instance public IP> is the second output mentioned above.
  
Execution: Execute command in Create Infra.txt file - AFTER - replacing the TechTest.Yaml file location to your local machine's location
Alternatively, use AWS console to create a cloud formation stack from TechTest.Yaml.

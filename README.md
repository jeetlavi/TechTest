# TechTest
Tech Test Solution
This solution contains YAML based AWS cloud formation template that luanches a single Windows 2012 R2 EC2 instance with no RDP/SSH access.
The EC2 instance has public ip assigned and displays an HTML page providing its instance ID on port 80.
The Output can be access at:
http://<Public IP address of the instance>/ID.html
  
Requirements:
Windows command prompt with AWS CLI profile setup. Use 'AWS configure' cmdlet to setup a new default profile.

Here are the pre-requisites/assumption made in the case:
1) The account from which CF template is being executed has access to luanch VPC,Subnets, EC2 instances and so on.
2) At any point, in the given problem, we do not require RDP/SSH access to our EC2 instance.

Bit about the template:
Input required:
1) InputInstanceType - t2.micro (default)
2) InputCIDRBlock - 10.11.12.0/24 (default)
3) InputKeyName - To be provided by user

Output:
1) Instance ID
2) Instance public IP

To access output:

Go to - http://<Instance public IP>/ID.html
where <Instance public IP> is the second output mentioned above.
  
Execution: Execute command in Create-Infra.txt file - AFTER -
1) replacing the TechTest.Yaml file location to your local machine's location.
2) replacing Key name in the command.
Example, is present in the Create-Infra.txt
Alternatively, use AWS console to create a cloud formation stack from TechTest.Yaml.

Note: Stack can be deleted using delete-stack cmdlet.

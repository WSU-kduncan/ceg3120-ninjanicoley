Project 4 Notes

CloudFormation 

1. Description

I modified the description to say Luedeman CF Template to create a VPC, allow SSH access from trusted networks, and create a single instance with an Elastic IP address. 

2. Mappings

The AMI I chose to use was the same AMI I used in Project 3 which is the Ubuntu Server 20.04 LTS (HVM), SSD Volume Type - ami-09e67e426f25ce0d7 (64-bit x86).

3. Resources

VPC range is set to /24 for the e.c.
Subnet range is set to /28 for the e.c.

4. Security Group Settings

I allowed SSH for the following trusted networks: 
Home: 74.140.198.202/32 - but this one is the !ref sshlocation default
WSU: 130.108.0.0/16
VPC: 10.0.0.0/24 

I used the same trusted networks as I did in Project 3 with the correct VPC connection. 

5. Instance Settings

Set the "tag" or key to CF-instance instead of Name. This was done under the tags section.
I set my private IP addess to 10.0.0.11
I added the commands to the script to install git, python3, and pip3

Extra Credit

Set the VPC to a range of /24
Set the Subnet to a range of /28

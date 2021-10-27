Project 4 Notes

CloudFormation 

1. Description

I modified the description to say Luedeman CF Template to create a VPC, allow SSH access from trusted networks, and create a single instance with an Elastic IP address. 

2. Mappings
3. Resources



4. Security Group Settings

I allowed SSH for the following trusted networks: 
Home: 74.140.198.202/32 
WSU: 130.108.0.0/16
VPC: 10.0.0.0/24

I used the same trusted networks as I did in Project 3 with the correct VPC connection. 

5. Instance Settings

Extra Credit
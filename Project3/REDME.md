Part 1 - Build a VPC
1. Create a VPC
To create a VPC, we need to go to services, Network & Content Delivery, and click on VPC. We will click on "Your VPCs" and click on Create VPC. The name tage will be luedeman-vpc. A IPv4 CIDR block is chosen for the range for the VPC. I went with 10.0.0.0/24. 
We then add a tag with the Key as Name and the value as luedeman-vpc (this might be autofilled). 

2. Create a subnet
We will click on Subnets located under VPCs in the left hand menu and then click create subnet. From here we select the vpc we created and give it the name of luedeman-subnet. The cider block is then made 10.0.0.0/28. We then give it a tag with a key of Name and value of luedeman-subnet (this may be autofilled). 

3. Create an internet gateway
We click on Internet Gateways in the left hand menu and click on create internet gateway. 
We name it luedeman-gw, make the Key in the tags section say Name and give it a value of luedeman-gw (this could be autofilled). 
After that, we must click on actions and attach to VPC in order to be able to talk with the internet. 

4. Create a route table
We click on route table from the same left hand menu. Click on create route table. 
We make the name luedeman-routetable and connect the VPC we made previously. We then add a tag with the key as Name and the value as luedeman-routetable (this may be autofilled). 

5. Create a security group
To create a security group, we go to Security Groups under Network and Security. We click on create security group and give it a name "luedeman-sg". 
We put in the description that it allows SSH to trusted networks and connect it the VPC we created previously. We add an inbound rule for a Custom TCP to port 22 and a source of an IPv4 and the IP address that you would like to allow for inbound. We make multiple inbound rules for all the allowed IP address we want to access this instance and give it an outbound rule to anywhere (0.0.0.0/0). We give it a tag of Name and luedeman-sg (this may be autofilled). 

6. Create a key pair (if necessary)
Creating a key pair was not necessary as I had already made a key pair in a prveious assignment. It was added to this instance that we create in the instance creation part of the project. 

Part 2 -  EC2 instances 
1. Create a new instance
    To create a new instance, from in the instances section of the EC2 dashboard, click on launch instances. This allows you to choose an AMI (Amazon Machine Image). I personally chose Ubuntu Server 20.04 LTS (HVM), SSD Volume Type - ami-09e67e426f25ce0d7 (64-bit x86) / ami-00d1ab6b335f217cf (64-bit Arm) and the type is t2.micro. 

2. Attach the instance type to your VPC. 
    In the configure instance details (while setting up the instance), under network, we will change the default vpc to the one we created. For example, the Luedeman-vpc. 
    When you change the VPC, the subnet is changed with it and tells you how many IP addresses are still available under it. 

3. Determine whether a Public IPv4 address will be auto-assigned to the instance. 
    The auto-assign public IP is set to use the subnet setting which disables the auto-assign setting. 
    With Elastic IP addresses, it allows us to rapidly remap the address to another instance in the VPC. They are account bound and we can only have 5 max per account. 
    Going with the elastic IP address, we are reserving one from the pool and connecting it to the instance so that one is not auto-reassigned although it could happen if AWS really wanted to. 

4. Attach a volume to your instance. 
    Step 4 of adding storage to the instance, we select a volume type to add. I stuck with the default personally which is the general purpose SSD (gp2).

5. Tag your instance with a "Name" of "YOURLASTNAME-instance" to your instance. 
    Tags are applied to all instances and volumes. So we add a tag with the key being Name and the value luedeman-instance. This is step 5 under creating an instance. 

6. Associate your security group, "YOURLASTNAME-sg" to your instance. 
    On Step6: Configure Security Group of creating the instance, we will assign the security group we made previously. To do that, we select existing security group and then click on the one we created. We then select review and launch. 

7. Reserve an Elastic IP address. Tage it with "YOURLASTNAME-EIP". Associate with your instance. 
    To reserve and allocate and Elastic IP address, we go to Elastic IPs under Network & Security. We then click on Allocate Elastic IP address. We then add a new tag and use Name as the key and luedeman-eip. 
    Then we need to associate it with our instance so we click on the EIP we just made (the little box next to it), then the drop down, Actions, and click on Associate Elastic IP address. We choose the Instance resource type and select the instance we created, luedeman-instance.We then click associate, go back to instances and reload them. TA-DA! 

8. Create a screenshot your instance details and add it here: 


9. ssh in to your instance. Change the hostname to "YOURLASTNAME-AMI" where AMI is some version of the AMI you chose. 
    
    We use the command "ssh -i ceg3120-aws-vm.pem ubuntu@3.211.99.167" to ssh into the instance we just created. The IP address is the one that was created when we made our elestic ip. 
    We then change the hostname by typing in "sudo hostnamectl set-hostname luedeman-ubuntu"

10. Create a screenshot of your ssh connection to your instance and add it here: (shows hostname)
Project 1 

Setup: how to initialize a repo and all other setup steps (users, permissions, keys)
Make sure you have a git account to start with
Start with creating the key pair for the instance on AWS
generate keys for github
change the permissions by using chmod 600 /path/to/private/key
create a .ssh/config file 
then you connect to the instance using ssh -i /path/to/private/key ubuntu@ElasticIP 


Usage:
clone- to create a working copy of a local repo
init- to create a new local repo
add- add files to staging
commit- commit changes to the head but not remote yet
push-send changes to the master


Proof: include screenshots of the repo 
  existing on the AWS instance
  being cloned to your local system

-the above will be added to the pushed project. 
<img width="572" alt="Screen Shot 2021-09-04 at 2 43 50 PM" src="https://user-images.githubusercontent.com/27076383/132105073-e2f32630-b9a3-4ac8-acd1-f267fa2fd44e.png">


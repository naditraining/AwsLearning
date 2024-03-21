# How to set up EC2 in private subnet and access from outside (internet) using SSH key pair and how to enable internet access to EC2 instance
  create VPC with private and public
  create EC2 in private and have just private IP
    note: make sure to link SSH key pair
  create bastion EC2 in public subnet and make sure it has public IP
    note: make sure to link same SSH key pair
  make sure the bastion allow SSH 22 inbound
  make sure bastion outbound goes to everywhere or private subnet EC2
  ssh-add ubuntuKeyPair.pem 
  ssh forwarding ssh -A ubuntu@public IP of public EC2 instance
  ssh ec2-user@private-instance-private-ip

# Enable internet access to EC2 in private subnet
  we need NAT to translate the private IP of EC2 to Public IP (Elastic IP) attached in NAT
  Create NAT with elastic IP (public IP)
  Update the route table of private subnet to forward the request to NAT for any internet access 0.0.0.0/0
  
  



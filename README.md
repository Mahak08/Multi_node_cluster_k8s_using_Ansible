# Multi_node_cluster_k8s_using_Ansible
Roles on Ansible Galaxy can be download by following commands
1)ansible-galaxy install mahak08.k8s_master

2)ansible-galaxy install mahak08.k8s_slave

3)ansible-galaxy install mahak08.provision_aws_ec2_instance

Description of Three roles 
1) aws_instance : It will launch ec2-instance on top of cloud 

Before running the playbook remember to add IAM Credential
->To add Credential -
  i) Create IAM role user.
  ii)Create credential and save them (download).
  ii)On top of cli run the following commands to add Access_key and secret_key
    - aws configure
    > give Access_key
    > give Secret_key
    > give region (eg. ap-south-1)
    
->In the vars file give instance ID , key_name , instance_type , instance_tags , region , vpc_subnet_id ,security_group , path: inventory_path   
->According to playbook the IP of the instances launch is DYNAMICALLY updated in the inventory for further use. 

2) Master role: Configure the master host and generate token so slave can get connected.
 
3) Slave role: Congigure the slave hosts , need master token to connect to master 

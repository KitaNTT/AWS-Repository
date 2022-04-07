## **TASK 1: Create a working VPC**<br />
### CREATE VPC<br />
![image](https://user-images.githubusercontent.com/89054503/160119616-5432de95-99e4-4cbd-910b-690f17b1b034.png)<br />
### Create subnet with vpc-id<br />
![image](https://user-images.githubusercontent.com/89054503/160119734-e893f283-c5b4-4984-818f-365658fea289.png)<br />
### Create an Internet Gateway<br />
![image](https://user-images.githubusercontent.com/89054503/160119790-17e10bc5-a2c2-49aa-8894-8f845351a8ea.png)<br />
### Update the internet-gateway-id and vpc-id<br />
![image](https://user-images.githubusercontent.com/89054503/160119841-e0322054-79fa-4cd2-b4bd-05eaf6c32847.png)<br />
### Create a custom route table<br />
![image](https://user-images.githubusercontent.com/89054503/160119860-d85c6b4c-3f6e-4841-be53-f7959f73c7e8.png)<br />
### Update the route-table-id and gateway-id <br />
![image](https://user-images.githubusercontent.com/89054503/160119888-ea4aa94a-3efd-4a82-adb9-4cf8bb10424c.png)<br />
### Check route has been created and is active<br />
![image](https://user-images.githubusercontent.com/89054503/160119923-9581b1ff-0ac6-4287-aad6-e6c0b3ec4c7b.png)<br />
### Retrieve subnet IDs<br />
![image](https://user-images.githubusercontent.com/89054503/160119939-e3a9d3f9-6157-4c88-8055-331da1c1f424.png)<br />
### Associate subnet with custom route table to make public <br />
![image](https://user-images.githubusercontent.com/89054503/160119964-c38f9d58-72f1-461c-8df0-021e76e87bc4.png)<br />
### Configure subnet to issue a public IP to EC2 instances<br />
![image](https://user-images.githubusercontent.com/89054503/160120012-458ac51f-9836-43ac-8ad8-065739d143cf.png)<br />
### Create EC2 instance in public subnet<br />
![image](https://user-images.githubusercontent.com/89054503/160120041-2407372b-2439-4d6c-abe8-cc27e4dcb81b.png)<br />
![image](https://user-images.githubusercontent.com/89054503/160120062-4bcb6d59-c8f1-4b4a-b6b1-0eb5a63e6645.png)<br />
### SSH to new EC Instance<br />
![image](https://user-images.githubusercontent.com/89054503/160120103-46b389c9-12ff-4d07-afcf-46c5340b90c4.png)<br />
## **TASK 2: Create a EC2 Instance in Private Subnet then Create a VPC Endpoint for SSM and connect Session Manager to this EC2 Instance**<br />
### Create EC2 Instance in Private Subnet, This EC2 Instance can not connected via SSM <br />
![image](https://user-images.githubusercontent.com/89054503/162139403-2d98608d-fd73-4cf8-a2c7-82f0fc55a386.png) <br />
### Create VPN Endpoint for SSM, SSM Message,  EC2 Message <br />
![image](https://user-images.githubusercontent.com/89054503/162139624-6c33e198-e974-43c4-86db-0a768276395b.png) <br />
### Reboot the EC2 Instance, after that we can connect SSM to this EC2 Instance <br />
![image](https://user-images.githubusercontent.com/89054503/162139963-61141827-600f-4c27-b49f-33262975d7ec.png) <br />
![image](https://user-images.githubusercontent.com/89054503/162139976-40a3bff4-f28c-411a-94ce-aa1034a17a66.png) <br />
## **TASK 3: Connect SSH to EC2 Instance and ping to another EC2 Instance via VPC Peering** <br />
### Create VPC Peering to another account <br />
![image](https://user-images.githubusercontent.com/89054503/162145871-2c6f7f49-eec8-4932-abd5-25e532fcd584.png)
### Accept VPC <br />
![image](https://user-images.githubusercontent.com/89054503/162140278-27b27eb6-c4ba-46fe-a509-72748682cdfb.png) <br />
### Add Route to VPC Peering Subnet via Peering Connection <br />
![image](https://user-images.githubusercontent.com/89054503/162146037-b0825175-e823-41f6-8187-ffe498139847.png)
### SSH to EC2 Instance Same Account, then SSH to another EC2 Instance <br />
![image](https://user-images.githubusercontent.com/89054503/162140326-bfbcf52d-81f6-4086-b55a-1d6986218ca7.png) <br />


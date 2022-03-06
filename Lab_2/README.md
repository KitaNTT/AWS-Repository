## **TASK 1: Create EC2 instance with type t2.micro (in a public subnet)**<br />
### **Launch instance LostSSHKey**<br />
![image](https://user-images.githubusercontent.com/89054503/156892743-2876c5d1-f468-47f7-b27c-05c9a406a062.png)<br />
### **Show all instance state**<br />
![image](https://user-images.githubusercontent.com/89054503/156892776-a38333e2-f85e-4694-a02f-f0d004c35baf.png)<br /><br />
## **TASK 2: Connect SSH to the EC2 instance, remove the authorized_keys then disconnect the SSH and restore the authorized_keys to restore SSH access**<br />
### **SSH to Instance LoshSSHKey then remove authorized_keys file**<br />
![image](https://user-images.githubusercontent.com/89054503/156892846-ae9e8038-cedc-45fb-8f1e-0069666d9787.png)<br />
### **Stop Instance LostSSHKey then launch another Instance Named RecoverSSHKey (Both Instance using the same key-pair)**<br />
![image](https://user-images.githubusercontent.com/89054503/156892870-aaf3d989-bfa4-4c6e-ad18-226e0fe43db1.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156892883-8af33d75-deda-4f32-9902-74a74bd88738.png)<br />
### **Detach volume of Instance LostSSHKey to RecoverSSHKey**<br />
![image](https://user-images.githubusercontent.com/89054503/156892905-79db445a-d207-43c7-8970-27b9e18b9054.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156892906-2fd754d0-b808-4d45-88e6-f86130881429.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156892909-da7812c8-c043-425d-93e9-1ca8c6ec417e.png)<br />
### **SSH to Instance RecoverSSHKey**<br />
![image](https://user-images.githubusercontent.com/89054503/156892963-564872d2-b2ec-4400-b165-719d06196f8c.png)<br />
### **Mount volume of Instance LostSSHKey to direction /mnt/tempvol**<br />
![image](https://user-images.githubusercontent.com/89054503/156892980-6d00a78f-0c67-4d4d-b6d5-f2aa7af67d3b.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156892987-12db5062-b632-4dce-b486-5caaa6e7a23b.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156893009-67442a0a-4b09-4f1e-9707-0407c73c4e12.png)<br />
### **Copy authorized_keys to LostSSHKey Volume**<br />
![image](https://user-images.githubusercontent.com/89054503/156893022-bd6a5d7b-9a72-4699-9520-0cdd08959a01.png)<br />
### **Stop Instance RecoverSSHKey**<br />
![image](https://user-images.githubusercontent.com/89054503/156893033-c5f0e414-e6c8-4771-989c-accb1acb07c4.png)<br />
### **Detach LostSSHKey Volume to LostSSHKey Instance**<br />
![image](https://user-images.githubusercontent.com/89054503/156893040-d20dcd89-4846-4612-9224-8810f90605e3.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156893041-44152d51-410f-4e50-ac74-7816773dd5bc.png)<br />
### **Start LostSSHKey Instance**<br />
![image](https://user-images.githubusercontent.com/89054503/156893052-6670d930-f007-46a8-bf76-e62fa9a2b36a.png)<br />
### **Now can ssh again to LostSSHKey Instance**<br />
![image](https://user-images.githubusercontent.com/89054503/156893058-25818643-427d-4255-a319-8e30a4a15f40.png)<br />
## **TASK 3: Using Session Manager to the EC2 instance**<br />
### **Create Role for EC2 Service**<br />
![image](https://user-images.githubusercontent.com/89054503/156911190-562c3e25-b566-4765-b9da-4e2681a121de.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156911204-bae1c9c2-914d-40e5-8791-db03b48fa7e8.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156911213-b8101d70-ace4-4ab9-99e5-4bf965cbd505.png)<br />
### **Attach Role to instance LostSSHKey**<br />
![image](https://user-images.githubusercontent.com/89054503/156911249-85ff6a6b-fc9a-476d-9c5f-79b00c49c59a.png)<br />
**Use Session Manager to access Instance LostSSHKey**<br />
![image](https://user-images.githubusercontent.com/89054503/156911260-59fe7926-5b8b-4581-9ba1-3b3acfe6625f.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156911265-48b10b7f-e8d8-4e67-b824-b57ec6adfc13.png)<br />
## **TASK 4: Install nginx on the EC instance**<br />
### **Configure the EC2 instance can be accessed HTTP 80 from the Internet**<br />
![image](https://user-images.githubusercontent.com/89054503/156911331-48e5e9d5-23f8-4e41-8277-685d58e9fe20.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156911334-5adcf19e-e2c4-4668-8a25-3265ede9bcf3.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156911335-54a847bb-98ce-4956-ad1f-fc5ded1c6034.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156911336-6ca7e100-98d0-4219-8e19-6454280daa6e.png)<br />
### **Sending nginx access logs to CloudWatch Logs**<br />
#### **Attach Policy “allow access to CloudWatch” to ec2role**<br />
![image](https://user-images.githubusercontent.com/89054503/156911908-77dac332-9cd9-4c37-af45-3da6c2e92e9f.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156911910-040c6713-d8eb-4975-b0c1-a24c46ea2593.png)<br />
#### **Install awslog**<br />
![image](https://user-images.githubusercontent.com/89054503/156911346-2cf8670d-8686-4dc1-9ba9-b29f14511ab8.png)<br />
#### **Mapping access and error log of nginx to awslog direction**<br />
![image](https://user-images.githubusercontent.com/89054503/156911436-5c43fa64-d1c3-441d-a284-6193207727dc.png)<br />
#### **Start awslogs service**<br />
![image](https://user-images.githubusercontent.com/89054503/156911361-2ee6666d-8bb2-4eba-9a9f-f7cc0aa62fa8.png)<br />
#### **View access log and error log from CloudWatch**<br />
![image](https://user-images.githubusercontent.com/89054503/156911365-60d8471f-84e1-4c2a-9fdc-407b3ac24337.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156911366-3e11abdf-0fee-4f0a-a5c0-91f872d8e0a1.png)<br />




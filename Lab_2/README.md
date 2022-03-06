## **TASK 1: Create EC2 instance with type t2.micro (in a public subnet)**<br />
**Launch instance LostSSHKey**<br />
![image](https://user-images.githubusercontent.com/89054503/156892743-2876c5d1-f468-47f7-b27c-05c9a406a062.png)<br />
**Show all instance state**<br />
![image](https://user-images.githubusercontent.com/89054503/156892776-a38333e2-f85e-4694-a02f-f0d004c35baf.png)<br /><br />
## **TASK 2: Connect SSH to the EC2 instance, remove the authorized_keys then disconnect the SSH and restore the authorized_keys to restore SSH access**<br />
**SSH to Instance LoshSSHKey then remove authorized_keys file**<br />
![image](https://user-images.githubusercontent.com/89054503/156892846-ae9e8038-cedc-45fb-8f1e-0069666d9787.png)<br />
**Stop Instance LostSSHKey then launch another Instance Named RecoverSSHKey (Both Instance using the same key-pair)**<br />
![image](https://user-images.githubusercontent.com/89054503/156892870-aaf3d989-bfa4-4c6e-ad18-226e0fe43db1.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156892883-8af33d75-deda-4f32-9902-74a74bd88738.png)<br />
**Detach volume of Instance LostSSHKey to RecoverSSHKey**<br />
![image](https://user-images.githubusercontent.com/89054503/156892905-79db445a-d207-43c7-8970-27b9e18b9054.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156892906-2fd754d0-b808-4d45-88e6-f86130881429.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156892909-da7812c8-c043-425d-93e9-1ca8c6ec417e.png)<br />
**SSH to Instance RecoverSSHKey**<br />
![image](https://user-images.githubusercontent.com/89054503/156892963-564872d2-b2ec-4400-b165-719d06196f8c.png)<br />
**Mount volume of Instance LostSSHKey to direction /mnt/tempvol**<br />
![image](https://user-images.githubusercontent.com/89054503/156892980-6d00a78f-0c67-4d4d-b6d5-f2aa7af67d3b.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156892987-12db5062-b632-4dce-b486-5caaa6e7a23b.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156893009-67442a0a-4b09-4f1e-9707-0407c73c4e12.png)<br />
**Copy authorized_keys to LostSSHKey Volume**<br />
![image](https://user-images.githubusercontent.com/89054503/156893022-bd6a5d7b-9a72-4699-9520-0cdd08959a01.png)<br />
**Stop Instance RecoverSSHKey**<br />
![image](https://user-images.githubusercontent.com/89054503/156893033-c5f0e414-e6c8-4771-989c-accb1acb07c4.png)<br />
**Detach LostSSHKey Volume to LostSSHKey Instance**<br />
![image](https://user-images.githubusercontent.com/89054503/156893040-d20dcd89-4846-4612-9224-8810f90605e3.png)<br />
![image](https://user-images.githubusercontent.com/89054503/156893041-44152d51-410f-4e50-ac74-7816773dd5bc.png)<br />
**Start LostSSHKey Instance**<br />
![image](https://user-images.githubusercontent.com/89054503/156893052-6670d930-f007-46a8-bf76-e62fa9a2b36a.png)<br />
**Now can ssh again to LostSSHKey Instance**<br />
![image](https://user-images.githubusercontent.com/89054503/156893058-25818643-427d-4255-a319-8e30a4a15f40.png)<br />
##**Task 3: Using Session Manager to the EC2 instance**
**Create Role for EC2 Service**
![image](https://user-images.githubusercontent.com/89054503/156911190-562c3e25-b566-4765-b9da-4e2681a121de.png)





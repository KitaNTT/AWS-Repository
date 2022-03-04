**Tạo EC2, và thực hiện assumerole thông qua AWS CLI**

**SSH vào EC2 instance**

![image](https://user-images.githubusercontent.com/89054503/156734278-1a3ba997-1997-4c04-8d33-78c1ac274d07.png)

**Cấu hình profile adminaccess có quyền admin**
Cấu hình admin profile credential
![image](https://user-images.githubusercontent.com/89054503/156733981-9d15e9cb-3ad6-4c4e-a493-84963297c5a1.png)
Kiểm tra thông tin identity
![image](https://user-images.githubusercontent.com/89054503/156734000-cd3795cd-349c-4d1f-9c5d-aa310d637b18.png)

**Dùng admin để tạo tài khoản kita2**
Tạo user kita2 bằng profile admin
![image](https://user-images.githubusercontent.com/89054503/156734375-92eb49c7-f445-4412-98e2-320e6a5f4f48.png)
Tạo file policy json có nội dung sau cho iam user kita2 có quyền truy cập ec2 iam:listrole và sts:assumerole
![image](https://user-images.githubusercontent.com/89054503/156734395-153ed5c7-3727-4e1f-8409-65cce13ac33e.png)
Tạo policy cho kita2 bằng profile admin
![image](https://user-images.githubusercontent.com/89054503/156734432-e0fc9d04-969f-4518-a425-8d2481e54f09.png)
Attach Policy vào kita2
![image](https://user-images.githubusercontent.com/89054503/156734453-9b96d004-b244-45f4-a045-3c29b76be2a2.png)
Tạo Access Key cho kita2
![image](https://user-images.githubusercontent.com/89054503/156734508-8131ca80-c6be-425f-8694-8dbd89b24ef1.png)

**Tạo AssumeRole có quyền list s3 bucket**
Tạo file Trust Relationship Policy có nội dung sau cho iam role assumerole
![image](https://user-images.githubusercontent.com/89054503/156734812-2060ef65-8e30-469d-b3ce-fc8acedb2cad.png)
Tạo Role
![image](https://user-images.githubusercontent.com/89054503/156734865-0679f1b0-9e7a-4d7c-a649-383ec0c776d9.png)
Attach Policy arn:aws:iam::aws:policy/AmazonS3FullAccess vào role assumerole
![image](https://user-images.githubusercontent.com/89054503/156734883-62c76f05-fa62-4ddb-8a28-bb1bb3646e5f.png)

**Dùng iam user kita2 assume role assumerole**
Assume Role
![image](https://user-images.githubusercontent.com/89054503/156734907-a3db01c6-295c-415b-8832-14b971a6d00f.png)
Configure profile, session_token cho assumerole sau đó thực hiện aws s3 ls
![image](https://user-images.githubusercontent.com/89054503/156735053-c364b810-c575-4d16-8f1a-5477f88313be.png)


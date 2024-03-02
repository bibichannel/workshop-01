---
title : "Chuẩn bị VPC và EC2"
date :  "`r Sys.Date()`" 
weight : 7
chapter : false
pre : " <b> 3.7 </b> "
---

Tiếp theo ta sẽ thực hiện push code lên repository trên CodeCommit ta vừa tạo ở bước [2.5](/2-prerequiste/2.5-createCodeCommit/)

- Truy cập vào CodeCommit copy url https của repo 

![IMAGE](/images/3-developmentEnvironment/3.7-pushCode/001-pushCode.png)

Sau đó ta thực hiện push code lên CodeCommit với các câu lệnh sau:
```shell
git remote add origin https://git-codecommit.us-east-1.amazonaws.com/v1/repos/workshop-01-react
git add .
git commit -m "fist push"
git push --set-upstream origin master
```
![IMAGE](/images/3-developmentEnvironment/3.7-pushCode/002-pushCode.png)

Truy cập vào CodeCommit ta thấy source code đã được push lên.

![IMAGE](/images/3-developmentEnvironment/3.7-pushCode/003-pushCode.png)
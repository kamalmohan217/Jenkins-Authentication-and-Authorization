# Jenkins-User-Authentication-and-Authorization

For Jenkins User Authentication I am explaining two steps
1. LDAP
2. Jenkins own user database

For Authorization I am explaining 
1. Matrix based security
2. Project-based Matrix authorization strategy

### Authentication
1. LDAP

I am using open LDAP and created three users dexter who has administrative privileges and user1 and user2 who are normal users whose access I will restrict.

![image](https://github.com/user-attachments/assets/a75293b6-c7df-4673-9c92-7daa1cebbfa5)

I logged-in with user dexter who has administrative privilege
![image](https://github.com/user-attachments/assets/e9b3b6b7-8391-4220-91ad-74472daafc43)

Go to **Manage Jenkins** > **Security** as shown in the screenshot attached below.

![image](https://github.com/user-attachments/assets/940d7317-58e2-4f26-99df-69a6d99515f7)
![image](https://github.com/user-attachments/assets/06d362e2-8f55-4a1a-8c6b-f45a31e2e27d)
![image](https://github.com/user-attachments/assets/152eefbb-8153-4365-8c42-567da607f7e0)

First of all I am using **Matrix based security** as shown in the screenshot attached below.

For Authenticated users I had provided overall Read permission and for user1 I had provided only Read permission at Job level. For user2 I had provided Read and Build permission as Job level as shown in the screenshot attached below.
![image](https://github.com/user-attachments/assets/69816d79-edfc-492a-bdf2-b194b513129b)

When login with user1 can only read the job but can not build the job as the user don't have build access, shown in the screenshot attached below.

![image](https://github.com/user-attachments/assets/3484019f-f165-4e66-96cd-16987e4dff78)
![image](https://github.com/user-attachments/assets/a81e38e3-0fd6-49e4-aa88-c67bc4efbc7d)

When login with user2 can read and build the job as shown in the screenshot attached below.
![image](https://github.com/user-attachments/assets/60a06678-5673-4edc-99d1-5ae202b54eb2)
![image](https://github.com/user-attachments/assets/8757123c-2ab3-4da4-b57a-7b8788dcdce9)
![image](https://github.com/user-attachments/assets/cb260fc7-1317-4112-9218-1fb6002c3506)

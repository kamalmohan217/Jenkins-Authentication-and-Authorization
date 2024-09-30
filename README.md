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
![image](https://github.com/user-attachments/assets/3b8973fb-1b0a-484f-ae2f-8c4ed74cd252)
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

Now I am using **Project-based Matrix authorization strategy** and provided overall Read and Build access to the user2 as shown in the screenshot attached below.

![image](https://github.com/user-attachments/assets/96fd5a08-5d63-4ad4-bbe0-fb5a0a4acd73)

Go to **Manage Jenkins** > **Security** as shown in the screenshot attached below.
![image](https://github.com/user-attachments/assets/a290eec1-53d5-475f-b020-c62645ada824)

In Jenkins Job test-2 I did not enable project based security while in Jenkins Job test-1 I enabled project based security with the condition of **Inherit permissions from parent ACL** as shown in the screenshot attached below. In test-1 Jenkins Job user1 has Job based Read access as shown in the screenshot attached below.

![image](https://github.com/user-attachments/assets/b3cc8dd1-8629-4b5f-baef-986509b4113a)
![image](https://github.com/user-attachments/assets/fb54e7dc-f009-43f5-b521-2253ca139ebb)

I can conclude that the user1 can only read test-1 jenkins job and can not read any jenkins job as shown in the screenshot attached below.

![image](https://github.com/user-attachments/assets/61aea66e-d01f-473c-b1f8-0ea99dca6f8d)
![image](https://github.com/user-attachments/assets/77917d51-cdea-4760-8026-fb8a6fda339a)

However user2 can Read and Build both the jenkins job test-1 and test-2 as shown in the screenshot attached below.

![image](https://github.com/user-attachments/assets/83af73de-e7f0-4bdc-8b40-b18cff172882)
![image](https://github.com/user-attachments/assets/07ebf0ac-a0b6-4572-855b-b26f6cafb2be)
![image](https://github.com/user-attachments/assets/a3c0bb79-6fd2-4a2e-92da-67e89c653540)

Now in Jenkins Job test-2 I did not enable project based security while in Jenkins Job test-1 I enabled project based security with the condition of **Do not Inherit permissions granted from other ACLs** as shown in the screenshot attached below. In test-1 Jenkins Job user1 has Job based Read access as shown in the screenshot attached below.

![image](https://github.com/user-attachments/assets/a83ff166-81fa-4851-b25f-f2a4286eeb55)

With this condition user1 can only see jenkins job test-1 and user2 can only see jenkins job test-2 with Build Access as shown in the screenshot attached below.

![image](https://github.com/user-attachments/assets/3657b634-0db4-4569-b619-71c0dfaf0972)
![image](https://github.com/user-attachments/assets/3ad3c246-362e-4c01-a065-f82bbc649935)

![image](https://github.com/user-attachments/assets/2d45eb30-a146-4d3d-9dc9-5e8714667260)
![image](https://github.com/user-attachments/assets/3f45b51e-5296-4438-a599-e3acf4fc5ade)

For **Jenkins own user database** go to **Manage Jenkins** > **Security** as shown in the screenshot attached below.

![image](https://github.com/user-attachments/assets/1b92ca0c-4781-40d3-bda0-e9b74344de28)

For Autorization mode I chosen Logged-in users can do anything. However you can restrict the user with Matrix based security or Project-based Matrix authorization strategy as explain earlier. I have unchecked Allow anonymous read access.

![image](https://github.com/user-attachments/assets/9948828a-2ddd-4d7a-b764-cdbbbb0d130a)

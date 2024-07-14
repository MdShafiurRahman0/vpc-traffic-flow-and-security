### VPC Traffic Flow and Security

VPC Networking project: 


### Project Architecture:


![image](https://github.com/user-attachments/assets/6eabf784-0b4b-46c4-bc28-351d1e744efe)




1. ☁️ An Amazon VPC (amazing!)
3. 🥅 A public subnet (woohoo!)
4. 🚪 An internet gateway (go you!)



#Let's get ready to:

1. 🚏 Create a route table.
2. 👮‍♀️ Create a security group.
3. 📋 Create a Network ACL (Network Access Control List).




![image](https://github.com/user-attachments/assets/1f98558a-5380-4199-9568-766d600c733f)


Step 1: Create a VPC 

![image](https://github.com/user-attachments/assets/6a077feb-0207-4fcf-88ae-88db9008d14f)




# Remember CIDR block: 


![image](https://github.com/user-attachments/assets/b613aff2-5320-4460-9a32-4d8855f0d9d0)



Step 2: Create  Subnets



Configure your subnet settings:

1. **VPC ID:** name VPC
2. **Subnet name:** Public 1
3. **Availability Zone:** Select the first Availability Zone in the list.
4. **IPv4 VPC CIDR block:** 10.0.0.0/16
5. **IPv4 subnet CIDR block:** 10.0.0.0/24


![2024-07-13_13h13_59](https://github.com/user-attachments/assets/722ba48a-8b25-4153-809e-5b3a4fa29960)

![image](https://github.com/user-attachments/assets/edcac603-4264-4d3d-adb5-a0514e846d1c)





Step 3: Create an Internet Gateway

![image](https://github.com/user-attachments/assets/8afd2421-3c1d-4310-ae09-35efddc24c12)



![2024-07-13_13h25_32](https://github.com/user-attachments/assets/73275050-0161-4fb0-a4e2-473da8fb9c76)



1. **Choose Create internet gateway.**
2. **Select your newly created internet gateway and choose Actions, then Attach to VPC.**
3. **Select NextWork VPC.**
4. **Select Attach internet gateway.**


![2024-07-13_13h27_41](https://github.com/user-attachments/assets/b39c154a-9267-4aed-b7b9-23519aadd66b)


Step 4: Create a Route Table

![image](https://github.com/user-attachments/assets/99d065a3-6111-423b-81cc-33de3bade23a)


![2024-07-13_13h55_40](https://github.com/user-attachments/assets/02c571d6-36f1-4bff-989f-4e41b1ec2cd0)




1. **Select the Routes tab.**
2. **Choose Edit routes.**
3. **Choose Add route near the bottom of the page.**


![2024-07-13_13h58_15](https://github.com/user-attachments/assets/1c6f75c5-d08b-40d5-b984-dab8b62070e0)



💡 Why is the destination 0.0.0.0/0?
0.0.0.0/0 means all IPv4 addresses! When you set 0.0.0.0/0 as the destination in a route table, you are creating a default route that sends any traffic that doesn't match more specific routes on your route table.

In your case, since the the only other route has a destination of 10.0.0.0/16, this means all traffic that is not bound for another resource within your VPC is bound for the internet gateway!

The internet gateway then forwards this traffic to the internet, allowing your resources to communicate with external networks and users.





![2024-07-13_13h58_40](https://github.com/user-attachments/assets/f770a9e1-1b94-4544-a9fa-a37e116480f3)


![image](https://github.com/user-attachments/assets/f036ba07-52f6-4548-af44-dae0b3cc731a)


Step 5: Create a security group


![image](https://github.com/user-attachments/assets/cefcd7a8-8fc2-4940-95ab-23a18107592a)




![2024-07-13_17h10_07](https://github.com/user-attachments/assets/cd34f79e-4f9f-45e4-a667-5d3e0903ef6e)


## Step 6: Create a Network ACL

![image](https://github.com/user-attachments/assets/06917714-4e82-416d-abe0-a197277bc878)




![2024-07-13_18h17_04](https://github.com/user-attachments/assets/facc0c7f-8554-4239-8100-a9fdc79394ad)



## Choose the top network ACLs that's associated with your Public 1 subnet, and check out the tabs for Inbound rules and Outbound rules.

![image](https://github.com/user-attachments/assets/2941b630-ddc3-4850-8558-99da520ad704)


## Under the Subnet associations tab, select Edit subnet associations.

![2024-07-13_18h27_40](https://github.com/user-attachments/assets/5cb8e991-0da1-4515-a357-510a93b6b78e)


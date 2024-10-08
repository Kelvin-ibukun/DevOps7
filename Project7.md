# Project7 - AWS VPC Project

A VPC in AWS enables you to launch resources within a secure, isolated virtual network that you control.

## Step 1 - VPC Creation

- I logged in to my AWS console and searched for VPC as shown below:

![1](img/1.png)

![2](img/2.png)

- Creation of Internet Gateway

I created internet gateway as shown in the images below:

![3](img/3.png)

![4](img/4.png)

![5](img/5.png)

![6](img/6.png)

![7](img/7.png)

- Creating subnet naming schemes and subnets

1. Creation of Public Subnet - I followed the steps in the images below:

![8](img/8.png)

![9](img/9.png)

![10](img/10.png)

![11](img/11.png)

![12](img/12.png)

- I used the steps in the images above to create subnets for:

1. Application Subnets

![13](img/13.png)

2. Database Subnets

![14](img/14.png)

3. Management Subnets

![15](img/15.png)

4. Platform Subnets

![16](img/16.png)

** After creating the subnets, this is what I have **

![17](img/17.png)

## Route Table Design

I created a custom route table for each subnet group and then set the necessary rules for the subnets. The first one done is for Public route table and it's as shown below:

![18](img/18.png)

![19](img/19.png)

![20](img/20.png)

I added 3 public subnets (prod-web-public a,b,c) as shown below:

![21](img/21.png)

- The image below is what I have after creating all 5 route tables and their subnet association:

![22](img/22.png)

## NAT (Network Address Translation) Gateway

A NAT gateway allows instances in a private subnet to access external services, while preventing external services from initiating connections to those instances.

To do this, we created a NAT gateway and attached it to all our route tables created earlier as shown below:

![23](img/23.png)

![24](img/24.png)

We add NAT gateway to our route tables one by one as shown below:

![26](img/26.png)

![27](img/27.png)

![28](img/28.png)

The steps above is repeated for the other route tables (DB, APP and MGT route tables)

** It should be noted that the Public subnet was left out. This is deliberate as as we want to route traffic using internet gateway as shown below:**

![29](img/29.png)

![30](img/30.png)

![31](img/31.png)

## AWS VPC Topology

- To check VPC topology, we follow the steps as shown in the images below:

![32](img/32.png)

![33](img/33.png)

## Network ACLs

Network access control list (NACL) in a VPC manages inbound and outbound traffic at the subnet level.

Here is a step by step on a Network ACLS:

![34](img/34.png)

![35](img/35.png)

![36](img/36.png)

![37](img/37.png)

![38](img/38.png)

![39](img/39.png)

![40](img/40.png)

![41](img/41.png)

END OF PROJECT 7
<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Creating a Private Subnet

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-private)

**Author:** Aaron  
**Email:** longshotbeats@gmail.com

---

## Creating a Private Subnet

![Image](http://learn.nextwork.org/gleeful_red_proud_durian/uploads/aws-networks-private_afe1fdbd)

---

## Introducing Today's Project!

### What is Amazon VPC?

is a service that allows you to create a logically isolated section of the AWS cloud, providing a private network environment for your AWS resources.

### How I used Amazon VPC in this project

to create private and public subnets, route tables, and network ACL, and security group

### One thing I didn't expect in this project was...

i didn't expect to be creating private subnets, route tables,  and network  ACL.

### This project took me...

two hours

---

## Private vs Public Subnets

The difference between public and private subnets is that in their connectivity to the internet. Public subnets have a route to an internet gateway, allowing resources within them to directly access the internet, while private subnets lack this direct route and rely on mechanisms like NAT gateways to access the internet indirectly.

Private subnets are useful because they enhance network security by restricting direct internet access to sensitive resources within a VPC

My private and public subnets cannot have the same IP address.

![Image](http://learn.nextwork.org/gleeful_red_proud_durian/uploads/aws-networks-private_afe1fdbd)

---

## A dedicated route table

By default, my private subnet is associated with the default network ACL for the VPC.

I had to set up a new route table because when you want to customize how network traffic is routed within a VPC 

My private subnet's dedicated route table only has one inbound and one outbound rule that allows traffic within the VPC itself (local routes) and traffic destined for the internet to be routed through a NAT Gateway or other managed service, but it generally does not allow direct traffic to the internet. 

![Image](http://learn.nextwork.org/gleeful_red_proud_durian/uploads/aws-networks-private_b4b904b5)

---

## A new network ACL

By default, my private subnet is associated with a route table that does not have a route to an internet gateway.

I set up a dedicated network ACL for my private subnet because to explicitly allow or deny specific inbound and outbound traffic, supplementing the rules defined in your security groups.

My new network ACL has two simple rules allows all inbound and outbound traffic, or explicitly denies all inbound and outbound traffic, depending on the rules' configurations. 

![Image](http://learn.nextwork.org/gleeful_red_proud_durian/uploads/aws-networks-private_1ed2cb07)

---

---

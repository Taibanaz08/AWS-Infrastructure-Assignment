# AWS Infrastructure Assignment - Questions & Answers

## Part 1 - IAM
### Q1. Why should the root account not be used for daily activities?
*Answer:*

The root account has full access to all AWS services. It should only be used for account setup and critical tasks to improve security.

---
### Q2. What is the difference between an IAM User and an IAM Role?

*Answer:*
- IAM User is created for a person and has permanent credentials.
- IAM Role provides temporary permissions to AWS services or users.

---

### Q3. Why are Groups preferred over assigning permissions directly to users?

*Answer:*

Groups make permission management easier because the same permissions can be assigned to multiple users at once.

---
## Part 2 - VPC
### Q4. Why create a custom VPC instead of using the default VPC?

*Answer:*
A custom VPC provides better control over networking, IP addresses, routing, and security.

---

### Q5. Why are multiple Availability Zones used?

*Answer:*
Multiple Availability Zones improve High Availability by keeping the application running even if one Availability Zone fails.

---
### Q6. What happens if the Internet Gateway is detached?

*Answer:*
The EC2 instances lose internet connectivity and cannot send or receive internet traffic.

---
### Q7. What happens if the default route (0.0.0.0/0) is removed?

*Answer:*
Internet traffic cannot reach the Internet Gateway, so the instances cannot access the internet.

---
## Part 3 - Security Groups
### Q8. What is the purpose of a Security Group?

*Answer:*
A Security Group acts as a virtual firewall that controls inbound and outbound traffic for EC2 instances.

---
### Q9. What is the difference between a Security Group and a Network ACL (NACL)?
*Answer:*
- Security Group works at the instance level and is stateful.
- NACL works at the subnet level and is stateless.
---
### Q10. Why should SSH not be open to the entire internet in production?

*Answer:*
Opening SSH to everyone increases security risks. It should be restricted to trusted IP addresses.

---
## Part 4 - EC2

### Q11. Why are the servers placed in separate Availability Zones?

*Answer:*
Servers are placed in different Availability Zones to improve High Availability.

---
### Q12. What happens if one Availability Zone becomes unavailable?

*Answer:*
The Load Balancer sends traffic to the healthy EC2 instance in the other Availability Zone.

---
## Part 5 - EBS
### Q13. Why does the file remain after reboot?

*Answer:*
The file remains because EBS is persistent storage.

---
### Q14. What is the difference between RAM and EBS?

*Answer:*
RAM is temporary memory, while EBS is permanent storage.

---
### Q15. What happens if the EBS volume is detached?

*Answer:*
The EC2 instance cannot access the data stored on the EBS volume.

---
## Part 6 - Target Groups
### Q16. What is the purpose of a Target Group?

*Answer:*
A Target Group routes traffic to healthy EC2 instances.

---
### Q17. Why does a Load Balancer use Target Groups?

*Answer:*
It uses Target Groups to send requests only to healthy EC2 instances.

---
## Part 7 - Application Load Balancer
### Q18. Why is a Load Balancer required?

*Answer:*
A Load Balancer distributes traffic across multiple EC2 instances.

---
### Q19. What happens if one EC2 instance fails?

*Answer:*
Traffic is automatically sent to the healthy EC2 instance.

---
### Q20. What is the purpose of Health Checks?

*Answer:*
Health Checks identify healthy and unhealthy EC2 instances.

---
## Part 8 - Failure Testing
### Q21. Why was the application still accessible?

*Answer:*
The Load Balancer redirected traffic to the healthy EC2 instance.

---
### Q22. Which AWS component handled the failure?

*Answer:*
The Application Load Balancer and Target Group handled the failure.

---
## Part 9 - Auto Scaling Group
### Q23. What is Desired Capacity?

*Answer:*
Desired Capacity is the number of EC2 instances Auto Scaling keeps running.

---
### Q24. What is the purpose of a Launch Template?

*Answer:*
A Launch Template stores the EC2 configuration used to launch new instances.

---
### Q25. How does Auto Scaling improve availability?

*Answer:*
It automatically launches or replaces EC2 instances when needed.

---
## Troubleshooting Challenges
### Q26. Delete the route 0.0.0.0/0. What happens?

*Answer:*
The instances lose internet access. Add the route back to the Internet Gateway to fix it.

---
### Q27. Remove Port 80 from the Security Group. What happens?

*Answer:*
The website becomes inaccessible. Add Port 80 back to restore access.

---
### Q28. Stop one EC2 instance. Why does the application still work?

*Answer:*
The Load Balancer sends traffic to the healthy EC2 instance.

---
### Q29. Detach the EBS volume. What happens?

*Answer:*
The EC2 instance cannot access the data stored on the EBS volume.

---
### Q30. Remove all targets from the Target Group. What happens?
*Answer:*
The Load Balancer has no healthy targets, so the application becomes unavailable. Register the EC2 instances again to fix it.

# Azure - Managing Network Access Control

# Managing Network Access Using Azure Firewall and Custom Routes
![Network Diagram](https://i.imgur.com/qFwsRK0.png)

## Summary

In this project, Azure Firewall is deployed and configured to manage inbound and outbound traffic of the network workload.  

## Objective
The main objective of this project is to demonstrate how network access can be controlled in Azure using custom routes, ACLs (Access Control Lists), and network/application rules. 

Managing network traffic is essential for protecting data and resources from unauthorized access. Applying specific rules for ingress/egress traffic is one of the methods Information Security professionals utilize to prevent network and data breaches from occurring.   

## Platform and Technologies Utilized

- Microsoft Azure
  - Azure Firewall
  - ARM (Azure Resource Manager) template
  - Virtual Machines
  - DNS Servers
  - Resource Groups
  
- Additional Items
  - Subnets 
  - Firewall Rules (Egress)
  - Application Rules (Outbound Traffic)
  - Custom Routes 
  - Remote Desktop (RDP)
  - External DNS server query
  - Infrastructure as Code (IaC)

## Part 1: Deploy Network Environment Using ARM (Azure Resource Manager)

In this phase, the network environment is deployed using an ARM template. The network includes multiple VMs as well as NSGs. 

ARM is an Azure service that allows you to deploy resources via IaC. Once the template is loaded into the Azure environment, the specified services will deploy including region, protocol, provisions, access control, etc. 

The configurations used to accomplish this include: 

-	ARM Template (written in JSON)
-	Created Resource Group
<br/>

<b>Uploading Custom ARM Template</b>

![Adding Template](https://i.imgur.com/QSaBYBB.png)

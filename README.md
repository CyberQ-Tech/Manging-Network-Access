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
<b>Uploading Custom ARM Template 1</b>

![Adding Template](https://i.imgur.com/QSaBYBB.png)

<b>Uploading Custom ARM Template 2</b>

![ARM Template](https://i.imgur.com/2Kktm4N.png)

<b>Creating Resource Group</b>

![Resource Group](https://i.imgur.com/CqGrf5y.png)

## Part 2: Creating the Azure Firewall

In this phase, Azure Firewall used to manage network traffic is deployed within the resource group. In addition, the VM and Private IP are configured and placed into a region.

The configurations used to accomplish this include: 

-	Azure Firewall
-	Virtual Machine

<b>Firewall Creation</b>

![Firewall 1](https://i.imgur.com/T8p9iEs.png)

<b>Firewall 2</b>

![Firewall 2](https://i.imgur.com/5Dx67yQ.png)

<b>List of Network Resources</b>
![Network Resources Deployed](https://i.imgur.com/HRc4hEg.png)

## Part 3: Create a Default Route

In this phase, a default route is configured for one of the network subnet workloads. This will direct the outbound traffic through the firewall. This is accomplished by linking the firewall route and subnet. 

The configurations used to accomplish this include: 

-	Default Routes
-	Firewall Route Configuration

<b>Route Table</b>

![Route Table 2]( https://i.imgur.com/pbo3IZS.png)

<b>Configuring Firewall Route</b>

![Route Table 2]( https://i.imgur.com/RNDNKVq.png)

## Part 4: Configuring Application and Network Rule

In this phase, an application rule is applied to control the outbound traffic to a specific destination, and a network rule is applied to permits outbound access to two IP addresses on DNS (port 53).

The configurations used to accomplish this include: 

-	Application Rule

<b>Application Rule</b>
![Application Rule](https://i.imgur.com/yZWk0IK.png)

<b>Network Rule 1</b>
![Network Rule 1](https://i.imgur.com/YyveoW4.png)

<b>Network Rule 2</b>
![Network Rule 2](https://i.imgur.com/f5iz1fP.png)


## Part 5: Configuring Virtual Machine DNS Servers

In this phase, the DNS servers are configured for primary and secondary DNS access to the VM. The DNS servers are referenced via the network rule IPs.

The configurations used to accomplish this include: 

-	DNS Server Configuration

<b>DNS Server</b>
![DNS Servers]( https://i.imgur.com/OLhNxvF.png)


## Part 6: Testing the Firewall Using RDP

In this phase, the firewall rules and network routes are tested using RDP. The RDP file is downloaded onto the host machine and credentials are used to access the VM created during deployment. 

The route rules are tested by editing the IE Enhanced Security Configuration on the server and launching a web browser in the VM and attempting to access a website. The firewall rules will only permit access to specified sites.

The configurations used to accomplish this include: 

-	RDP

<b>RDP</b>

![RDP]( https://i.imgur.com/wJN5vfj.png)

<b>Launching RDP File</b>

![Launching RDP File from Host 1]( https://i.imgur.com/HxPfvxm.png)





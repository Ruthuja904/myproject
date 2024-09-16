# myproject
**Brain DIseases** is a website that The brain is the most complex part of the human body. This three-pound organ is the seat of intelligence, interpreter of the senses, initiator of body movement, and controller of behavior. Lying in its bony shell and washed by protective fluid, the brain is the source of all the qualities that define our humanity. The site aims to simplify the decision-making process by providing users to get better treatment for brain related diseases.

This project demonstrates the deployment of **Brain Diseases** using Azure's ARM templates and load balancing across two Virtual Machines(VMs) in different zones for high availability and scalability.

**Problem Statement**    

Your brain is your body’s control center. It’s part of the nervous system, which also includes the spinal cord and a large network of nerves and neurons. Together, the nervous system controls everything from your senses to the muscles throughout your body.

When your brain is damaged, it can affect many different things, including your memory, your sensation, and even your personality. Brain disorders include any conditions or disabilities that affect your brain. This includes conditions that are caused by:

Illness Genetics Traumatic injury

**Project Goals**

1.Deploy the ** Brain - Diseases ** website on Azure using ARM templates.
2.Set up a Virtual Network (VNet) with two Subnets and a Network Security Group (NSG).
3.Use a Load Balancer to distribute traffic between two VMs located in different availability zones.
4.Host the static website on these VMs and make it accessible via the load balancer's frontend IP.

**Technologies and Azure Services Used**

1.**Azure CLI**: Used to create the resource group and Virtual Network.
2.**ARM Templates**: Automated the creation of VNet, subnets, and NSG.
3.**Azure Virtual Machines (VMs)**: Hosted the Sitara-Hotel website.
4.**Azure Load Balancer**: Distributed the traffic between two VMs to ensure high availability.
5.**Nginx**: Used as a web server on both VMs to serve the static content.
6.**Git**: Cloned the website from GitHub onto the VMs using a custom script.
7.**Custom Script Extension**: Used to automatically configure the VMs upon deployment.

**Project Steps**

1.**Website Development**

**Brain - Diseases**: A static website allowing users to book doctor's appointment for brain diseases and pay for appointmentcharges online.


2.**Deploying the Website on GitHub**

Frontend of **Brain - Diseases** was uploaded to a public GitHub repository: 

3.**Azure Deployment Using ARM Templates**

1.**Resource Group**: Created using Azure CLI to hold all the resources.
2.**Virtual Network (VNet)**: Set up using an ARM template, which included two subnets for distributing the VMs.
3.**Network Security Group (NSG)**: Applied inbound rules to allow traffic on ports 22 (SSH) and 80 (HTTP).


4.**Virtual Machines Setup**

**VM 1**: Created in Availability Zone 1 using Azure Portal. Configured with:
-Custom Script Extension to clone the website from GitHub.
-Networking settings to connect to the VNet and assigned Subnet.


Custom Script:

#!/bin/bash
sudo apt update
sudo apt install nginx git -y
cd /tmp && git clone https://https://github.com/Ruthuja904/myproject/edit/main/README.md
sudo rm -rf /var/www/html/index.nginx-debian.html
sudo cp -r /tmp/mysitee/* /var/www/html/


VM 2: Created in Availability Zone 2 with the same configuration as VM 1.



















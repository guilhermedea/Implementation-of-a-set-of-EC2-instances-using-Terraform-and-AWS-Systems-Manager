# Implementation of a set of EC2 instances using Terraform and AWS Systems Manager
![picture with the words Cloud Project and the icons for the services used](https://miro.medium.com/v2/resize:fit:720/format:webp/0*VIHlo2__EsvElB78.jpg)

In this project based on a real-world scenario, I acted as DevSecOps Engineer, and I deployed a set of EC2 instances and infrastructure in an automated way using 
Terraform (infrastructure as code — IaC). Also, it was necessary to install a specific security agent on all these instances in an automated way.

Once I provisioned the infrastructure, AWS System Manager and its component Command Run were used to install the security agents in an automated way. I used the 
Amazon Simple Notification Service — SNS to send an email informing the whole process status.

![Picture with words Solution Architecture and a graph showing the project](https://miro.medium.com/v2/resize:fit:720/format:webp/0*qBjwiDK4xQIMvJaC.jpg)

Terraform is an amazing tool, capable of provisioning multiple structures in multiple cloud providers at the same time. I already knew this tool from the 
The Cloud Bootcamp’s Cloud Immersion, and I was fascinated by it’s potential. I added the Terraform files carrying the necessary instructions for this project’s
structure and uploaded it to AWS’s Cloud Shell, executing Terraform after that. In a matter of minutes, the architecture was ready, running with the correct 
configurations, exactly as it was on the Terraform file instructions.

![A AWS CloudShell running Terraform](https://miro.medium.com/v2/resize:fit:720/format:webp/0*AYpUGZIMrS2C2tMH.jpeg)

To correctly run the notification system, I had to create a notification topic on Amazon Simple Notification Service (SNS) and subscribe it using my personal
e-mail to get the notifications. Also, to allow System Manager to use the SNS, it was needed to create a role on IAM with the correct permissions access.

With the notification structure ready, I proceed to use Systems Manager, a very powerful AWS tool to manage multiples virtual machines using a unified interface. 
The process to create and manage a fleet it’s very quick and easy. In less than 15 minutes, both Terraform created virtual machines were already 
being managed by Systems Manager.

![AWS Systems Manager dashboard](https://miro.medium.com/v2/resize:fit:720/format:webp/0*d9ph_0qFYLOnphyJ.jpeg)

To validate the Systems Manager use on this project, a script was created, which installed and verified a test security agent. The script had download instructions, 
installation and checks. Using Systems Manager, the process on both machines was made one time only, trought the management dashboard. If this was handy using only
two machines, imagine using it on a fleet of 100s or 1000s machines!

This was a very cool hands-on project. Terraform is a powerful tool to create architectures, and Systems Manager makes easy to manage multiple machines, 
something essential when handling security in cloud projects.



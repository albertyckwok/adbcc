# Access Cloud Resource

## Overview

In order to do anything, you need to gain access to the data center. The method for accessing resources are depended on where the resource are located and the security policy mandated by each company.

When working in the cloud, there are often times when your servers and services are not exposed to the public internet. The Oracle Cloud Infrastructure (../../exacs/labs/OCI) Database cloud service is an example of a service that is usually only accessible through private networks. It is best to keep it siloed away from the internet to help protect your data from potential attacks and vulnerabilities. It’s a good practice to limit resource exposure as much as possible, but at some point, you’ll likely want to connect to those resources. In this lab, we will show you different ways to access cloud resources.

## Tasks

The following are a few ways to access to cloud resources depending on where the resources are located. The first 3 are the best as they are cloud services, i.e. out-of-box, on-demand, scale automatically as needed, simplest to use and support.
1. [OCI Secure Desktop service (OSD)](../../exacs/labs/osdAccess.html) is the most comprehesive. It provides both GUI and text terminal access to private resource with any browser.
2. [OCI cloud shell](../../exacs/labs/connect-dbs-ocishell.html) is the simplest if all you need is text terminal basic access. It comes with the OCI UI/control plane without any additional requirement.
3. [OCI Bastion Service](../../exacs/labs/bastionService.html) allows secure access to resource with minimal network require that can tolerate network with long/high latency.
4. [Standard SSH bastion Host](../../exacs/labs/bastionHost.html) is most flexible that support all standard SSH features.
5. VPN (../../exacs/labs/Virtual Private Network) for both site to site and client to site that extend the private network to your site and desktop client. This requires additional setup for both customer.
6. [Access OSC data center](accessOSC.md) provides direct access to OSC data center that the resource such as ExaCC is located.

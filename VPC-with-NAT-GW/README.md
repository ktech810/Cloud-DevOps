
Here I'll be implementing a highly-available, regionally resilient NAT GW solution within this custom VPC.

I'll be demonstrating:

<li>3 NAT Gateways</li>
<li>Route tables</li>
<li>Default routes with the NAT GW as a target</li>
<li>Associate those route tables with the 3 subnets in AZ A, B and C.</li>

<p></p>
<p></p>

I'll be using a one click deployment link that will create an entire infrastructure stack used for this lab. This stack does not include any NAT GWs, Route tables or default routes. Those are what I will implement in this lab.

<p></p>

![AWSstackComplete](https://github.com/user-attachments/assets/ae885d6b-8451-45dc-80f0-e38e848d02bb)

<p></p>

We have an EC2 instance thats deployed in the <b>Application A Subnet</b>, which is a private subnet that does not have a public IPv4 address. I'll be connecting into it via session manager.

<p></p>

![EC2PreConnect](https://github.com/user-attachments/assets/0901342c-c919-4db0-a583-421b895d49e6)

<p></p>

If we try pinging any IP address (8.8.8.8), we'll notice that it cannot resolve any host because it currently does not have any public internet connectivity.

![EC2PostConnect](https://github.com/user-attachments/assets/3359e804-5ebf-491e-8829-23de3d5ed78f)

<p></p>

So at this point we'll need to deploy our NAT GWs which will provide our private EC2 instances with connectivity to the public IPv4 internet. We'll need to deploy a NAT GW into each of the 3 subnets (A,B,C)

<p></p>

![NATGWA](https://github.com/user-attachments/assets/01ae7420-bca1-4218-9f01-6f6bb537a688)

<p></p>

![NATGWA2](https://github.com/user-attachments/assets/0ece3041-7df6-48b4-8139-cc431fb7313b)

<p></p>

Until I have all 3 NAT GW built and available

<p></p>

![AllNATDONE](https://github.com/user-attachments/assets/5a5e6f75-6c04-46ea-be2d-f4e5402ef41a)

<p></p>

What we need to do now is configure routing so that private EC2 instances can communicate via the NAT GWs. I'm going to create a Route table for each of the 3 Availability Zones.

<p></p>

![RTA1](https://github.com/user-attachments/assets/4de9f131-b5f1-4797-827a-d05c80294ed3)

<p></p>

![RTA2](https://github.com/user-attachments/assets/359a0714-4ea4-49f5-bbec-1b44e495c6c9)

<p></p>

Until we have Route-tables built for all 3 of Availability zones.

<p></p>

![ALLRTDONE](https://github.com/user-attachments/assets/c7d9b96f-3df7-4a76-8069-c4eeafe0a6c4)

So now we need to create a default route within each of these route tables, which will then point at the NAT GW in the same availability zone.

<p></p>

Here I'm creating a default route for the Route-table in Availability Zone A

![DefRouteA](https://github.com/user-attachments/assets/aca4d156-6e42-4efc-a0f5-f8a8a14d8f4c)

And as we can see have a default route for AZ A. 

![DEFrouteAhighlight](https://github.com/user-attachments/assets/e3bed170-39d3-420a-8171-185cf9bce459)

We want to repeat this for each of the Availability zones.

Lastly we'll need to associate each of the Route-tables with all the same subnets inside that same AZ. This is how it looks for AZ A, we'll want to repeat this for AZ B and C as well.

![SubnetAssoA](https://github.com/user-attachments/assets/459a071b-a2c5-4455-b6bc-665cefedf7ec)



NOW with all this configured, if we go back to our EC2 instance from the beginning, we should be able to ping 8.8.8.8. This is because we now have a NAT GW providing service to each of the private subnets in all of the 3 availability zones.

![SuccessPing](https://github.com/user-attachments/assets/8ccccf4e-f2ff-4b6a-81ef-62ad71216440)



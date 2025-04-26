I've implemented a Multi-tier-VPC Subnet within my AWS environment

I built a multi-tier custom VPC configured to use the IP address range of the US-east-1 region - 10.16.0.0/16. Inside the VPC there will be space for 4 tiers running in 4 AZs for a total of 16 possible subnets. The four tiers will be Reserved, Database, Application and Web but only 3 AZs, A, B, and C.

I also created an Internet GW to give resources in the VPC public access. I created a NAT GWs to give private instances outgoing only access.

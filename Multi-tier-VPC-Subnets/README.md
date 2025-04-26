I've implemented a Multi-tier-VPC Subnet within my AWS environment

I built a multi-tier custom VPC configured to use the IP address range of the US-east-1 region - 10.16.0.0/16. Inside the VPC there will be space for 4 tiers running in 4 AZs for a total of 16 possible subnets. The four tiers will be Reserved, Database, Application and Web but only 3 AZs, A, B, and C.

I also created an Internet GW to give resources in the VPC public access. I created a NAT GWs to give private instances outgoing only access.


The following below is a list of all the details of the subnets I used to create my custom VPC.

We have 4 subnets: sn-reserved, sn-db, sn-app, and sn-web across 3 AZs, A, B and C.

sn-reserved-A 10.16.0.0/20 AZA IPv6 00
sn-db-A 10.16.16.0/20 AZA IPv6 01
sn-app-A 10.16.32.0/20 AZA IPv6 02
sn-web-A 10.16.48.0/20 AZA IPv6 03

sn-reserved-B 10.16.64.0/20 AZB IPv6 04
sn-db-B 10.16.80.0/20 AZB IPv6 05
sn-app-B 10.16.96.0/20 AZB IPv6 06
sn-web-B 10.16.112.0/20 AZB IPv6 07

sn-reserved-C 10.16.128.0/20 AZC IPv6 08
sn-db-C 10.16.144.0/20 AZC IPv6 09
sn-app-C 10.16.160.0/20 AZC IPv6 0A
sn-web-C 10.16.176.0/20 AZC IPv6 0B

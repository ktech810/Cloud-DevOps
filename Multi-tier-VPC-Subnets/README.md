I've built a multi-tier custom VPC subnet configured to use the IP address range of the US-east-1 region - 10.16.0.0/16. Inside the VPC there will be space for 4 tiers running in 4 AZs for a total of 16 possible subnets. The four tiers will be Reserved, Database, Application and Web but only 3 AZs, A, B, and C will be used. I'm not accounting for the reserved AZ in my lab.

---

<b><h4>The following below is a list of all the IPv4 and IPv6 details of the subnets I used to create my custom VPC.</b></h4>


We have 4 subnets: <b>sn-reserved</b>, <b>sn-db</b>, <b>sn-app</b>, and <b>sn-web</b> for each of the 3 AZs, A, B and C.

- sn-reserved-A 10.16.0.0/20 AZA IPv6 00
- sn-db-A 10.16.16.0/20 AZA IPv6 01
- sn-app-A 10.16.32.0/20 AZA IPv6 02
- sn-web-A 10.16.48.0/20 AZA IPv6 03
----
- sn-reserved-B 10.16.64.0/20 AZB IPv6 04
- sn-db-B 10.16.80.0/20 AZB IPv6 05
- sn-app-B 10.16.96.0/20 AZB IPv6 06
- sn-web-B 10.16.112.0/20 AZB IPv6 07
----
- sn-reserved-C 10.16.128.0/20 AZC IPv6 08
- sn-db-C 10.16.144.0/20 AZC IPv6 09
- sn-app-C 10.16.160.0/20 AZC IPv6 0A
- sn-web-C 10.16.176.0/20 AZC IPv6 0B
---
Within the VPC I created a subnet for each tier:

<h3>The first is for AZ A</h3>

![SN-Reserved-A](https://github.com/user-attachments/assets/92efb0a2-6cf1-4d2f-b29a-c7d4d0cf2268)

![SN-DB-A](https://github.com/user-attachments/assets/01ca8d99-685d-4a2d-b09b-0ae710530bb1)

![SN-APP-A](https://github.com/user-attachments/assets/53c1adbc-0d72-4275-b0b2-9aa34cbd9cff)

![SN-WEB-A](https://github.com/user-attachments/assets/d0a9f367-709a-418d-9f8d-8df8c860a4af)

![SN-A-Created](https://github.com/user-attachments/assets/202d7ea9-b646-4734-8a0e-77a95c80f7b8)

<h3>Then for AZ B</h3>

![SN-B-Created](https://github.com/user-attachments/assets/97a5f94f-5c6f-43df-9fb7-d85fabc93743)

<h3>Then for AZ C</h3>

![SN-C-Created](https://github.com/user-attachments/assets/25ee77dd-ca21-4c33-b881-681cad000e8a)

<h3>until I have a total of 12 subnets created, not including the 6 default ones that AWS provides.</h3>

![SN-ALL-Created](https://github.com/user-attachments/assets/a2a63c8a-5471-4985-8ae6-8f1ab25fd287)



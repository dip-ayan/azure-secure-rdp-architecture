# azure-secure-rdp-architecture
Implemented DNAT rules, UDR, NSG, and internal load balancing to protect VMs from public exposure while enabling RDP through Azure Firewall.

Project Summary:
Designed and implemented a scalable and secure Azure network architecture to enable Remote Desktop Protocol (RDP) access to virtual machines without exposing any public IPs.
The solution is based upon Azure Firewall, Internal Load Balancer, Network Security Groups (NSGs), and User Defined Routes (UDRs) to ensure centralized control, visibility, and protection for inbound and outbound traffic.

Architecture Overview:

Azure Firewall :
Acts as the primary entry point with a public IP. Configured DNAT rules to translate incoming RDP requests from the internet to the internal Load Balancer.

Internal Load Balancer (ILB):
Distributes RDP traffic to backend virtual machines within the private subnet, ensuring no direct exposure to the internet.

Backend Virtual Machines (VMs):
Hosted in a private subnet without public IPs. NSGs configured to allow RDP traffic only from the Firewall subnet for tight security.

Network Security Groups (NSGs):
Enforced least-privilege inbound rules, allowing access solely from the Firewall’s private IP range.

User Defined Routes (UDRs):
Configured to route all outbound traffic from the backend subnet through the Azure Firewall.

Outcome:

 1.Achieved secure, controlled RDP connectivity without exposing backend VMs publicly.
 2.Architecture easily extendable to include Web or Application tiers with the same security baseline.



 





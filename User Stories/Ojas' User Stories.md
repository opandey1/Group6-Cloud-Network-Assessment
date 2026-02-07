**User Story 1: Network Topology Visualization**
	• As a Network Analyst,
	• I want to create a detailed high-level diagram of our 3-Tier VPC architecture,
	• So that the team can visually identify all subnets, gateways, and availability zones.
✅ Acceptance Criteria:
	• Diagram clearly shows 3 distinct tiers: Web, App, and Data.
	• Diagram includes all key components: Internet Gateway (IGW), NAT Gateways, and Application Load Balancers (ALB).
	• Availability Zones (AZ-A and AZ-B) are visually distinct to demonstrate high availability.

**User Story 2: Segmentation Strategy Analysis**
	• As a Security Architect,
	• I want to document the isolation boundaries between the Public, Private, and Data tiers,
	• So that I can verify that no direct path exists from the Internet to the Database.
✅ Acceptance Criteria:
	• Verification that the Data Tier has no route to the Internet Gateway.
	• Documentation confirms App Tier only accepts inbound traffic from the Web Tier (ALB).
	• Comparison table created showing specific "Inbound/Outbound" rules for each tier.

**User Story 3: Egress Traffic Security Review**
	• As a Network Defense Analyst,
	• I want to analyze the traffic flow for outbound updates (patching) via the NAT Gateway,
	• So that I can ensure private instances can update without accepting unsolicited inbound connections.
✅ Acceptance Criteria:
	• The "Traffic Flow" section describes the path: Private Instance -> Private Route Table -> NAT Gateway -> Internet.
	• Analysis explains how the NAT Gateway drops unsolicited inbound traffic.
	• Risks of unmonitored egress (e.g., data exfiltration) are identified.

**User Story 4: Security Boundary Comparison**
	• As a Compliance Auditor,
	• I want to compare the roles of Network ACLs (NACLs) versus Security Groups in our architecture,
	• So that I can demonstrate defense-in-depth and identify potential misconfigurations.
✅ Acceptance Criteria:
	• Report explains the difference between Stateless (NACL) and Stateful (Security Group) filtering.
	• Common pitfalls, such as "Ephemeral Port Issues" with NACLs, are documented.
    Documentation clarifies that Security Groups act as the primary "Distributed Firewall" for instances.

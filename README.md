# vpc-3layers-multi-region
A AWS template to make a vpc 3 layers and multiregion
Parameters
ClassB: A Class B number for the VPC, used to define the CIDR block.
CustomerAlias: An alias for the customer, used in the resource tags.
CenterAccountId: The customer's central account ID, with a default value.
Resources
VPC: Creates a VPC with a CIDR block based on the ClassB parameter. It also enables DNS support and DNS hostnames.
InternetGateway: Creates an Internet Gateway and attaches it to the VPC.
Subnets:
Public Subnets: Three public subnets, each in a different availability zone, with public IP addresses enabled.
Private Subnets: Three private subnets in different availability zones.
Intra Subnets: Three internal subnets, also in different availability zones.
RouteTables: Creates route tables for the public, private, and internal subnets.
RouteTableAssociations: Associates each subnet with the corresponding route table.
RouteTablePublicInternetRoute: Defines a route in the public route table for internet traffic via the Internet Gateway.
Outputs
Provides several outputs exporting important information:

TemplateID: Identifier of the template.
AZs: Number of availability zones used.
AZA, AZB, AZC: The specific availability zones.
ClassB: The value of the ClassB parameter.
VpcId: The ID of the created VPC.
SubnetsPublic, SubnetsPrivate, SubnetsIntra: Lists of the public, private, and internal subnets.
RouteTables: IDs of the public, private, and internal route tables.
Individual Subnets: IDs of each created subnet.
CustomerAlias: Customer alias used.

Overview
The template is designed to create a secure and distributed network infrastructure across multiple AWS regions and availability zones. This type of setup is ideal for applications requiring high availability and workload separation (e.g., public front-end, private back-end, and internal subnets).
This code is useful for automating the creation of a complex network infrastructure in AWS, ensuring that all necessary components are correctly configured and follow a consistent structure based on the parameters provided by the user.

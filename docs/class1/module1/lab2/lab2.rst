Step 2: VPC Requirements
----------------------------------------------


 https://support.f5.com/kb/en-us/products/big-iq-centralized-mgmt/manuals/product/big-iq-centralized-management-and-amazon-web-services-setup-6-0-0/2.html#guid-0fd6defe-1e5b-4414-bd5b-674a1630b828

IAM user accounts (optional but not required)

Key pair (required)
	Per AWS best practice, this is required to get ssh access to the instance after boot. After login, you can change the admin password for access to the GUI

**VPC**

Single or Multi Region is supported

Management subnet (public)
	For BIG-IQ GUI access, data sync between Primary/Secondary
Internal subnet (private)
	For Elasticsearch Cluster traffic between BIG-IQ CM and BIG-IQ DCD (logging node)
	For BIG-IP device discovery, management, monitoring
Security group configuration
	Group1= allow-only-ssh-https-ping
	Group2= allow-all-traffic
Internet gateway
	If you cannot allow internet access, you will need to do manual activation for BIG-IQ and BIG-IP pool licenses
Route Table configuration
	To allow access to internet for management and external subnets

Provision BIG-IQ (AWS)
==============================================================

**Description:**

In this lab, we will deploy both BIG-IQ CM and DCD in AWS cloud. Refer to below AskF5 link if you need further details. 

`AskF5 Reference <https://support.f5.com/kb/en-us/products/big-iq-centralized-mgmt/manuals/product/big-iq-centralized-management-and-amazon-web-services-setup-6-0-0/2.html#guid-0fd6defe-1e5b-4414-bd5b-674a1630b828>`__


Step 1: AWS VPC Requirements
----------------------------------------------

Before you deploy BIG-IQ in AWS, ensure that you meet below requirements:

- An active AWS account
- Access to the AWS Marketplace
- Valid BIG-IQ CM and BIG-IQ DCD registration keys (Contact your F5 Sales representative for this)

  ..NOTE:: 
    Single or Multi Region is supported

#. IAM user accounts (optional, not required)
#. Key pair (required): `AWS Reference <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html>`__
   
   .. IMPORTANT::
      Per AWS best practice, this is required to get ssh access to the instance after boot. After login, you can change the admin password for access to the GUI

#. Management subnet (public)
	For BIG-IQ GUI access, data sync between Primary/Secondary
#. External subnet (public)
   - For Elasticsearch Cluster traffic between BIG-IQ CM and BIG-IQ DCD (logging node)
   - For BIG-IP device discovery, management, monitoring
#. Security group configuration. Configure your security group so that it meets below criteria:
   - Criteria 1 = **allow-only-ssh-https** from the source IP of your location for management access
   - Criteria 2 = **allow-all-traffic** from the internal AWS subnet 10.0.0.0/16 for traffic between BIG-IQ devices
#. Internet gateway (for initial BIG-IQ activation)
   - If you cannot allow internet access, you will need to do manual activation for BIG-IQ and BIG-IP pool licenses
#. Route Table configuration (association)
   - To allow access to internet for management and external subnets


Step 2: Launch Instance
----------------------------------------------

Recommended Instance Type:  `m4.xlarge (EBS)
<https://support.f5.com/kb/en-us/products/big-iq-centralized-mgmt/manuals/product/big-iq-centralized-management-and-amazon-web-services-setup-6-0-0/1.html#guid-bd42a26b-9fa6-4127-88ab-fe5ab06bd3c2>`__


Required Network Interfaces:  2

**AWS Marketplace**

Follow below steps to deploy **2** BIG-IQ CM devices. You can repeat these same steps to deploy your BIG-IQ DCD device(s). 

.. IMPORTANT::
   DCD is required to use analytics, application dashboard, and other visualization features. 

#. Search using keywords **F5 BIG-IQ** 
    Note that **F5 BIG-IQ Virtual Edition** and **F5 BIG-IP Cloud Edition** deploy the same instance of BIG-IQ Centralized Manager. 
    
   |lab-1-1|

   .. NOTE:: Currently only BYOL is available in AWS
    
   .. ATTENTION::Make sure to accept EULA when launching for first time
#. Click Continue

   |lab-1-2|

#. Select m4.xlarge, click Next: Configure Instance Details

   |lab-1-3|

#. Enter in **2** for number of instances to provision Primary and Secondary BIG-IQ CM devices. Select your VPC and then management subnet. 

   |lab-1-4|

#. Launch with 2 network interfaces. Select the External subnet for the additional NIC. Click Review and Launch

   |lab-1-5|

#. For storage size, you can set it to 500GB. Select General Purpose SSD and click Next: Add Tags

   |lab-1-6|

#. Add tags as necessary

   |lab-1-7|

#. Select the existing security group you created earlier, then click Review and Launch

   |lab-1-8|

#. Click Launch

   |lab-1-9|

#. Select the existing key pair you created earlier, then click Launch Instances

   |lab-1-10|

#. Associate EIP to primary IP of the management ENI
#. Log in via SSH to the EIP. Use public key authentication and your key that you specified when launching the instances
#. Change admin password so you can log into GUI
  - ``tmsh modify auth password admin``
  - ``tmsh save sys config``


.. |lab-1-1| image:: images/lab-1-1.png
.. |lab-1-2| image:: images/lab-1-2.png
.. |lab-1-3| image:: images/lab-1-3.png
.. |lab-1-4| image:: images/lab-1-4.png
.. |lab-1-5| image:: images/lab-1-5.png
.. |lab-1-6| image:: images/lab-1-6.png
.. |lab-1-7| image:: images/lab-1-7.png
.. |lab-1-8| image:: images/lab-1-8.png
.. |lab-1-9| image:: images/lab-1-9.png
.. |lab-1-10| image:: images/lab-1-10.png


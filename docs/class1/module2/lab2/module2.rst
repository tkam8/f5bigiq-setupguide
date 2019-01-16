BIG-IQ Setup Wizard (AWS)
==============================================================

**Description:**

In this lab, we will complete the setup wizard for BIG-IQ CM and DCD in AWS cloud. Refer to below AskF5 link if you need further details. 

`AskF5 Reference https://support.f5.com/kb/en-us/products/big-iq-centralized-mgmt/manuals/product/big-iq-centralized-management-plan-implement-deploy-6-1-0/03.html#guid-37a1f866-5f56-45bb-914f-f24dbd3348d0>`__


Step 1: Setup Wizard 
----------------------------------------------

Follow below steps to setup your BIG-IQ CM and DCD devices. The only difference will be step (2) below.


#. When you first log into the BIG-IQ, you must complete the setup wizard. The first step is licensing. Enter in the Base Registration Key for your BIG-IQ CM, accept EULA and activate. 

   .. NOTE::
      If you cannot configure Internet access, use Manual activation

   |lab-1-1|

#. Select "BIG-IQ Central Management" for CM. Select "BIG-IQ Data Collection Device" when configuring your logging node

   |lab-1-2|

#. In AWS, the Hostname, Management Port IP Address, Management Port Route are automatically set by DHCP. Select Self-IP for discovery address (recommended) and enter in the internal IP assigned to your second network interface using the appropriate netmask

   |lab-1-3|

#. Configure your Time Server using Amazon Time Sync Service and set your time zone 

   |lab-1-4|

#. Set Master key: <Long password>

   |lab-1-5|

#. Skip changing the password for admin, just set root

   |lab-1-6|

#. Confirm configuration and Launch

   |lab-1-7|

.. |lab-1-1| image:: images/lab-1-1.png
.. |lab-1-2| image:: images/lab-1-2.png
.. |lab-1-3| image:: images/lab-1-3.png
.. |lab-1-4| image:: images/lab-1-4.png
.. |lab-1-5| image:: images/lab-1-5.png
.. |lab-1-6| image:: images/lab-1-6.png
.. |lab-1-7| image:: images/lab-1-7.png
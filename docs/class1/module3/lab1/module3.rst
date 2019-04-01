High Availability (VMware and AWS) 
==============================================================

**Description**

In this lab, we will configure High Availability for BIG-IQ CM. Refer to below AskF5 link if you need further details. 

`AskF5 Reference <https://support.f5.com/kb/en-us/products/big-iq-centralized-mgmt/manuals/product/big-iq-centralized-management-plan-implement-deploy-6-1-0/04.html#ch-managing-a-big-iq-system>`__

Step 1:  High Availability
----------------------------------------------

For the high availability pair to synchronize properly, each system must be running the same BIG-IQ version, and the clocks on each system must be synchronized to within 60 seconds.

#. Click **System** > **BIG-IQ HA** > **Add Secondary** and enter in the secondary device connectivity information

   |lab-1-1|

   - Use self-ip of peer BIG-IQ
   - Enter in root password that you configured in the setup wizard (required)

#. Click **OK** to add the HA Peer Device 

   |lab-1-2|

This completes the BIG-IQ High Availability configuration. 

.. |lab-1-1| image:: images/lab-1-1.png
.. |lab-1-2| image:: images/lab-1-2.png
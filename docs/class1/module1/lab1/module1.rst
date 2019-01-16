Provision BIG-IQ (VMware)
==============================================================

**Description:**

This lab will deploy both BIG-IQ CM and DCD in VMware ESXi. Refer to below AskF5 link if you need further details. 

`AskF5 Reference <https://support.f5.com/kb/en-us/products/big-iq-centralized-mgmt/manuals/product/big-iq-centralized-management-and-vmware-setup-6-0-0.html>`__


Step 1: VMware ESXi Requirements
----------------------------------------------

The vSphere virtual machine guest environment for the BIG-IQ Virtual Edition (VE), at minimum, must include:

- 4 virtual CPUs
- 16 GB RAM
- Important: When you provision the amount of RAM allocated to the virtual machine, it must match the amount of reserve RAM.
- 1 VMXNET3 virtual network adapter
- 1 virtual network adapter
- At least 128GB disk
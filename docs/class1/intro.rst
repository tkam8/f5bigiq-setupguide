Overview
========

This document details the technical steps needed to set up BIG-IQ v7.0 for testing in a test environment. This guide assumes a small environment that requires high availability. 

Infrastructure
---------------

F5 BIG-IQ Centralized Management is a platform that
you use as a tool to help you manage BIG-IP devices and all of
their services (such as LTM, AFM, ASM, and
so forth), from one location. BIG-IQ can manage up to 600 (physical,
virtual, or vCMP) BIG-IP devices and handle licensing for up
to 5,000 unmanaged devices.

Using BIG-IQ helps you more efficiently manage your BIG-IP devices. That
means you and your co-workers don't have to log in to individual BIG-IP
systems to get your job done. Instead, you can discover, upgrade, deploy
policy changes, manage licenses, and more, from just one place.

From BIG-IQ, you can manage a variety of tasks from software updates to
health monitoring, and traffic to security. And because permissions for
users are role-based, you can limit access to just a few trusted
administrators to minimize downtime and potential security issues. You
can also allow users to view or edit only those BIG-IP objects that they
need to do their job.

An F5 BIG-IQ Centralized Management solution can
involve a number of different elements. The topology for these elements
depends on your needs, and on whether you include data collection
devices (DCDs) in your solution. A typical solution can include the
following elements:

-  BIG-IQ system(s)

-  BIG-IP devices

-  Data collection devices

-  Remote storage devices


.. NOTE::
	 We recommend that all work for this lab be performed from your local Web browser or from the windows jumphost. No installation with your local system is required.

**BIG-IQ Centralized Management system**

Using BIG-IQ Centralized Management, you can centrally manage your
BIG-IP devices, performing operations such as backups,
licensing, monitoring, and configuration management. And because access
to each area of BIG-IQ is role-based, you can limit access to users,
thus maximizing work flows while minimizing errors and potential
security issues.

**BIG-IP device**

A BIG-IP device runs a number of licensed components that are designed
around application availability, access control, and security solutions.
These components run on top of F5 TMOS. This custom
operating system is an event-driven operating system designed
specifically to inspect network and application traffic, and make
real-time decisions based on the configurations you provide. The BIG-IP
software runs on both hardware and virtualized environments.

**Data collection device**

A \ *data collection device* (DCD) is a specially provisioned BIG-IQ
system that you use to manage and store alerts, events, and statistical
data from one or more BIG-IP systems.

Configuration tasks on the BIG-IP system determine when and how alerts
or events are triggered on the client. The alerts or events are sent to
a data collection device in a BIG-IQ Centralized Management deployment,
and the BIG-IQ system retrieves them for your analysis. When you opt to
collect statistical data from the BIG-IP devices, the DCD periodically
retrieves those statistics from your devices, and then processes and
stores that data.

The group of data collection devices and BIG-IQ systems that work
together to store and manage your data are referred to as the \ *data
collection cluster*. The individual data collection devices are
generally referred to as \ *nodes*.

**Remote storage device**

You need a remote storage device only when your deployment includes a
data collection device (DCD) and you plan to store backups of your
events, alerts, and statistical data for disaster recovery requirements.
You also need remote storage so that you can retain this data when you
upgrade your software.

**Network environment for simple device management and configuration**

To deploy a simple device management and configuration environment, all
you need is one or more BIG-IQ systems and the
BIG-IP devices that you want to manage. The number of BIG-IQ
systems you need depends on how much redundancy your business requires.
A second system provides high availability failover capability.

The simple management and configuration solution uses a single
management network. The BIG-IQ system uses traffic on the management
network to do these things:

-  Enable bidirectional traffic between the BIG-IQ systems and the
   BIG-IP devices.

-  Enable traffic between the BIG-IQ systems. If you use a secondary
   high availability BIG-IQ system, this traffic keeps the state
   information synchronized.

-  Provide access to the BIG-IQ user interface. You can also use the
   management network to access the BIG-IQ system using SSH if you need
   to run manual commands.

Note: The number of devices of each type that will best meet your
company's needs depends on a number of factors. Refer to the \ *F5
BIG-IQ Centralized Management: Data Collection Device Sizing
Guide* on support.f5.com for details.


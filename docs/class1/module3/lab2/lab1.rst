Step 1: High Availability
----------------------------------------------


Reference:
<https://support.f5.com/kb/en-us/products/big-iq-centralized-mgmt/manuals/product/big-iq-centralized-management-plan-implement-deploy-6-1-0/04.html#ch-managing-a-big-iq-system>

#. Currently only for configuration sync, not automatic failover
#. SSL Certificate Verification (For post failover purpose)
   - Go to /config/httpd/conf/ssl.crt on primary and secondary and save the ssl.crt to local system
   - Import to BIG-IQ primary
   - Reference: <https://support.f5.com/csp/article/K52425065>
#. Setup HA
     ``tmsh modify sys db systemauth.disablerootlogin value false``
	``tmsh save sys config``
   - Use self-ip of peer BIG-IQ
   - Enter in root password (required)

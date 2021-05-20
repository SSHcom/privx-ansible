PrivX example deployment playbook / SSH Communications Security

This example configures a target host to use PrivX.
It configures OpenSSH to accept PrivX CA certificate and sends information about the host identity to PrivX server.

This playbook requires Ansible 1.2.

To deploy PrivX hosts with Ansible, please do the following:

1) Install PrivX server and create a new role called "web-developers"
Assign some users to the role.

2) Go to https://yourprivxserveraddress/privx/deployment/trusted-clients and add new Trusted Client

3) Download deploy.py for the trusted client and copy it to this directory

4) Modify privx_hosts file to contain your hosts

5) Copy your target host private key to privx_test.pem or change the filename in privx_hosts file

6) Run ansible

ansible-playbook -b -i privx_hosts privx_hosts.yml

Note that deploy.py makes changes to OpenSSH configuration, so it requires sudo access (-b flag)


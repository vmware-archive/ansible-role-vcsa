vcsa
=========

Deploys a VMware Platform Service Controller or vCenter Server Appliance using the ovftool

Requirements
------------

pyVmomi
pysphere

Role Variables
--------------

the_one_task_template
the_one_task
vcenter_host
vcenter_user
vcenter_password
vcenter_port
esx_hostname
esx_username
esx_password
esx_datastore
esx_network
appliance_thin_disk_mode
ip_family
time_tools_sync
ssh_enable
database_type
sso_domain_name
sso_site_name
sso_password
psc_appliance_vcenter_name
vcsa_appliance_vcenter_name
psc_appliance_domain_name
vcsa_appliance_domain_name
psc_appliance_root_password
vcsa_appliance_root_password
appliance_deployment_option
psc_appliance_ip_address
psc_appliance_ip_prefix
psc_appliance_ip_gw
psc_appliance_dns_servers
vcsa_appliance_ip_address
vcsa_appliance_ip_prefix
vcsa_appliance_ip_gw
vcsa_appliance_dns_servers
ovftool
iso
ova
mount_dir_path
ovftool_http_timeout

Dependencies
------------

Example Playbook
----------------

- name: Deploy a virtual machine via ovftool
  hosts: localhost
  gather_facts: false
  vars_files:
    - roles/vcsa/vars/main.yml
    - roles/vcsa/defaults/main.yml
  roles:
    - vcsa

License
-------



Author Information
------------------

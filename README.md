# ansible-role-vcsa

Deploys a VMware Platform Service Controller or vCenter Server Appliance (vcsa).
The PSC or vCSA is deployed is deployed into an ESXi host or vCenter Server
 referenced
using vars below.  The general use case would be to apply this role to a single host
that can reach the host the  vm will be deployed into.

*Hereafter either ESXi or vCenter Server will be called the **"host endpoint"***

*Hereafter either PSC or vCSA will be called the **"ova"***

# Requirements

* This role requires the molecule pip module (for testing only).
* To install the ova, you must have downloaded the vcsa ISO
 from vmware.com beforehand.  This ISO contains the **ova** we will deploy to the **host endpoint**
* The role must be run against a host with access to the **host endpoint**

# Role Variables

The following variables are required, but may have valid 
defaults in set in `defaults/main.yml`.



Note: A non-defaulted variable, download_site, must be set by a vars file
or by other mechanism prior to calling this role. The download_site must
provide a URL base (e.g., http://mysite.com/downloads)
from which the download files (e.g., ISO files or similar) may be obtained.
See the defaults/main.yml for the files of interest.

```
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
```

# Example Playbook

```yaml
- name: Deploy a virtual machine via ovftool
  hosts: localhost
  gather_facts: false
  vars_files:
    - roles/vcsa/vars/main.yml
    - roles/vcsa/defaults/main.yml
  roles:
    - vcsa
```

# License and Copyright

Copyright 2015 VMware, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

## Author Information

This role was created in 2015 by [Jake Dupuy / VMware](http://www.vmware.com/).

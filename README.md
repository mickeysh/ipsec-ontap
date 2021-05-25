# ONTAP IPSec Configuration

## Requirements
- You need to configure all the variables and hosts in the [hosts.yaml](hosts.yaml) file
- Install ansible on your workstation/server
- Install netapp.ontap ansible collection
```
ansible-gallaxy install collection netapp.ontap
```

### 1. Hosts
Update the list of hosts under ``ipsec`` group

### 2. IPSec Configureation Variables
``ipsec_target_cidr``: ONTAP target CIDR (dataLIF) (default: ``10.3.2.81/32``)\
``ipsec_source_cidr``: Servers source CIDR (default: ``10.3.2.0/24``)\
``ipsec_secret``: Preshared key (PSK) for client server config (default: ``wWTZINNo8kUCPVicZyDssX1qe6H8Rno/``\) 

> NOTE: You can generate a PSK key [here](https://cloud.google.com/network-connectivity/docs/vpn/how-to/generating-pre-shared-key)

### 3. ONTAP Configuration Variables
``ontap_api_interface``: ONTAP Cluster management interface (default: ``10.3.2.83``)\
``ontap_user``: ONTAP login user (default: ``admin``)\
``ontap_password``: ONTAP login password (default: ``Netapp1!``)

### 4. Server 
``ansible_connection``: Ansible connection method (default: ``ssh``)\
``ansible_user``: Ansible SSH login user (default: ``ubuntu``)\
``ansible_ssh_private_key_file``: SSH private key path (default: ``~/.ssh/google_compute_engine``)\
``ansible_python_interpreter``: Python interpreter path (default: ``/usr/bin/python3``)


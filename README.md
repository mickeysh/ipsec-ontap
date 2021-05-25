# ONTAP IPSec Configuration

## Variables

You need to configure all the variables in the [hosts.yaml](hosts.yaml) file

### 1. IPSec Configureation Variables
``ipsec_target_cidr``: ONTAP target CIDR (dataLIF) (default: ``10.3.2.81/32``)\
``ipsec_source_cidr``: Servers source CIDR (default: ``10.3.2.0/24``)\
``ipsec_secret``: Preshared key (PSK) for client server config (default: ``wWTZINNo8kUCPVicZyDssX1qe6H8Rno/``\) 
### 2. ONTAP Configuration Variables
``ontap_api_interface``: ONTAP Cluster management interface (default: ``10.3.2.83``)\
``ontap_user``: ONTAP login user (default: ``admin``)\
``ontap_password``: ONTAP login password (default: ``Netapp1!``)

### 3. Server 
ansible_connection: ssh
ansible_user: ubuntu
ansible_ssh_private_key_file: ~/.ssh/google_compute_engine
ansible_python_interpreter: /usr/bin/python3

You can generate a PSK key [here](https://cloud.google.com/network-connectivity/docs/vpn/how-to/generating-pre-shared-key)
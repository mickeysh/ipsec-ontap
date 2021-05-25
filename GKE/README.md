# Deploy IPSec for ONTAP on GKE Nodes

To deploy IPSec for ONTAP on GKE nodes you will need:
1. Prepare these parameter:
- ONPTAP DataLIF CIDR block (example: 10.3.2.81/32)
- GKE Node pool subnet CIDR block (exmaple: 10.3.2.0/24)
- Preshared Key (PSK)
> NOTE: You can generate a PSK key [here](https://cloud.google.com/network-connectivity/docs/vpn/how-to/generating-pre-shared-key)

2. Enable IPSec in your ONTAP cluster
```
security ipsec config modify -is-enabled true
```
3. Create an IPSec Policy
```
security ipsec policy create -vserver <your svm name> -name ipsec_test -local-ip-Subnets <your ontap datalif cidr> -remote-ip-subnets <your gke subnet cidr> -shared-key <your psk>
```
4. Update the 3 parameters in the [configmap.yml](configmap.yml)

5. Execute the DaemonSet in your GKE cluster using [daemonset.yml](daemonset.yml)
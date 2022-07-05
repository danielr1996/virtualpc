# virtualpc
bootstrap Arch linux with kvm/qemu and GPU passthrough

## installation
 > Ensure passwordless sudo is enabled, otherwise if you run ansible with `sudo` the current
 > user will be root instead of the current user and adding the current user to the `libvirt`
 > group will not work

 > If host networking (i.e. VMs get ip addresses from the same network as the host) is required
 > make sure to create a network bridge on the host: 
 > ```shell
 > ip link add name vmbridge type bridge
 > ip ink set vmbridge up
 > ip link set eno1 master vmbridge
 >```
 > And select "Network Source" "Bridge Device" and "Device Name" `vmbridge` in the VMs NIC 
```shell
ansible-playbook playbook.yaml
``` 
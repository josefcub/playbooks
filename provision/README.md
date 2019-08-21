# provisioning

VM Provisioning Playbook

This playbook does the initial provisioning of a CentOS 7 VM.  The script requires variables to be set before it is ran.  

 * __hostname__ is the hostname that will be assigned to the VM both internally and as the ansible inventory name.
 * __memory__ is specified in megabytes,
 * __cpus__ is the number of virtual CPUs,
 * __disk_size__ should be specified in gigabytes,
 * __group__ indicates which inventory group in /etc/ansible/hosts this vm will belong to.

These options can be configured in prov.yml or by using -e on the command line:

  * __kickstart_server__ is where the kickstart file is saved immediately prior to beginning installation.
  * __subnet_cidr__ is used to indicate which IP address pool to take an address from in IPAM
  * __domain__ the domain and TLD your guest's hostname will be attached to.
  
  Don't forget to add in your SSH key and librenms/PHPIPAM API keys!
  
Invocation Example:

     $ ansible-playbook ./prov.yml -e "hostname=docker" -e "memory=1024" -e "cpus=1" -e "disk_size=40" -e "group=docker"



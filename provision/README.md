# provisioning

VM Provisioning Playbook

This playbook does the initial provisioning of a CentOS 7 VM.  The script requires variables to be set before it is ran.  

 * __hostname__ is the hostname that will be assigned to the VM both internally and as the ansible inventory name.
 * __memory__ is specified in megabytes,
 * __cpus__ is the number of virtual CPUs,
 * __disk_size__ should be specified in gigabytes,
 * __group__ indicates which inventory group in /etc/ansible/hosts this vm will belong to.

Invocation Example:

     $ ansible-playbook ./prov.yml -e "hostname=docker" -e "memory=1024" -e "cpus=1" -e "disk_size=40" -e "group=docker"



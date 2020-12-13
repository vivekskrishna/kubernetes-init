# Kubernetes Cluster using Ansible
* Clone repository.
* Create multiple centos8 servers. One master and many worker. Use vagrant like [here](https://github.com/edib/many_vagrant_machines)
* assign the hostname and ip's on the newly booted centos servers
* Change the “ad_addr” in the env_variables file with the IP address of the Kubernetes master node.
* Run the following command to setup the Kubernetes Master node.


```
ansible-playbook setup_master_node.yml --extra-vars "ansible_sudo_pass=admin"
```
* Once the master node is ready, ansible script will automatically set up the worker nodes.
* Once the workers have joined the cluster, run the following command to check the status of the worker nodes.
* run below command from master node
```
kubectl get nodes
```

## Additional information
* The IP addresses of the workers and masters added to the /etc/hosts file on all workers and masters as part of the [prerequisites.yml](centos/playbooks/prerequisites.yml) playbook,
if necessary or in case of DNS issues make sure the addresses have been added to /etc/hosts file.

## Reference:
* https://medium.com/faun/how-to-create-your-own-kubernetes-cluster-using-ansible-7c6b5c031a5d


used https://github.com/ctienshi/kubernetes-ansible as a base and added some customization





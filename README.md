# cosbench-ansible

Description:
Automaticaly deploy cosbench and run predefined workloads on clients to test the Quobyte s3 server
Automaticaly deploy cosbench and run predefined workloads on Quobyte cluster nodes when no clients are availible
After the workloads have finished the result can be found in $HOME/cosbench/archive


Requirements:
- One or more Linux machines running Centos or Ubuntu with Internet access.
- Password less ssh key access to all driver nodes

Configuration:

1) Add the names and IP's for the nodes that will be running Cosbench to the inventory file, the first node should have both the controller and driver role the rest will only have the driver role.

2) Add the Quobyte Management API IP (do not add http://) plus port to the vars/cosbench_vars file. 
 (using default credentials)

3) Add the S3 endpoint domain name to the vars/cosbench_vars file.

4) Enter the IP's of the nodes that are running S3 in the vars/s3_nodes file. When testing through your own load-balancer provide the IP of the LB.
(make sure to use the fastest interface)

5) On the first node that will be running the controller and driver role install ansible and execute the playbook with the following command:
   ansible-playbook -i inventory cosbench.yaml

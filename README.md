# cosbench-ansible

Automaticaly deploy cosbench and run predefined workloads on clients to test the Quobyte s3 server
Automaticaly deploy cosbench and run predefined workloads on Quobyte cluster nodes when no clients are availible

After the workloads have run the result can be found in ~/cosbench/archive

Add the Quobyte Management API IP (do not add http://) plus port to the cosbench_vars file.
Add the S3 endpoint domain name to the cosbench_vars file.

 - Example content of cosbench_vars file -
vars/cosbench_vars.yaml:
mgmt_api: 172.16.78.111:7860
s3_endpoint: s3.skynet.local

Enter the IP's of the nodes that are running S3 in the s3_nodes file.
(make sure to use the fastest interface)

When testing through your own load-balancer provide the IP of the LB. 

 - Example content of s3_nodes
vars/s3_nodes:
172.16.78.111 
172.16.78.112
172.16.78.113
172.16.78.114 


# ubuntuk8scalm
These blueprints allow to create a K8s cluster using Ubuntu Cloud Image, following [Microsoft's guidelines for SQL Server Big Data Clusters on Ubuntu] (https://github.com/microsoft/sql-server-samples/tree/master/samples/features/sql-big-data-cluster/deployment/kubeadm/ubuntu).

The first one *(1-Ubuntu_Image_Server.json)* does the following:

  - Downloads Ubuntu Cloud Image
  - Expands it with additional 50 GB
  - Converts to qcow2 format to make it compatible with AHV
  - Creates an image server, that is used as image source for the second blueprint

Once deployed, open the second blueprint *(2_Ubuntu_K8s_Cloudimg.json)* and edit *DOWNLOADABLE IMAGE CONFIGURATION*. Modify the IP Address in the *Source URI* box, to match your already deployed image server settings. For instance:

http://10.42.99.54/images/ubuntu-16.04-server-cloudimg-amd64-disk1.qcow2

Modify the *Master_Node_Hostname, Worker_Nodes_Hostname* and *Domain* variables as required.

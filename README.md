# AWS-Create-an-Amazon-Redshift-Cluster
AWS Create an Amazon Redshift Cluster

Make sure your firewall, if you have one, has a port open you can use. Port 5439 is used by Amazon Redshift by default.

Log into the the AWS IAM console and select roles under access management in the left menu. Click the create role button.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/IAM_Roles_1.png)

Click on Redshift and then Redshift - Customizable. Click next:permissions.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/Redshift_Customizable.png)

Find and check the box for AmazonS3ReadOnlyAccess then click next:tags.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/AmazonS3ReadOnlyAccess.png)

Leave tags blank and click next:review. Create a role name and description then click create role.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/role_name_1.png)

Go into the role that you just created and take note of the Role ARN. It will be used when you use the copy command to load sample data from S3.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/Role_ARN_1.png)

Navigate to the Amazon Redshift console. Make sure your in the correct region. Click on create cluster.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/Create_Cluster_1.png)

Name the cluster. Choose dc2.large for the node tyoe in the comute optimized section. Choose 2 nodes.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/Cluster_Node_Size.png)



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

For the database port enter 5439. Create a master username and password.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/Database_Port.png)

In the Cluster permissions section select the IAM user you created and click add IAM role. Click create cluster.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/Cluster_Permissions.png)

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/example_cluster.png)

To use the query editor first make sure that the IAM user you plan to use has permission for the following AWS policies "AmazonRedshiftQueryEditor" and "AmazonRedshiftReadOnlyAccess"

In the Redshift console main page click on Editor in the left menu. Create a new connection and Choose the correct cluster. Enter the database name, the database user, and the password. Click on Connect to database.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/Connect_to_Database.png)

Choose public in the dropdown under select schema. Enter the code shown in the screenshot below in the editor and click run to create a new table.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/Data_Objects.png)

After it has completed press clear. Enter the code shown in the screenshot below in the editor and click run to add rows to the table.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/Add_rows.png)

After it has completed press clear. Enter the code shown in the screenshot below in the editor and click run to query the new table.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/select_shoes.png)

Scroll down to see the query results.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/Query_Results.png)

Click the Export dropdown to download query results.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/Export.png)

To load sample data from Amazon S3, run the following create table statements as shown in the following screenshots. Which will create tables.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/create-table_1.png)

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/create_table_2.png)

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/create_table_3.png)

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/redshift_tables.png)

Load data from Amazon S3 by using the COPY command. Create a folder in an S3 bucket, name it and save it.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/test_bucket_1.png)

Upload data to the new folder.

Navigate back to Redshift. Again, make sure the user has access to Redshift and S3. Enter the following code in the query editor and click run to copy users from S3. You must have your S3 bucket name, IAM role ARN, and AWS region.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/users_1.png)

Run the following with your information.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/pipe.png)

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/Pipe_2.png)

Run the following query to check the data.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/query_run.png)

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/schema_name.png)

Use the snapshot saved and plug it into the Redshift CloudFormation Template YAML file in cloud formation. You should be able to re-deploy from the snapshot so you don’t have to create the cluster again.

![alt text](https://github.com/doyle199/AWS-Create-an-Amazon-Redshift-Cluster/blob/master/snapshots.png)





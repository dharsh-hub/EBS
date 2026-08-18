# WORKING WITH EBS
### NAME: DHARSHINI S
### REGISTER NO : 212224100012
## AIM:
In this lab environment, access to AWS services and service actions might be restricted to the ones that are needed to complete the lab instructions. You might encounter errors if you attempt to access other services or perform actions beyond the ones that are described in this lab.

## OBJECTIVE:
Create an Amazon EBS volume *Attach and mount your volume to an EC2 instance *Create a snapshot of your volume *Create a new volume from your snapshot *Attach and mount the new volume to your EC2 instance

## Illustration:
### STEP 1:
In this step, you will create and attach an Amazon EBS volume to a new Amazon EC2 instance.You will see an existing volume that is being used by the Amazon EC2 instance. This volume has a size of 8 GiB, which makes it easy to distinguish from the volume you will create next, which will be 1 GiB in size.

<img width="1917" height="1078" alt="Screenshot 2026-08-18 092910" src="https://github.com/user-attachments/assets/f2c044fc-e72a-41da-a95e-f69104b38ef3" />


<img width="942" height="880" alt="image" src="https://github.com/user-attachments/assets/18f280e7-dc2c-42f0-b425-9c21959d7152" />


### STEP 2:
In this step, you will connect to the Lab EC2 instance using Session Manager.You can now attach your new volume to the Amazon EC2 instance.

<img width="954" height="878" alt="image" src="https://github.com/user-attachments/assets/d1df7132-de61-4756-bfc5-2ce9af9130b5" />


### STEP 3:
In this step, you will add the new volume to a Linux instance as an ext3 file system under the /mnt/data-store mount point.

<img width="948" height="880" alt="image" src="https://github.com/user-attachments/assets/7af198a9-5afa-4a85-a371-fc2b124a6d70" />

<img width="954" height="878" alt="image" src="https://github.com/user-attachments/assets/83e9847f-7218-44b3-92a2-429565d3806b" />

<img width="1906" height="1080" alt="Screenshot 2026-08-18 092331" src="https://github.com/user-attachments/assets/868c32e4-6b1d-49e4-8641-d99c17309c02" />



### STEP 4:
You can create any number of point-in-time, consistent snapshots from Amazon EBS volumes at any time. Amazon EBS snapshots are stored in Amazon S3 with high durability. New Amazon EBS volumes can be created out of snapshots for cloning or restoring backups. Amazon EBS snapshots can also be easily shared among AWS users or copied over AWS regions.


<img width="957" height="1078" alt="image" src="https://github.com/user-attachments/assets/2331851b-17cd-4518-95d8-efb17c8afd88" />

<img width="960" height="876" alt="image" src="https://github.com/user-attachments/assets/5e9be3a4-096f-49f8-abc8-292f60e50622" />


### STEP 5:

<img width="954" height="878" alt="image" src="https://github.com/user-attachments/assets/9ecca606-b74c-4efc-9e29-8b11a0eff974" />

## RESULT:
Successfully created, managed, and deleted an EBS bucket on AWS, demonstrating the ability to upload, access, and control objects within Amazon EBS.

# EBS
## NAME: DHARSHINI S
## REG NO: 212224100012
## Aim

To create and configure an Amazon Elastic Block Store (EBS) volume, attach and mount it to an Amazon EC2 instance, create a snapshot backup, and restore the snapshot to a new EBS volume.

## Algorithm / Steps

1. Create a new Amazon EBS volume with a size of 1 GiB.
2. Select the same Availability Zone as the EC2 instance.
3. Attach the EBS volume to the EC2 instance using `/dev/sdb`.
4. Connect to the EC2 instance using AWS Systems Manager Session Manager.
5. Check the available storage using `df -h`.
6. Create an `ext3` file system on the EBS volume.
7. Create the `/mnt/data-store` directory.
8. Mount the EBS volume to `/mnt/data-store`.
9. Configure `/etc/fstab` for automatic mounting.
10. Verify that the EBS volume is successfully mounted.
11. Create `file.txt` inside the mounted EBS volume.
12. Verify the contents of the created file.
13. Create an EBS snapshot named `My Snapshot`.
14. Delete `file.txt` from the original EBS volume.
15. Create a new EBS volume from the snapshot.
16. Attach the restored volume to the EC2 instance using `/dev/sdc`.
17. Create the `/mnt/data-store2` directory.
18. Mount the restored volume to `/mnt/data-store2`.
19. Verify that `file.txt` has been successfully restored.


## Program

### 1. Check Available Storage

```bash
df -h
```

### 2. Create an ext3 File System

```bash
sudo mkfs -t ext3 /dev/sdb
```

### 3. Create a Mount Directory

```bash
sudo mkdir /mnt/data-store
```

### 4. Mount the EBS Volume

```bash
sudo mount /dev/sdb /mnt/data-store
```

### 5. Configure Automatic Mounting

```bash
echo "/dev/sdb   /mnt/data-store ext3 defaults,noatime 1 2" | sudo tee -a /etc/fstab
```

### 6. View the File System Configuration

```bash
cat /etc/fstab
```

### 7. Verify the Mounted Volume

```bash
df -h
```

### 8. Create a File in the EBS Volume

```bash
sudo sh -c "echo some text has been written > /mnt/data-store/file.txt"
```

### 9. Read the File

```bash
cat /mnt/data-store/file.txt
```

### 10. Delete the File

```bash
sudo rm /mnt/data-store/file.txt
```

### 11. Verify File Deletion

```bash
ls /mnt/data-store/
```

### 12. Create a Mount Directory for the Restored Volume

```bash
sudo mkdir /mnt/data-store2
```

### 13. Mount the Restored EBS Volume

```bash
sudo mount /dev/sdc /mnt/data-store2
```

### 14. Verify Snapshot Restoration

```bash
ls /mnt/data-store2/
```

Expected output:

```text
file.txt
```

## Outputs

### Output 1: EBS Volume Created

The AWS EC2 Volumes page shows the newly created `My Volume` EBS volume with a size of 1 GiB.

<img width="1920" height="1200" alt="Screenshot 2026-08-03 160033" src="https://github.com/user-attachments/assets/5f5a3236-9d0a-4b9e-ba3a-4de0fec4002b" />


---


### Output 2: EBS Volume Mounted Successfully

The `df -h` command displays the mounted EBS volume at `/mnt/data-store`.

<img width="1233" height="907" alt="Screenshot 2026-08-03 155511" src="https://github.com/user-attachments/assets/cf5fb229-af75-49ee-8aa0-031750afa10b" />

---

### Output 3: File Created and Verified

The file `file.txt` is successfully created inside the EBS volume and the stored text is displayed.

```text
some text has been written
```
<img width="1147" height="280" alt="image" src="https://github.com/user-attachments/assets/6da9f10b-bff5-4ad4-a80e-0d9c860761b1" />


---

### Output 4: EBS Snapshot Created

The AWS EC2 Snapshots page shows `My Snapshot` with the snapshot creation completed successfully.
<img width="1920" height="1200" alt="Screenshot 2026-08-03 155619" src="https://github.com/user-attachments/assets/3b341dd3-2c5c-4816-a7b5-dbb647e81d09" />


---

### Output 5: Snapshot Restored Successfully

The snapshot is restored to a new EBS volume named `Restored Volume`. After attaching and mounting the restored volume, the deleted `file.txt` is successfully recovered.

```text
file.txt
```
<img width="1042" height="175" alt="image" src="https://github.com/user-attachments/assets/e4b96fc0-8bc9-4274-82b5-8e1ec12f3f3a" />

## Result
Amazon EBS was successfully used to create, attach, back up, restore, and recover data on an EC2 instance using snapshots.

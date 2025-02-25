

## 📌 Configure NFS Server and Client in Linux  

> **Note:** All steps should be executed as the **root** user.

### 🖥️ Setting Up the NFS Server  

1️⃣ **Install the `nfs-utils` package:**  
```bash
yum install -y nfs-utils
```

2️⃣ **Create a directory to share with clients:**  
```bash
mkdir /nfsshare 
chgrp nfsnobody /nfsshare/
chmod g+w /nfsshare/
```

3️⃣ **Edit the `/etc/exports` file and add the following line:**  
```bash
vi /etc/exports
```
```ini
/nfsshare *(rw,sync,no_root_squash,insecure)
```

4️⃣ **Re-export the shared directory:**  
```bash
exportfs -rav
```

5️⃣ **Enable and start the NFS server service:**  
```bash
systemctl start nfs-server
systemctl enable nfs-server
```

---

### 🔗 Setting Up the NFS Client  

🔹 Log in to the **target server** and execute the following steps:  

1️⃣ **Switch to the root user:**  
```bash
su - root
```

2️⃣ **Create a mount directory:**  
```bash
mkdir /nfsshare
```

3️⃣ **Mount the NFS filesystem:**  
```bash
mount -t nfs 10.10.10.100:/nfsshare /nfsshare
```
📌 *Replace `10.10.10.100` with the actual NFS server IP address.*

---

### 🎯 Verifying the Setup  

✔️ Check the mounted NFS share using:  
```bash
df -hT
```

✔️ Test writing to the NFS share:  
```bash
touch /nfsshare/testfile
ls -l /nfsshare/
```




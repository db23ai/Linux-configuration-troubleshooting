Configure NFS Server and Client in CentOS/RHEL 7

-- Execute all steps using root user

-- Install nfs-utils package

		yum install -y nfs-utils

-- Create a directory to share with other clients.

		mkdir /nfsshare ; chgrp nfsnobody /nfsshare/; chmod g+w /nfsshare/


-- Edit /etc/exports file and add below line

		vi /etc/exports
		/nfsshare *(rw,sync,no_root_squash,insecure)

-- Re-export the share

		exportfs -rav

-- Enable and start the nfs-server service

		systemctl start nfs-server ; systemctl enable nfs-server


-- Login into Target Server to mount nfs filesystem

-- Execute all steps using root user

	su - root

	mkdir /nfsshare

	mount -t nfs 10.10.10.100:/nfsshare /nfsshare      #Replance nfs server ipaddress to 10.10.10.100

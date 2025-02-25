🚀 Setup Yum Repository in Oracle Linux 7

Setting up the Yum repository in Oracle Linux 7 allows you to install and manage packages seamlessly. Follow these steps for a smooth configuration.

📌 Step 1: Switch to Root User

Run the following command to switch to the root user:

su -

📂 Step 2: Navigate to the Yum Repos Directory

Change the directory to the Yum repository configuration folder:

cd /etc/yum.repos.d

📝 Step 3: Create the Repository File

📌 Create a new repository file:

touch oracle-temp.repo

🖊️ Edit the file using vi or any text editor:

vi oracle-temp.repo

✍️ Add the following configuration:

[test]
name=Oracle Linux $releasever Latest ($basearch)
baseurl=https://yum.oracle.com/repo/OracleLinux/OL7/latest/x86_64
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-oracle
gpgcheck=1
enabled=1

Save and exit the file (ESC + :wq in vi).

✅ Step 4: Verify the Repository File

Ensure the repository file is correctly created:

cat /etc/yum.repos.d/oracle-temp.repo

📥 Step 5: Install Packages

Now, you can install packages using Yum:

yum install wget

🔍 Step 6: Troubleshooting

If you encounter "No enabled repos", list all repositories:

yum repolist all

Enable a specific repository:

yum-config-manager --enable <repo_name>

🔗 Reference

    Oracle Linux 7 Yum Repository

🎯 Summary

By following these steps, you can successfully configure and enable the Yum repository on Oracle Linux 7 for package management. If you experience issues, ensure proxy settings, internet connectivity, and repository configurations are correct.

🚀 Happy Installing!

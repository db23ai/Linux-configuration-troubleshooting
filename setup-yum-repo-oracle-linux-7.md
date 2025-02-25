To set up the Yum repository in Oracle Linux 7, follow these steps:

    Login to the Server: Use the root user to login to the server.

    Navigate to the Yum Repos Directory: Change the directory to /etc/yum.repos.d.

bash

cd /etc/yum.repos.d

    Create the Repository File: Create a file named oracle-temp.repo and add the repository configuration.

    Verify the Repository File: Ensure the repository file contains the correct information.

bash

cat /etc/yum.repos.d/oracle-temp.repo

The output should be:
INI

[test]
name=Oracle Linux $releasever Latest ($basearch)
baseurl=https://yum.oracle.com/repo/OracleLinux/OL7/latest/x86_64
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-oracle
gpgcheck=1
enabled=1

    Install Packages: You can now install packages using yum.

bash

yum install wget

If you encounter issues with no enabled repos, you can list all repositories and enable custom ones using:
bash

yum repolist all
yum-config-manager --enable <repo>

Reference:

    Oracle Linux Yum Server

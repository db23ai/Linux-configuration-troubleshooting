Install JDK 17

Install the JDK 17 RPM package using the following command:
bash

yum install jdk-17.0.12_linux-x64_bin.rpm --nogpgcheck

Example:
bash

[root@servername]# yum install jdk-17.0.12_linux-x64_bin.rpm --nogpgcheck
Examining jdk-17.0.12_linux-x64_bin.rpm: 2000:jdk-17-17.0.12-8.x86_64
Marking jdk-17.0.12_linux-x64_bin.rpm to be installed
Resolving Dependencies
--> Running transaction check
---> Package jdk-17.x86_64 2000:17.0.12-8 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

========================================================================================================================
 Package                     Arch                       Version                                     Repository       Size
========================================================================================================================
Installing:
 jdk-17                      x86_64                     2000:17.0.12-8                              /jdk-17.0.12_linux-x64_bin  304 M

Transaction Summary
========================================================================================================================
Install  1 Package

Total size: 304 M
Installed size: 304 M
Is this ok [y/d/N]: y
Downloading packages:
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : 2000:jdk-17-17.0.12-8.x86_64                                                                                                                                        1/1 
  Verifying  : 2000:jdk-17-17.0.12-8.x86_64                                                                                                                                        1/1 

Installed:
  jdk-17.x86_64 2000:17.0.12-8                                                                                                                                                         

Complete!


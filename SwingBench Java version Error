# 🖥️ SwingBench Java Version Error

If you encounter a `java.lang.UnsupportedClassVersionError` when running SwingBench, follow these steps to resolve the issue.

## Issue:
```
[oracle@servername]$ ./oewizard -allindexes -bigfile -bs 10000 -cl -create  -dba "admin@orcl_high" -dbap "Test@1234" -nocompress -p "Test@1234" -part -scale 1 -ts ts_sb_oe -u soe21 –v
java.lang.UnsupportedClassVersionError: com/dom/benchmarking/swingbench/wizards/Wizard has been compiled by a more recent version of the Java Runtime (class file version 55.0), this version of the Java Runtime only recognizes class file versions up to 52.0
        at java.lang.ClassLoader.defineClass1(Native Method)
        at java.lang.ClassLoader.defineClass(Unknown Source)
        at java.security.SecureClassLoader.defineClass(Unknown Source)
        at java.net.URLClassLoader.defineClass(Unknown Source)
        at java.net.URLClassLoader.access$100(Unknown Source)
        at java.net.URLClassLoader$1.run(Unknown Source)
        at java.net.URLClassLoader$1.run(Unknown Source)
        at java.security.AccessController.doPrivileged(Native Method)
        at java.net.URLClassLoader.findClass(Unknown Source)
        at java.lang.ClassLoader.loadClass(Unknown Source)
        at sun.misc.Launcher$AppClassLoader.loadClass(Unknown Source)
        at java.lang.ClassLoader.loadClass(Unknown Source)
        at java.lang.Class.forName0(Native Method)
        at java.lang.Class.forName(Unknown Source)
        at org.apache.commons.launcher.ChildMain.run(ChildMain.java:183)
```

## Solution:

Use the latest SwingBench software (e.g., `swingbench20022024a.zip`) which is built for Java 11+. Hence, install the latest Java JDK.

1. Download the latest Java JDK:
   [Download JDK 22](https://download.oracle.com/java/22/latest/jdk-22_linux-x64_bin.rpm)

2. Copy the downloaded RPM to the target server and install using `yum`:

```bash
[root@servername opc]# yum install -y jdk-22_linux-x64_bin.rpm
```

### Sample Output:
```bash
Loaded plugins: versionlock
Examining jdk-22_linux-x64_bin.rpm: 2000:jdk-22-22.0.1-8.x86_64
Marking jdk-22_linux-x64_bin.rpm to be installed
Resolving Dependencies
--> Running transaction check
---> Package jdk-22.x86_64 2000:22.0.1-8 will be installed
--> Finished Dependency Resolution
--> Finding unneeded leftover dependencies
Found and removing 0 unneeded dependencies

Dependencies Resolved

=============================================================================================================================================================
 Package                         Arch                            Version                                Repository                                      Size
=============================================================================================================================================================
Installing:
 jdk-22                          x86_64                          2000:22.0.1-8                          /jdk-22_linux-x64_bin                          327 M

Transaction Summary
=============================================================================================================================================================
Install  1 Package

Total size: 327 M
Installed size: 327 M
Downloading packages:
warning: /home/opc/jdk-22_linux-x64_bin.rpm: Header V3 RSA/SHA256 Signature, key ID ad986da3: NOKEY

Public key for jdk-22_linux-x64_bin.rpm is not installed
[root@source-servername opc]# yum install -y jdk-22_linux-x64_bin.rpm --nogpgcheck
Loaded plugins: versionlock
Examining jdk-22_linux-x64_bin.rpm: 2000:jdk-22-22.0.1-8.x86_64
Marking jdk-22_linux-x64_bin.rpm to be installed
Resolving Dependencies
--> Running transaction check
---> Package jdk-22.x86_64 2000:22.0.1-8 will be installed
--> Finished Dependency Resolution
--> Finding unneeded leftover dependencies
Found and removing 0 unneeded dependencies

Dependencies Resolved

=============================================================================================================================================================
 Package                         Arch                            Version                                Repository                                      Size
=============================================================================================================================================================
Installing:
 jdk-22                          x86_64                          2000:22.0.1-8                          /jdk-22_linux-x64_bin                          327 M

Transaction Summary
=============================================================================================================================================================
Install  1 Package

Total size: 327 M
Installed size: 327 M
Downloading packages:
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
Warning: RPMDB altered outside of yum.
  Installing : 2000:jdk-22-22.0.1-8.x86_64                                                                                                               1/1
  Verifying  : 2000:jdk-22-22.0.1-8.x86_64                                                                                                               1/1

Installed:
  jdk-22.x86_64 2000:22.0.1-8

Complete!
```

After installation, the `SwingBench` command should work without issues:
```bash
[oracle@servername bin]$ ./oewizard -allindexes -bigfile -bs 10000 -cl -create  -dba "admin@orcl_high" -dbap "Test@1234" -nocompress -p "Test@1234" -part -scale 1 -ts ts_sb_oe -u soe21 –v

SwingBench Wizard
Author  :       Dominic Giles
Version :       2.7.0.1438

Running in Lights Out Mode using config file : ../wizardconfigs/oewizard.xml
```

---

*This document was last updated on 2025-02-25 18:02:28 (UTC).*

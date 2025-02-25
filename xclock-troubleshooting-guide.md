🖥️ Fix xclock Display Not Working in Oracle Linux 8

    Issue:
    bash: xclock: command not found

    If xclock is not working in Oracle Linux 8, follow these steps to resolve the issue.

📌 1. Prerequisites
🔹 Log in as the root user

su -

🔹 Check OS Version

uname -a

📌 Example Output:

[root@servername ~]# uname -a
Linux servername 5.4.17-2136.327.2.el8uek.x86_64 #2 SMP Fri Jan 5 14:55:52 PST 2024 x86_64 x86_64 x86_64 GNU/Linux

🔍 2. Check if xclock RPM Exists

Run the following command:

rpm -qa xorg-x11-apps

📌 If the output is empty, it means xclock is not installed. Proceed to installation.
📥 3. Install xclock (xorg-x11-apps)
🔹 For systems behind a VPN or firewall

Set up a proxy (use company-authorized settings):

export https_proxy=www-proxy-servername.ind.servername.com:80
export http_proxy=www-proxy-servername.ind.servername.com:80

🔹 Enable Required Repository

dnf config-manager --enable ol8_codeready_builder

🔹 Install xorg-x11-apps

dnf install -y xorg-x11-apps

✅ Verification

After installation, test if xclock is working:

xclock

🎯 If the graphical clock appears, the installation is successful!
📌 Additional Troubleshooting
🔹 Check if X11 Forwarding is enabled

cat /etc/ssh/sshd_config | grep X11Forwarding

📌 If the output is X11Forwarding no, update it to X11Forwarding yes and restart SSH:

systemctl restart sshd

🔹 Ensure DISPLAY variable is set

echo $DISPLAY

If empty, set it manually:

export DISPLAY=:0.0

🎯 Conclusion

Following these steps will resolve the xclock display issue on Oracle Linux 8. If problems persist, ensure your X server is running on your local machine (e.g., Xming or VcXsrv for Windows users).


# Linux Security Command Cheat Sheet

**Last Updated:** 20 May, 2024

Maintaining a secure and hardened Linux system is crucial in today's threat-laden digital landscape. This comprehensive Linux Security Command Cheat Sheet serves as an invaluable resource for system administrators and security professionals.

From user and group management to privilege escalation, file system security, process monitoring, firewall configuration, and security scanning, this guide covers a wide array of tools and utilities tailored for fortifying Linux environments.

## 1. User and Group Management
Commands to create, modify, and delete user accounts, set passwords, and manage memberships.

| Command | Description | Example |
| :--- | :--- | :--- |
| `passwd` | Change or set user password. | `passwd user1` |
| `chpasswd` | Change passwords in bulk using a text file. | `chpasswd < user_passwords.txt` |
| `chage` | Set aging properties for user passwords. | `chage -M 90 user1` |
| `useradd` | Create a new user account. | `useradd -m user2` |
| `usermod` | Modify existing user account settings. | `usermod -l newuser olduser` |
| `userdel` | Delete a user account. | `userdel user2` |
| `groupadd` | Create a new group. | `groupadd group1` |
| `groupmod` | Modify existing group settings. | `groupmod -n newgroup oldgroup` |
| `groupdel` | Delete a group. | `groupdel group1` |

## 2. Privilege Management
Tools to temporarily elevate or switch user privileges.

| Command | Description | Example |
| :--- | :--- | :--- |
| `su` | Switch user (temporarily become another user). | `su - username` |
| `sudo` | Execute commands with elevated privileges. | `sudo command` |
| `visudo` | Edit the sudoers file safely. | `sudo visudo` |

## 3. File and Directory Management
Essentials for managing permissions, ownership, and access rights.

| Command | Description | Example |
| :--- | :--- | :--- |
| `chmod` | Change file permissions. | `chmod 644 file.txt` |
| `chown` | Change file ownership. | `chown user1 file.txt` |
| `chgrp` | Change file group ownership. | `chgrp group1 file.txt` |
| `umask` | Set default permissions for newly created files. | `umask 077` |
| `ls` | List directory contents. | `ls -l` |

## 4. Process Management
Insights into running processes, resource usage, and network connections.

| Command | Description | Example |
| :--- | :--- | :--- |
| `ps` | Display information about running processes. | `ps aux` |
| `top` | Display dynamic real-time process info. | `top` |
| `netstat` | Display network connections and routing tables. | `netstat -tuln` |
| `ss` | A tool to investigate sockets (modern netstat). | `ss -tuln` |
| `lsof` | List open files and the processes that opened them. | `lsof /path/to/file` |

## 5. Firewall and Security
Tools for configuring firewalls, intrusion prevention, and auditing.

| Command | Description | Example |
| :--- | :--- | :--- |
| `firewalld` | Manage firewall rules (modern). | `firewall-cmd --zone=public --add-port=80/tcp --permanent` |
| `fail2ban` | Intrusion prevention system scanning log files. | `fail2ban-client status` |
| `auditd` | Monitor system calls and file system events. | `auditctl -l` |
| `semanage` | SELinux policy management tool. | `semanage fcontext -a -t httpd_sys_content_t '/web(/.*)?'` |
| `getsebool` | Get the value of an SELinux boolean. | `getsebool httpd_can_network_connect` |
| `setsebool` | Set the value of an SELinux boolean. | `setsebool -P httpd_can_network_connect on` |
| `sestatus` | Display SELinux status. | `sestatus` |
| `AppArmor` | Mandatory access control framework. | `aa-status` |
| `sysctl` | Configure kernel parameters at runtime. | `sysctl -w net.ipv4.tcp_syncookies=1` |
| `ufw` | Uncomplicated Firewall. | `ufw allow ssh` |

## 6. Networking and Security Tools
Utilities for secure remote access, scanning, encryption, and data transfer.

| Command | Description | Example |
| :--- | :--- | :--- |
| `ssh` | Secure Shell - remote login protocol. | `ssh user@hostname` |
| `openssl` | Manage SSL/TLS certificates and keys. | `openssl req -new -newkey rsa:2048 -nodes -keyout key.pem -out req.pem` |
| `gpg` | Encryption and signing tool. | `gpg --encrypt --recipient recipient@example.com file.txt` |
| `sshd` | Secure Shell Daemon configuration. | `sshd -t` |
| `nmap` | Network exploration tool and security scanner. | `nmap -sV target_IP` |
| `tcpdump` | Packet analyzer. | `tcpdump -i eth0` |
| `wireshark` | Network protocol analyzer (GUI). | `wireshark` |
| `curl` | Transfer data with URLs. | `curl -O http://example.com/file.txt` |
| `wget` | Retrieve files from the web. | `wget http://example.com/file.txt` |

## 7. Security Scanners
Tools to detect rootkits, backdoors, and vulnerabilities.

| Command | Description | Example |
| :--- | :--- | :--- |
| `chkrootkit` | Check for signs of a rootkit infection. | `chkrootkit` |
| `rkhunter` | Scan for rootkits, backdoors, and exploits. | `rkhunter --check` |
| `lynis` | Security auditing and hardening tool. | `lynis audit system` |

---
*Disclaimer: Use these commands responsibly. Always verify commands before running them in a production environment.*


OS enumeration

uname -a
cat /etc/release


Processes and Shells


ps -efH | grep -i ".*tty.*"
w #shells
who 
id

netstat -ttpnau 
netstat -ltuna
ss -auntp #need sudo

ps
lsof


User enumeration

cat /etc/sudoers
cat /etc/password >> users.txt #login shells 
cat /etc/passwd | grep -v "nologin" -E "false"


DNS and Domain enumeration
cat /etc/hosts
cat /etc/resolv.conf

# dns queries listed
cat /etc/nsswitch.conf


File System Enumeration


ls -latrh
ls -lsa 
ls -lp


ps auxf
ps -fHww
pstree
pstree -p -s <pid>





Services

→ check systemd, sysv, upstart

```markdown

ls -lotr /sbin/init
inetd
xinetd
cat /lib/systemd/systemd
```

Cronjobs

```markdown
crontab -l -u <user>
crontab

# Directories:
/etc/crontab
/var/spool/cron
/etc/cron.d

```

Logging

```markdown
/usr/bin/syslog
cat /var/log/syslog | grep "bash*"

# Interesting files to always check
wmtp #failed authentications
auth.log
kern.log
gpu-mgr-switch.log

#Apache logs
error.log
access.log
auth.log

```
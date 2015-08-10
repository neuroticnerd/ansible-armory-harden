ansible-armory-harden
=====================

install fail2ban
configure fail2ban

install ufw
configure ufw

change to non-standard ssh port


*   disable password login and root access (after testing devops user!)
    *   nano /etc/ssh/sshd_config
    *   PasswordAuthentication yes -> PasswordAuthentication no
    *   ChallengeResponseAuthentication yes -> ChallengeResponseAuthentication no
    *   PermitRootLogin no
    *   X11Forwarding no
    *   UseDNS no
    *   AllowGroups sshlogin
    *   Port {{ non_standard_ssh_port }}
*   lock ssh to specific IPs if desired
    *   AllowUsers devops@(ip) devops@(another-ip)
*   restart the ssh daemon
    *   sudo service ssh restart
*   configure firewall
    *   uwf or iptables?

*   enable automatic security updates?
*   install logwatch or other logging daemon

http://serverfault.com/questions/545978/how-to-handle-ssh-port-changes-with-ansible


/etc/apt/sources.list


deb http://us-east-1.ec2.archive.ubuntu.com/ubuntu/ trusty main restricted
deb http://us-east-1.ec2.archive.ubuntu.com/ubuntu/ trusty universe
deb http://us-east-1.ec2.archive.ubuntu.com/ubuntu/ trusty multiverse
deb http://us-east-1.ec2.archive.ubuntu.com/ubuntu/ trusty-updates main restricted
deb http://us-east-1.ec2.archive.ubuntu.com/ubuntu/ trusty-updates universe
deb http://us-east-1.ec2.archive.ubuntu.com/ubuntu/ trusty-updates multiverse
deb http://us-east-1.ec2.archive.ubuntu.com/ubuntu/ trusty-security main restricted
deb http://us-east-1.ec2.archive.ubuntu.com/ubuntu/ trusty-security universe
deb http://us-east-1.ec2.archive.ubuntu.com/ubuntu/ trusty-security multiverse

deb-src http://us-east-1.ec2.archive.ubuntu.com/ubuntu/ trusty main restricted
deb-src http://us-east-1.ec2.archive.ubuntu.com/ubuntu/ trusty universe
deb-src http://us-east-1.ec2.archive.ubuntu.com/ubuntu/ trusty multiverse
deb-src http://us-east-1.ec2.archive.ubuntu.com/ubuntu/ trusty-updates main restricted
deb-src http://us-east-1.ec2.archive.ubuntu.com/ubuntu/ trusty-updates universe
deb-src http://us-east-1.ec2.archive.ubuntu.com/ubuntu/ trusty-updates multiverse
deb-src http://us-east-1.ec2.archive.ubuntu.com/ubuntu/ trusty-security main restricted
deb-src http://us-east-1.ec2.archive.ubuntu.com/ubuntu/ trusty-security universe
deb-src http://us-east-1.ec2.archive.ubuntu.com/ubuntu/ trusty-security multiverse

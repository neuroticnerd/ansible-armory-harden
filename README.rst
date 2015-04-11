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


mkdir roles/base/templates ; cp /etc/ssh/sshd_config roles/base/templates/sshd_config_ubuntu.j2
    
nano roles/base/templates/sshd_config_ubuntu.j2
   
cd roles/base/templates/


## SERVER 3 SSH Access change restriction
 sudo chmod a+r /etc/ssh/sshd_config
 ls -l /etc/ssh/sshd_config
 sudo chmod o+r /etc/ssh/sshd_config
 sudo chmod o-r /etc/ssh/sshd_config




 
scp server3:/etc/ssh/sshd_config sshd_config_centos.j2
vim sshd_config_centos.j2
echo "AllowUsers {{ ssh_users }}" >> sshd_config_centos.j2
echo "AllowUsers {{ ssh_users }}" >> sshd_config_ubuntu.j2

# Adding-user-to-Linux-Machine-and-giving-SSH-access
Contains steps to add a new user in a Linux environment and giving SSH privileges

To create user and give access via SSH:

Create a new user as follows:

sudo useradd hadoopuser
sudo passwd hadoopuser

sudo visudo
Add the following line for newuser:
hadoopuser ALL= NOPASSWD: ALL

sudo vi /etc/ssh/external_sshd_config
Add the following in the last line:
AllowUsers hadoopuser

sudo service ext_sshd restart

Once you restart the machine, you should be able to reconnect using the new user.

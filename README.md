# hp_ilo_control
Control power of HP servers using SSH/Plink by sending power commands through iLO. Works great for home labs where you want to easily shutdown and start-up your loud power hungry servers.

Best practice would be to setup a dedicated used for power management in iLO. I generating SSH Key through Putty Key Generator and installing them in iLO for the user account.

Set your Server IP or Hostname in the script.

Open a CMD and change to the directory with the Plink executable and the SSH private key. The following command turns the server on.
C:\Program Files (x86)\PuTTY>plink -i ilo_poweradmin_privatekey.ppk poweradmin@192.168.1.1 "power on"

To turn off, simply use this command:
C:\Program Files (x86)\PuTTY>plink -i ilo_poweradmin_privatekey.ppk poweradmin@192.168.1.1 "power off"

A warm reset can be requested by using this command:
C:\Program Files (x86)\PuTTY>plink -i ilo_poweradmin_privatekey.ppk poweradmin@192.168.1.1 "power warm"

A cold reset can be requested by using this command:
C:\Program Files (x86)\PuTTY>plink -i ilo_poweradmin_privatekey.ppk poweradmin@192.168.1.1 "power reset"

Example batch file is included

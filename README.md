# hp_ilo_control
Control power of HP servers using SSH/Plink by sending power commands through iLO. Works great for home labs where you want to easily shutdown and start-up your loud, power hungry servers. I use it to control power to my VMWare home environment.

Best practice would be to setup a dedicated user for power management in iLO. Im generating SSH Public/Private key through Putty Key Generator and installing them in iLO for the user account.

Set your .ppk file location and server IP or Hostname in the script.

Open a CMD and change to the directory with the Plink executable and the SSH private key. The following command turns the server on.
plink -i ilo_poweradmin_privatekey.ppk poweradmin@192.168.1.1 "power on"

To turn off, simply use this command:
plink -i ilo_poweradmin.ppk poweradmin@192.168.1.1 "power off"

A warm reset can be requested by using this command:
plink -i ilo_poweradmin.ppk poweradmin@192.168.1.1 "power warm"

A cold reset can be requested by using this command:
plink -i ilo_poweradmin.ppk poweradmin@192.168.1.1 "power reset"

Example batch file is included

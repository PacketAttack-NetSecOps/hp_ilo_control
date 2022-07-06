# hp_ilo_control
Control power of HP servers using SSH/Plink by sending power commands thourgh iLO

Best practice would be to setup a dedicated used for power management in ILO. Im generating SSH Key through Putty Key Generator and installing them in ILO for the user account.

Set your Server IP or Hostname in the script.

Open a CMD and change to the directory with the Plink executable and the SSH private key. The following command turns the server on.
C:\Program Files (x86)\PuTTY>plink -i sshlogin.ppk sshlogin@192.168.1.1 "power on"

To turn off, simply use this command:
C:\Program Files (x86)\PuTTY>plink -i sshlogin.ppk sshlogin@192.168.1.1 "power off"

A warm reset can be requested by using this command:
C:\Program Files (x86)\PuTTY>plink -i sshlogin.ppk sshlogin@192.168.1.1 "power warm"

A cold reset can be requested by using this command:
C:\Program Files (x86)\PuTTY>plink -i sshlogin.ppk sshlogin@192.168.1.1 "power reset"

You can put these commands into a batchfile to power on/ off a couple of servers with a single click.

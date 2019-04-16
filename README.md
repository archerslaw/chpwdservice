## chpwdservice
Using the rhsrvany to registry some script as a windows service to reset Windows password.

Steps:
------
1、mount the windows system vulume to the linux VM as a data volume.
  - #mount /dev/vdb2 /mnt/
 
2、go to the /mnt/ to clone the chpwdservice.git
  - #cd /mnt/
  - #git clone https://github.com/archerslaw/chpwdservice.git
  
3、backup the SYSTEM file
  - #cp /mnt/Windows/System32/config/SYSTEM /mnt/Windows/System32/config/SYSTEM.backup
  
4、import the reg file to registry some script as a windows service
  - #reged -I /mnt/Windows/System32/config/SYSTEM HKEY_LOCAL_MACHINE\\\SYSTEM /mnt/chpwdservice/chpwd.reg

#### Note: 
Donot forget to remove chpwdservice directory after login to the windows, kill the rhsrvany.exe first and then remove the chpwdservice directory.

Contact & Contribute
--------------------

For information on how to contribute to chpwdservice, please feel free to contact me with email or send pull requests directly.

-- End of broadcast

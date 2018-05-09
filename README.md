# Linux
          MODIFYING PERMISSIONS AND OWNERSHIP
          
chmod u+x filename – adds execute permission for the owner of the file

chmod a+x filename – adds execute permission for all users

chmod a-x filename – removes execute permission for all users

chmod g-x filename – removes execute permission for the file’s group

chmod a=x filename – gives all users execute permission, nothing more or less

chmod o=rx filename – sets other users’ permissions to read and execute, not write

chmod ug+x filename – adds execute permission for the owner and the group



Users in Linux can belong to more than one group. In this case you want to create a brand new group, let's call it tomandruser:

sudo groupadd tomandruser
Now that the group exists, add the two users to it:

sudo usermod -a -G tomandruser tomcat6
sudo usermod -a -G tomandruser ruser
Now all that's left is to set the permissions on the directory:

sudo chgrp -R tomandruser /path/to/the/directory
sudo chmod -R 770 /path/to/the/directory

User and Group Management :
------------------------------

 
There are three types of user: 

1.Super user: Super users are those users who has all privileges of Linux system.

2.System user: System accounts are used by the services in Linux system. 
These accounts or users generally created when services are installed in system.  

3.Standard user: local user accounts or standard user accounts are for the people who need to work on a system and who need .limited access to the resources on that system.
  

Files affected by newly added user :

/etc/passwd: It stores user profile related information,  
/etc/shadow: It stores user password policies 
/etc/group: It stores group information. 
/etc/gshadow: Stores group password and member’s list. 

su: The ‘su’ command is used to switch users. 
Syntax, # su - <user_name>  

Password Management : 
#passwd: change the current user’s password  
#passwd username: assign or change other user’s password by root. 

/etc/shadow file: It stores the password and password policies of all users.
 
It contains nine fields and each field is separated by colon. 
   
1.Username 
2.Encrypted password 
3. Days since Jan 1, 1970, that the password was last changed 
4.Days before password may be changed 
5.Days after which password must be changed 
6.Days before password is to expire that user is warned 
7.Days after password expires that account is disabled 
8. Days since Jan 1, 1970, that account is disabled 
9.For future use 


View and change password policy : 
#chage – ‘chage’ (change age) command used to view or modify the password policy of the user.  
Syntax :   chage <option> <parameter> <username>                       
 Options: 
     -l:-   list / view password policy.  
     -m:-   min. days between password changes.  
     -M:-   maximum days between password changes.  
     -W:-   number of days of warning.  
     -I:-   number of inactivation days.  
     -E:-   The expiry date of the user account.  
     -d:-   force to change password.  
 
 
 
 
Group Administration/Management : 

Linux users can be a members of two different kinds of groups. First, there is the primary group. Every user must be a member of a primary group and there is only one primary group. When creating files, the primary group becomes the group owner of these files. 
 
#groupadd –  command is used to add secondary or supplementary group in the system.  
 
Syntax  : # groupadd <groupname>  
 
/etc/group file: This file contains all the group’s information.

The file has four fields and each field is separated by a colon (:). 
Following are fields of shadow file: 
 
1. Group name:  
2. Redirected group password:.  
3. Group id (GID):   
4. List of members:
   
Adding a group with a customize setting :

Syntax:

# groupadd <option> <parameter> <groupname>
  
Options :
 -g:-  Group id 
 -o:- Non unique  
 -f:- Forcefully 

Modify existing group with customize setting: 
Syntax:

# groupmod <option> <parameter> <groupname> 
 
Options : 
-g :- Group id  
-n :- Group Name 
-o :- Non unique 

User Administration/Management :

#useradd – ‘useradd’ command use to create new user account.   
Syntax:  # useradd <username> 

/etc/passwd file: This file stores user profile information.  
It contains 7 fields as follows: 
①:②:③:④:⑤:⑥:⑦  
1. User login name:  
2. Password link from shadow file: 
3. User id (UID): 
4. Primary group’s id (GID  
5. Comment field:  
6. Home Directory Home Directory:  
7. Login shell : 

Adding users with customized settings: 
Syntax : # useradd <options> <parameters> <username>  

Options: 
-u:- User id 
-g:- Primary group 
-c:- Comment 
-d:-  Home directory 
-s:- Login shell 
-G:- Secondary Group 
-r:- System user 
-e:- Account expiry date 
-o:- Non unique 

Modify user with customized setting:

#usermod – ‘usermod’ command is use to modify existing user’s setting.   
Syntax: 
# usermod <option> <parameters> <username>  

Options: 
-u:-  user id  
-g:-  primary group   
-c:-  Comment  
-d:-  home directory  
-s:-  login shell  
-G:-  secondary group  
-l:- login name  
-L:-  lock user password  
-U:-  unlock user password  
-m:-  modify directories 

Remove the user from the system:
 
#userdel – ‘userdel’ command is used to remove or delete user account from system.  
Syntax: 
# userdel <username> 

#gpasswd – command is used to give password to the group. 
It also can be used to add members and assign admin to the group.  
Syntax: 
# gpasswd <option> <parameter> <groupname>  

Options: 
-a:- Add members in the group  
-M:- Set a list of members in the group  
-A:- Assign user as group admin 

# User and Group Management in Linux

## Types of Users
There are three types of users in a Linux system:

1. **Super User**: Has all administrative privileges on the system (root user).
2. **System User**: Created automatically when services are installed (e.g., `mysql`, `nginx`).
3. **Standard User**: Regular user accounts with limited access to system resources.

## Files Affected by a Newly Added User
- `/etc/passwd` - Stores user profile-related information.
- `/etc/shadow` - Stores user password policies.
- `/etc/group` - Stores group-related information.
- `/etc/gshadow` - Stores group passwords and member lists.

---
## User Switching
Use the `su` command to switch users:
```bash
su - <username>
```

## Password Management
### Change User Passwords
```bash
passwd                 # Change the current user's password
passwd <username>      # Change another user's password (requires root)
```
### `/etc/shadow` File Format
This file stores password policies and contains nine fields:
1. Username
2. Encrypted password
3. Days since last password change (since Jan 1, 1970)
4. Minimum days before password can be changed
5. Maximum days before password must be changed
6. Days before expiry to warn user
7. Days after expiry before account is disabled
8. Days since Jan 1, 1970, when account was disabled
9. Reserved for future use

### View or Change Password Policy
Use the `chage` command:
```bash
chage <option> <username>
```
#### Options:
- `-l` : List password policies
- `-m` : Set minimum days between password changes
- `-M` : Set maximum days before password change
- `-W` : Set days before expiry warning
- `-I` : Set inactivity period before deactivation
- `-E` : Set account expiry date
- `-d` : Force immediate password change

---
## Group Management
### Types of Groups
1. **Primary Group** - A user must belong to one primary group. When creating files, the primary group owns them.
2. **Secondary Group** - Users can belong to multiple secondary groups.

### Adding a Group
```bash
groupadd <groupname>
```
### `/etc/group` File Format
This file contains four fields:
1. Group Name
2. Encrypted Password (usually `x`)
3. Group ID (GID)
4. List of Group Members

### Adding a Group with Custom Settings
```bash
groupadd <option> <groupname>
```
#### Options:
- `-g` : Specify Group ID (GID)
- `-o` : Allow non-unique GID
- `-f` : Force group creation

### Modifying an Existing Group
```bash
groupmod <option> <groupname>
```
#### Options:
- `-g` : Change Group ID
- `-n` : Rename Group
- `-o` : Allow duplicate GID

---
## User Management
### Adding a User
```bash
useradd <username>
```
### `/etc/passwd` File Format
This file contains seven fields:
1. Username
2. Password (linked from shadow file)
3. User ID (UID)
4. Primary Group ID (GID)
5. Comment field
6. Home Directory
7. Default Shell

### Adding a User with Custom Settings
```bash
useradd <option> <username>
```
#### Options:
- `-u` : Specify User ID
- `-g` : Specify Primary Group
- `-c` : Add a Comment
- `-d` : Set Home Directory
- `-s` : Define Login Shell
- `-G` : Assign Secondary Group
- `-r` : Create a System User
- `-e` : Set Account Expiry Date
- `-o` : Allow Duplicate UID

### Modifying an Existing User
```bash
usermod <option> <username>
```
#### Options:
- `-u` : Change User ID
- `-g` : Change Primary Group
- `-c` : Modify Comment
- `-d` : Change Home Directory
- `-s` : Change Login Shell
- `-G` : Modify Secondary Groups
- `-l` : Change Login Name
- `-L` : Lock User Account
- `-U` : Unlock User Account
- `-m` : Move Home Directory

### Removing a User
```bash
userdel <username>
```

### Managing Group Passwords
```bash
gpasswd <option> <groupname>
```
#### Options:
- `-a` : Add a user to the group
- `-M` : Define a list of group members
- `-A` : Assign a user as group admin

---
This document provides essential commands for user and group management in Linux. You can add this to GitHub as a Markdown file (`user_group_management.md`) for easy reference.


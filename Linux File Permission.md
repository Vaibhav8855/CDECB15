# **Linux File Permissions **

In Linux, every file and folder has permissions that control who can read, write, or execute them. This helps keep the system secure.

---

## **1. Types of Users in Linux**
Every file and folder in Linux has three types of users:

| User Type | Description |
|-----------|-------------|
| **Owner (User)** | The person who created the file/folder |
| **Group** | A set of users who share access to the file |
| **Others (World)** | Everyone else on the system |

---

## **2. Types of Permissions**
Each file/folder has three types of permissions:

| Symbol | Meaning | Numeric Value |
|--------|---------|--------------|
| `r` | Read (view the file) | 4 |
| `w` | Write (edit/delete the file) | 2 |
| `x` | Execute (run the file, if it's a program/script) | 1 |

These permissions are applied separately to:
- **Owner**
- **Group**
- **Others**

---

## **3. Checking File Permissions**
Use the `ls -l` command to see file permissions.

```bash
ls -l
```

### Example Output:
```
-rwxr--r-- 1 user group 1234 Mar 15 10:30 myfile.sh
```

### Breakdown:
- **First character:** `-` (File) or `d` (Directory)
- **Next 3 characters:** Owner’s permissions (`rwx`)
- **Next 3 characters:** Group’s permissions (`r--`)
- **Next 3 characters:** Others’ permissions (`r--`)

**Example Explanation:**
- The **owner** (`user`) can read (`r`), write (`w`), and execute (`x`).
- The **group** can only read (`r--`).
- **Others** can only read (`r--`).

---

## **4. Changing File Permissions (`chmod`)**
### **Using Symbolic Method**
```bash
chmod u+x myfile.sh   # Add execute permission for owner
chmod g-w myfile.sh   # Remove write permission for group
chmod o+r myfile.sh   # Give read permission to others
chmod a+x myfile.sh   # Allow everyone to execute
```

### **Using Numeric (Octal) Method**
Each permission is represented by a number:
- **Read (r) = 4**
- **Write (w) = 2**
- **Execute (x) = 1**

To set permissions, add up the values:
- `rwx` = 4+2+1 = **7**
- `rw-` = 4+2 = **6**
- `r--` = 4 = **4**

```bash
chmod 754 myfile.sh
```
This means:
- **7** (Owner: `rwx`)
- **5** (Group: `r-x`)
- **4** (Others: `r--`)

---

## **5. Changing File Ownership (`chown` & `chgrp`)**
- **Change file owner**:
  ```bash
  chown newuser myfile.sh
  ```
- **Change group**:
  ```bash
  chgrp newgroup myfile.sh
  ```
- **Change both owner and group**:
  ```bash
  chown newuser:newgroup myfile.sh
  ```

---

## **6. Special Permissions**
### **Set User ID (SUID) (`s`)**
- Allows a program to run with the owner's permissions.
- Used in commands like `passwd`.

```bash
chmod u+s myfile.sh
```
**Symbol:** `rwsr-xr-x`

### **Set Group ID (SGID) (`s`)**
- New files in a folder inherit the folder’s group.

```bash
chmod g+s mydir
```
**Symbol:** `rwxr-sr-x`

### **Sticky Bit (`t`)**
- Used on shared folders like `/tmp` so only the file owner can delete their files.

```bash
chmod +t /tmp
```
**Symbol:** `rwxrwxr-t`

---

## **7. Default Permissions (`umask`)**
The `umask` command sets default permissions for new files and folders.

Check current `umask`:
```bash
umask
```

Example output:
```
0022
```
This means:
- **New files:** `666 - 022 = 644` (`rw-r--r--`)
- **New folders:** `777 - 022 = 755` (`rwxr-xr-x`)

Change default permissions:
```bash
umask 0027   # New files: 640, New directories: 750
```

---

## **8. Advanced Permissions (ACL)**
For extra control, you can use **Access Control Lists (ACL)**.

- **Enable ACL**:
  ```bash
  sudo apt install acl   # Ubuntu/Debian
  sudo yum install acl   # RHEL/CentOS
  ```
- **Give a user specific permissions**:
  ```bash
  setfacl -m u:username:rwx myfile
  ```
- **View ACL**:
  ```bash
  getfacl myfile
  ```
- **Remove ACL**:
  ```bash
  setfacl -x u:username myfile
  ```

---

## **9. Useful Examples**
| Task | Command |
|------|---------|
| View file permissions | `ls -l` |
| Make a file executable | `chmod +x script.sh` |
| Set full permissions for everyone | `chmod 777 myfile.sh` |
| Make a file read-only | `chmod 444 myfile.sh` |
| Allow only the owner to read/write | `chmod 600 myfile.sh` |
| Change file owner | `chown user myfile.sh` |
| Change file group | `chgrp group myfile.sh` |
| Set SUID (run as file owner) | `chmod u+s file.sh` |
| Set SGID (inherit group) | `chmod g+s directory/` |
| Set Sticky Bit (protect files in a shared folder) | `chmod +t /tmp` |

---

## **10. Summary**
- Every file has **three permission groups**: **Owner, Group, Others**.
- Permissions are **Read (4), Write (2), Execute (1)**.
- Use `chmod` to change permissions (`chmod 755 file`).
- Use `chown` to change the file owner (`chown user file`).
- Use `umask` to set default permissions for new files.
- Special permissions: **SUID, SGID, Sticky Bit** for advanced security.

---



# Intermediate Linux Practice Tasks

## File and Directory Management
1. Find all files larger than 10 MB in the `/home` directory.
2. Create a directory structure like `projects/{project1,project2}/{src,bin,docs}` in a single command.
3. Copy all `.log` files from one directory to another while preserving their timestamps.
4. Create a symbolic link named `shortcut` pointing to a file of your choice.
5. Compress the `projects` directory into a `.tar.gz` archive.

## File Permissions and Ownership
6. Change the ownership of all files in the `projects` directory to a user named `developer`.
7. Grant execute permission to all `.sh` files in a directory.
8. Set the sticky bit on a directory to prevent others from deleting files they don’t own.
9. Find files in the `/var` directory that are writable by the group.

## Text Processing
10. Extract the 3rd column from a CSV file named `data.csv`.
11. Count the occurrences of the word "error" in a log file.
12. Remove all empty lines from a file named `report.txt`.
13. Sort a file named `scores.txt` by the second column.
14. Extract lines between the 10th and 20th line in a file named `log.txt`.

## Process and System Monitoring
15. Monitor real-time system resource usage (CPU, memory, disk I/O) for 1 minute.
16. Kill all processes running a specific program, such as `apache2`.
17. Display the top 5 memory-consuming processes on your system.
18. Check which processes are using the most disk I/O.
19. Display the number of threads used by the `ssh` service.

## Networking
20. List all active network connections on your system.
21. Download a file from the internet using `wget` or `curl`.
22. Find the open ports on your system using `netstat` or `ss`.
23. Test the speed of your internet connection using a command-line tool.
24. Display the route that packets take to reach a website (e.g., `google.com`).

## System Configuration
25. Add a cron job that clears temporary files every week.
26. Configure a user account with limited disk space using quotas.
27. Change the default shell for a user to `/bin/zsh`.
28. Set up SSH key-based authentication for a remote server.
29. Mount a USB drive manually and unmount it afterward.

## Archiving and Compression
30. Compress multiple files into a `.zip` archive.
31. Extract specific files from a `.tar.gz` archive without extracting the whole archive.
32. Split a large file into smaller chunks of 100 MB each.
33. Merge the chunks back into the original file.

## User and Group Management
34. Create a new group named `admins` and add a user to it.
35. Create a user account that expires after 30 days.
36. Lock and unlock a user account.
37. List all currently logged-in users and their activity.

## Advanced Search and Filters
38. Find all files in `/var/log` modified in the last 24 hours.
39. Search for a specific IP address in a log file and display the surrounding 5 lines.
40. Replace all occurrences of `http` with `https` in a file named `urls.txt`.
41. Identify and delete duplicate lines in a file.

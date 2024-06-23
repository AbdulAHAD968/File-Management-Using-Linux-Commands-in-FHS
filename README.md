# File Permissions in Linux

## Project Description

The research team at my organization needs to update the file permissions for certain files and directories within the projects directory. The permissions do not currently reflect the level of authorization that should be given. Checking and updating these permissions will help keep their system secure. To complete this task, I performed the following steps:

1. [Check file and directory details](#check-file-and-directory-details)
2. [Describe the permissions string](#describe-the-permissions-string)
3. [Change file permissions](#change-file-permissions)
4. [Change file permissions on a hidden file](#change-file-permissions-on-a-hidden-file)
5. [Change directory permissions](#change-directory-permissions)
6. [Summary](#summary)

## Check file and directory details

The following code demonstrates how I used Linux commands to determine the existing permissions set for a specific directory in the file system.

```sh
ls -la projects/

- 1st character: This character is either a `d` or hyphen (`-`) and indicates the file type. If it’s a `d`, it’s a directory. If it’s a hyphen (`-`), it’s a regular file.
- 2nd-4th characters: These characters indicate the read (`r`), write (`w`), and execute (`x`) permissions for the user. When one of these characters is a hyphen (`-`) instead, it indicates that this permission is not granted to the user.
- 5th-7th characters: These characters indicate the read (`r`), write (`w`), and execute (`x`) permissions for the group. When one of these characters is a hyphen (`-`) instead, it indicates that this permission is not granted for the group.
- 8th-10th characters: These characters indicate the read (`r`), write (`w`), and execute (`x`) permissions for other. This owner type consists of all other users on the system apart from the user and the group. When one of these characters is a hyphen (`-`) instead, that indicates that this permission is not granted for other.

## Change file permissions:

chmod o-w project_k.txt
ls -la projects/

---------------------------------------------------------------------

## Change file permissions on a hidden file:

chmod u-w .project_x.txt
chmod g-w .project_x.txt
chmod g+r .project_x.txt
ls -la projects/

---------------------------------------------------------------------

## Change directory permissions:

chmod g-x drafts/
ls -la projects/


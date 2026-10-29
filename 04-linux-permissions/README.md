# File Permissions in Linux

## Project Description
In this lab, I audited and updated file and directory permissions in Linux. The goal was to check current access levels against our security requirements and fix any overly permissive settings using the principle of least privilege.

---

## Check File and Directory Details
I ran `ls -la` to list all files, directories, and hidden files in the project folder, along with their permission strings. This brought up standard files like `project_k.txt`, a directory named `drafts`, and a hidden file named `.project_x.txt`.

---

## Describe the Permissions String
A 10-character string like `-rw-r--r--` breaks down as:
* **Position 1:** File type (`-` for regular file, `d` for directory).
* **Positions 2–4:** User/Owner permissions (`r` read, `w` write, `x` execute).
* **Positions 5–7:** Group permissions.
* **Positions 8–10:** Other users (everyone else).

---

## Change File Permissions
I noticed `project_k.txt` had write access enabled for "others". To fix this and prevent unauthorized edits, I ran:
```bash
chmod o-w project_k.txt

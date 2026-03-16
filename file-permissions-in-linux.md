# File Permissions in Linux 🐧

## Objective
Review and update file permissions for files and directories within
the `projects` directory to ensure they match the organization's
authorization requirements.

## Tools Used
- Linux CLI
- `ls -la` command
- `chmod` command

---

## Tasks

### 1️⃣ Check File and Directory Details
**Command used:**
```bash
ls -la /home/researcher2/projects
```

**Output revealed:**
- 1 subdirectory: `drafts`
- 1 hidden file: `.project_x.txt`
- 5 project files: `project_k.txt`, `project_m.txt`, `project_r.txt`, `project_t.txt`

---

### 2️⃣ Understanding the Permissions String
The 10-character permission string breaks down as follows:

```
- r w - r w - r - -
↑ ↑↑↑ ↑↑↑ ↑↑↑
| ||| ||| |||
| ||| ||| └── Other: read, no write, no execute
| ||| └────── Group: read, write, no execute
| └────────── User: read, write, no execute
└──────────── File type: - = file, d = directory
```

**Example — `project_t.txt` permissions: `-rw-rw-r--`**
| Entity | Read | Write | Execute |
|---|---|---|---|
| User | ✅ | ✅ | ❌ |
| Group | ✅ | ✅ | ❌ |
| Other | ✅ | ❌ | ❌ |

---

### 3️⃣ Remove Write Access from Other
**Issue:** `project_k.txt` had write access for `other` which violates policy.

**Command:**
```bash
chmod o-w project_k.txt
ls -la
```

**Result:** Write permission removed from `other` for `project_k.txt`

---

### 4️⃣ Change Permissions on Hidden File
**Issue:** `.project_x.txt` was archived — no one should have write access,
but user and group should retain read access.

**Command:**
```bash
chmod u-w,g-w,g+r .project_x.txt
ls -la
```

**Explanation:**
- `u-w` removes write from user
- `g-w` removes write from group
- `g+r` adds read to group

---

### 5️⃣ Change Directory Permissions
**Issue:** Only `researcher2` should have execute access to `drafts` directory.

**Command:**
```bash
chmod g-x drafts
ls -la
```

**Result:** Group execute permission removed. Only `researcher2` retains execute access.

---

## Summary
Successfully updated file permissions across the `projects` directory to
match organizational authorization requirements.

**Commands used:**
- `ls -la` — list all files including hidden with detailed permissions
- `chmod` — modify file and directory permissions

**Key takeaway:** Proper file permission management is a critical part of
least privilege enforcement and reducing attack surface in Linux environments.

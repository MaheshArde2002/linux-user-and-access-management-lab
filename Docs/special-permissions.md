
# Linux Special Permissions

## 1. SUID (Set User ID)

SUID on an executable file allows it to run with the file
owner's effective user ID, subject to system behavior.

```bash
chmod u+s program
ls -l program
```

The permission is represented by `s` in the owner's execute
position.

Do not use ordinary text files to demonstrate SUID behavior.
SUID on a non-executable file does not provide useful
privilege escalation.

## 2. SGID on a Directory

SGID on a directory causes newly created files and
subdirectories to inherit the directory's group on typical
Linux filesystems.

```bash
mkdir -p Sample
chgrp Developers Sample
chmod g+s Sample
ls -ld Sample
```

## 3. Sticky Bit on a Directory

The sticky bit restricts deletion and renaming of entries
in a shared writable directory. Typically, only the file
owner, directory owner, or root can remove an entry.

```bash
mkdir -p shared
chmod 1777 shared
ls -ld shared
```

The `/tmp` directory commonly uses the sticky bit.

## 4. Numeric Permission Examples

```bash
chmod 4755 executable-file
chmod 2750 shared-directory
chmod 1777 shared-directory
```

- 4: SUID
- 2: SGID
- 1: Sticky bit

Use these commands only on appropriate test files and
directories. The examples assume you understand the
security implications of executable files.

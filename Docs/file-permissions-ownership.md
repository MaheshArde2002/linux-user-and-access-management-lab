
# Linux File Permissions and Ownership

## 1. Create a Test File

```bash
touch sample.txt
ls -l sample.txt
```

## 2. Set Permissions to 640

```bash
chmod 640 sample.txt
ls -l sample.txt
```

Permission breakdown:

- Owner: read and write (6)
- Group: read (4)
- Others: no permissions (0)

## 3. Set Permissions Symbolically

```bash
chmod u=rw,g=r,o= sample.txt
```

## 4. Understand Permission Values

| Value | Permission |
|---|---|
| 0 | No permission |
| 1 | Execute |
| 2 | Write |
| 3 | Write + execute |
| 4 | Read |
| 5 | Read + execute |
| 6 | Read + write |
| 7 | Read + write + execute |

## 5. Change Owner

```bash
chown dev-rajesh sample.txt
```

## 6. Change Owner and Group

```bash
chown dev-rajesh:Developers sample.txt
```

## 7. Change Group Only

```bash
chgrp Developers sample.txt
```

## 8. Verify Ownership

```bash
ls -l sample.txt
stat sample.txt
```

## Security Note

Avoid using `chmod 777` as a routine fix.
Grant only the permissions required by the intended users.


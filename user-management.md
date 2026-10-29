
# Linux User Management

## 1. Create a User

```bash
useradd dev-rajesh
```

Creates a user with the default settings configured on the system.

## 2. Set a Password

```bash
 passwd dev-rajesh
```

Set a strong password when prompted.

## 3. Verify User Information

```bash
id dev-rajesh
getent passwd dev-rajesh
```

`id` displays the UID, primary GID, and supplementary groups.

`getent passwd` displays the account entry from the system's
configured account database.

## 4. Check the Home Directory

```bash
ls -ld /home/dev-rajesh
```

If the directory exists, this displays its permissions and ownership.

## 5. Modify a User

```bash
usermod -c "Developer Account" dev-rajesh
usermod -s /bin/bash dev-rajesh
```

The first command sets the account comment.
The second changes the login shell.

## 6. Verify the Login Shell

```bash
getent passwd dev-rajesh
```

The last field shows the configured login shell.

## 7. Switch User

```bash
su - dev-rajesh
whoami
pwd
exit
```

The `-` option starts a login shell and loads the user's
login environment.

## Important Note

On many RHEL/CentOS systems, `useradd` creates the home
directory according to the configured defaults. Verify it
rather than assuming it always exists.

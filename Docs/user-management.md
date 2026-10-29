
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

# Linux Group Management

## 1. Create a Group

```bash
groupadd Developers
```

## 2. Verify the Group

```bash
getent group Developers
grep '^Developers:' /etc/group
```

## 3. Add an Existing User to a Supplementary Group

```bash
usermod -aG Developers dev-rajesh
```

Use `-aG` to append the supplementary group without
replacing existing supplementary group memberships.

## 4. Verify Membership

```bash
id dev-rajesh
getent group Developers
groups dev-rajesh
```

## 5. Create a Second User and Group

```bash
useradd test-manoj
groupadd TestingTeam
usermod -aG TestingTeam test-manoj
```

## 6. Remove a User from a Supplementary Group

```bash
gpasswd -d dev-rajesh Developers
```

## Important Note

Linux group names are case-sensitive.

For example, `TestingTeam` and `Testingteam` are different names.

Existing login sessions may not immediately reflect updated
supplementary groups. Start a new login session to verify.

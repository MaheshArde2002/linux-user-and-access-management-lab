
# Linux User Session Management

## 1. Switch to Another User

```bash
su - dev-rajesh
whoami
pwd
```

## 2. Switch to a Second User

```bash
su - test-manoj
whoami
```

The target user's password is normally required unless
the caller is root or another permitted authentication
configuration applies.

## 3. Return to the Previous Shell

```bash
exit
```

## 4. Check Current User

```bash
whoami
id
groups
```

## 5. Check Logged-in Sessions

```bash
who
w
```

## 6. Run a Single Command as Another User

```bash
sudo -u dev-rajesh whoami
```

This runs the command with the specified user's identity
when sudo policy permits it.

## 7. Compare `su` and `su -`

- `su dev-rajesh`: switches user without fully initializing
  a login environment.
- `su - dev-rajesh`: starts a login shell and loads the
  target user's login environment.

## Practical Exercise

1. Log in as root or use an administrator account.
2. Switch to dev-rajesh.
3. Verify the current user.
4. Switch to test-manoj.
5. Verify the current user again.
6. Exit each shell and confirm the previous identity.

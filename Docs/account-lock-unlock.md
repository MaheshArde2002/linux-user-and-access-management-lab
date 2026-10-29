
# Linux Account Locking

## 1. Check Password Status

```bash
passwd -S test-manoj
```

The output commonly shows `LK` for a locked password
or `PS` for a password set, depending on the system.

## 2. Lock Password Authentication

```bash
passwd -l test-manoj
```

Locks the password hash.

## 3. Unlock Password Authentication

```bash
passwd -u test-manoj
```

Unlocks the password hash if it can be safely unlocked.

## 4. Verify the Status

```bash
passwd  -S test-manoj
```

## 5. Check Account Expiration

```bash
chage -l test-manoj
```

## Important Security Note

Locking a password does not necessarily disable every
authentication method or terminate existing sessions.

For a broader account restriction, investigate the account's
expiration settings, SSH configuration, and active sessions
according to the intended security policy.

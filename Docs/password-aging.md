
# Linux Password Aging

## 1. Check Current Policy

```bash
chage -l dev-rajesh
```

Displays password-change and account-expiration information.

## 2. Set Maximum Password Age

```bash
chage -M 90 dev-rajesh
```

Sets the maximum password age to 90 days.

## 3. Set Minimum Password Age

```bash
chage -m 1 dev-rajesh
```

Requires at least one day between password changes.

## 4. Set Expiry Warning

```bash
chage -W 7 dev-rajesh
```

Sets a warning period of seven days before password expiry.

## 5. Set Account Expiration Date

```bash
chage -E 2027-12-31 dev-rajesh
```

Sets the account expiration date.

## 6. Verify Changes

```bash
chage -l dev-rajesh
```

## Important Note

Password expiry and account expiry are different settings.

Password aging policies should follow your organization's
security requirements.

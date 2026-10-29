
# Linux Sudo Configuration

## 1. Check Sudoers Syntax

```bash
visudo -c
```

## 2. Inspect Sudo Access

```bash
sudo -l
sudo -l -U dev-rajesh
```

The second command inspects the privileges available to
the specified user. It generally requires administrator
privileges.

## 3. Check the Wheel Group

```bash
getent group wheel
grep -n 'wheel' /etc/sudoers
```

On many RHEL/CentOS installations, members of `wheel`
are permitted to use sudo when the relevant rule is enabled.

## 4. Grant Access Through a Dedicated File

Open a new sudoers drop-in file:

```bash
sudo visudo -f /etc/sudoers.d/dev-rajesh
```

Add this rule only if full administrator access is intended:

```text
dev-rajesh ALL=(ALL:ALL) ALL
```

Save and exit. Then validate:

```bash
sudo visudo -c
sudo -l -U dev-rajesh
```

## 5. Grant Limited Command Access

For example, to allow a user to run only the systemctl
status command for the SSH service, a rule may be written as:

```text
dev-rajesh ALL=(root) /usr/bin/systemctl status sshd
```

Check the actual executable path with `command -v systemctl`.
The rule must match the command path and arguments correctly.
Review the risks before granting command-specific privileges.

## Important Security Rules

- Use `visudo` to edit sudoers configuration.
- Validate the syntax before relying on a new rule.
- Keep an existing root or administrative session open
  until the new configuration has been tested.
- Avoid unrestricted `NOPASSWD: ALL` access.
- Do not edit `/etc/sudoers` with a normal text editor.



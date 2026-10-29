
# Linux Group Management

## 1. Create a Group

```bash
sudo groupadd Developers
```

## 2. Verify the Group

```bash
getent group Developers
grep '^Developers:' /etc/group
```

## 3. Add an Existing User to a Supplementary Group

```bash
sudo usermod -aG Developers dev-rajesh
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
sudo useradd test-manoj
sudo groupadd TestingTeam
sudo usermod -aG TestingTeam test-manoj
```

## 6. Remove a User from a Supplementary Group

```bash
sudo gpasswd -d dev-rajesh Developers
```

## Important Note

Linux group names are case-sensitive.

For example, `TestingTeam` and `Testingteam` are different names.

Existing login sessions may not immediately reflect updated
supplementary groups. Start a new login session to verify.

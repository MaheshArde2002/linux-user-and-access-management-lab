# Linux User and Access Management Lab

## About This Project

This project demonstrates practical Linux system administration
tasks performed in a RHEL/CentOS lab environment.

It covers user management, group administration, password
policies, account security, file permissions, special
permissions, sudo access, and user session management.

## Objectives

- Create, modify, and verify Linux users.
- Create groups and manage group membership.
- Configure password aging policies.
- Lock and unlock user password authentication.
- Manage file ownership and permissions.
- Understand SUID, SGID, and the sticky bit.
- Configure and validate sudo access safely.
- Switch between user accounts and inspect access rights.

## Technologies

- Operating System: RHEL/CentOS
- Shell: Bash
- Administration tools: useradd, usermod, groupadd,
  passwd, chage, chmod, chown, sudo, visudo, id, getent

## Project Structure

- docs/: Command explanations and practical exercises.
- scripts/: Reusable administration scripts.
- examples/: Example sudoers rules and service-account notes.
- screenshots/: Evidence of completed lab exercises.

## Lab Users

- dev-rajesh
- test-manoj

These are example accounts created for the lab.

## Prerequisites

- A RHEL/CentOS virtual machine.
- Root access or a user with appropriate sudo privileges.
- Basic Linux command-line knowledge.

## How to Use

1. Clone this repository.
2. Read the relevant guide in the docs directory.
3. Review the script before executing it.
4. Run administrative commands only in a test VM.
5. Capture screenshots of successful results.

## Safety Notes

- Never commit passwords, private keys, or other secrets.
- Do not grant unnecessary sudo privileges.
- Validate sudoers configuration with visudo.
- Avoid setting permissions to 777 without a specific need.
- Test account changes in a virtual machine.

## Learning Outcome

This lab demonstrates practical understanding of Linux
users, groups, permissions, and access control.

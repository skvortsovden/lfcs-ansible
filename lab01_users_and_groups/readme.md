# Linux Users and Groups – Practice Lab (Provisioned via Ansible)

## Provisioning

Run the playbook to create the practice environment:

```bash
ansible-playbook -i inventory.ini lab01_users_and_groups/users_and_groups.yaml
```

This sets up:

* Group: `developers`
* Users: `dev1` to `dev10`, all in group `developers`
* Bash shell, home directories

After the playbook completes, SSH into the target host(s) and perform the exercises manually.

---

## Linux Exercises

### 1. List All Local Users

**Task:**
List all users present on the system.

**Validation:**
Ensure `dev1` to `dev10` appear in the list.

---

### 2. Inspect Group Membership of Users

**Task:**
Check which groups `dev1` through `dev5` belong to.

**Validation:**
Verify each is a member of the `developers` group.

---

### 3. Add a User to an Additional Group

**Task:**
Create a new group called `testers`. Add `dev1` to that group as a secondary group.

**Validation:**
Confirm that `dev1` is a member of both `developers` and `testers`.

---

### 4. Create a New User With a Disabled Password

**Task:**
Create a new user called `nopass` with a locked password.

**Validation:**
Confirm the account exists and cannot be used for login until a password is set.

---

### 5. Set Login Passwords for Users

**Task:**
Set individual passwords for `dev1` through `dev10`.

**Validation:**
Verify that each user can successfully log in with their password.

---

### 6. Lock and Unlock a User Account

**Task:**
Lock `dev3`'s account, then unlock it again.

**Validation:**
While locked, the user cannot log in. After unlocking, login should succeed.

---

### 7. Set an Expiration Date for a User

**Task:**
Set `dev4` to expire on a future date (e.g., end of the year).

**Validation:**
Verify that the expiration date is correctly applied and visible in account details.

---

### 8. Create a System User Without a Home Directory

**Task:**
Create a system user named `sysuser` without a home directory and with no login shell.

**Validation:**
Ensure the user exists, has no home directory, and cannot log in.

---

### 9. Remove a User and Their Home Directory

**Task:**
Remove `dev10` and delete their home directory.

**Validation:**
Check that the user no longer exists and their home folder has been removed.

---

### 10. Create a Shared Group Directory

**Task:**
Create a directory `/opt/shared` with group `developers` as the owner. Set group sticky permissions so that all files remain owned by the group.

**Validation:**
Verify group ownership and that new files created by group members inherit the group.

## How to Run Cleanup

From the root of the repo:

```bash
ansible-playbook -i inventory.ini lab01_users_and_groups/users_and_groups_cleanup.yaml
```

This will:

* Delete all lab-created users and their home directories
* Remove associated groups
* Clean up the shared directory

Let me know if you'd like this to be more dynamic (e.g. skipping missing users silently or logging what's removed).

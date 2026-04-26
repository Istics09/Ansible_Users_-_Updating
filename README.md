# Ansible User Management Playbooks

This repository contains Ansible playbooks designed to automate user lifecycle management, including creation, deletion, and environment configuration.

## 📂 Project Structure

* **`creating_users_&_passwords.yml`**: Bulk creates users with passwords and group assignments.
* **`create_user_&_password.yml`**: Handles individual user creation.
* **`delete_user_&_password.yml`**: Removes users from the target systems.
* **`users.yml`**: *(Excluded via .gitignore)* Contains the list of users and their credentials.
* **`hosts.ini`**: *(Excluded via .gitignore)* The inventory file listing target servers.

## 🚀 Usage

### 1. Configuration
Ensure your `users.yml` file is populated with the desired users in the following format:

```yaml
users:
  - name: 'example_user'
    pass: 'secure_password'
    grp: 'sudo'
```

# To create users and set up their environment:
```
ansible-playbook -i hosts.ini creating_users_&_passwords.yml -K
```

### To delete users:
```
ansible-playbook -i hosts.ini delete_user_&_password.yml -K
```
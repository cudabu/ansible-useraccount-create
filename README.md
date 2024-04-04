# ansible-useraccount-create

## Generate a secure password

Create a random password, we can set the user account to force change on first login.

```
openssl passwd -6 -salt xyz yourpassword
```

## Encrypt password in vault

```
ansible-vault encrypt_string 'your_hashed_password_here' --name 'vault_local_user_password'
```

## Run the playbook

```
ansible-playbook create_local_user.yml --vault-password-file /path/to/vault_password_file

```

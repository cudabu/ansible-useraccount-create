# ansible-useraccount-create

## Generate a secure password

Create a random password

```
openssl passwd -6 -salt xyz yourpassword
```

## Encrypt password in vault

```
ansible-vault encrypt_string 'your_hashed_password_here' --name 'vault_local_user_password'
```

## Run the playbook

```
ansible-playbook create_local_user.yaml --vault-password-file /path/to/vault_password_file

```


## Additional thoughts

- Skip the vault all together, set a generic password and force password change on login.
- Automate through a Jira ticket and use a username field in a ticket as the username.
- The same principles here could be used to provide access to the wheel/sudo group temporarily. Use chron to remove the account after N minutes I suppose.
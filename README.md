
# for generate token, can run:

### Method 1: using vaultwarden cli

```
# command:
./vaultwarden hash "your_admin_token"

# Result:
ADMIN_TOKEN="$argon2id$v=19$m=4096,t=3,p=4$WDRFTDFnUDljQk1OSVEyNnhhYy9hemt5NXNxeXJCekZOUDNnT2p2VXkzVT0$wLHUHkHeUe671zz3qQh/9Y6F07rO9vUO5DzFFZ/MTWQ"

# Replace: $ => $$
ADMIN_TOKEN=$$argon2id$$v=19$$m=65540,t=3,p=4$$DUsO9sEkw482mRpuPPOMqb8vYkGfnxvw7AoUpuY/uzg$$fDqMvc3R93974UJegaWt/1lY5lSeA6I2PVVkVz90fjQ
```

### Method 2: using Argon2:
```

# command:
echo -n "MySecretPassword" | argon2 "$(openssl rand -base64 32)" -e -id -t 3 -p 4

# Result:
ADMIN_TOKEN="$argon2id$v=19$m=4096,t=3,p=4$WDRFTDFnUDljQk1OSVEyNnhhYy9hemt5NXNxeXJCekZOUDNnT2p2VXkzVT0$wLHUHkHeUe671zz3qQh/9Y6F07rO9vUO5DzFFZ/MTWQ"

# Replace: $ => $$
ADMIN_TOKEN=$$argon2id$$v=19$$m=65540,t=3,p=4$$DUsO9sEkw482mRpuPPOMqb8vYkGfnxvw7AoUpuY/uzg$$fDqMvc3R93974UJegaWt/1lY5lSeA6I2PVVkVz90fjQ
```

# provision stack

- ### create client.pem key: the key has public key located in the server.

- ### prerequisite:
> export VAULT_PASSWORD=my_vault_password

> chmod +x .vault_pass.py

- ### provision observer
> ansible-playbook provision.yaml -t vaultwarden

# Debianbox
Using Packer and Ansible to build a custom Debian QEMU image.

## Build Instructions
Download the Debian net install iso and place it in the project root. Pass the correct `iso_url` and `iso_checksum` variables to `packer build`.
```bash
packer init debianbox.pkr.hcl 
packer build -var 'iso_url=<debian iso>' -var 'iso_checksum=<iso checksum>' debianbox.pkr.hcl
```

### Adding SSH Keys
The `common` role adds ssh key for the default user (`username` variable). It looks for the public key defined in `ssh_public_key_file`. This can be overriden.
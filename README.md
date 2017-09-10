# Intro to Roots.io Example Project

This repo is an example of using Trellis and Bedrock from the Roots.io family of projects.

The contents of this repo are pretty specific to the talk given at the PDX 2017 WordCamp. If you are wanting a more detailed example, checkout out the official [Roots Example Repo](https://github.com/roots/roots-example-project.com).

## Viewing Production

If you are wanting to create your own 'passionsplay.com' site hosted somewhere like DigitalOcean, using this repo, then you can edit your local `hosts` file to point to the IP given when the server is initially created.

For the presentation, I was using an IP of `138.68.247.132`. Using that as an example, I would add something like:

```
138.68.247.132 passionsplay.com
```

to my hosts file. After saving the hosts file, any browsers should be directed to this new `passionsplay.com` site.

## Viewing Files Protected by Ansible Vault

Later commits involving production make use of Ansible's Vault feature. This means that sensitive information like database passwords and salts are encrypted.

In order to view this repo's encrypted vault files:

1. Create `.vault_pass` file sibling to `ansible.cfg` which contains `vaultpassword` on one line

You should now be able to decrypt / edit encrypted vault files by:

```
user@laptop:example.com/trellis $ ansible-vault decrypt group_vars/production/vault.yml
user@laptop:example.com/trellis $ ansible-vault edit group_vars/production/vault.yml
```


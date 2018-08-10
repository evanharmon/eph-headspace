# ANSIBLE VAULT

## Install Ansible
`brew install ansible`

## Check if Ansible is installed
`ansible --version`

## Create Password File
Use a password generator to create a long password string
`touch $HOME/.vault_pass.txt && chmod 640 $HOME/.vault_pass.txt`
`vi $HOME/.vault_pass.txt` and paste in text, save and quit.

## View Ansible Vault encoded data
`ansible-vault view config/envs/qa.env`

## Edit Ansible Vault encoded data
`ansible-vault edit config/envs/development.env`

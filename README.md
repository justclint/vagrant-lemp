# vagrant-lemp-project-wrapper
This is a VM system wrapper for new projects. To use, download this repository. Do not clone unless contributing back.

## Requirements
- Vagrant
- Vagrant hostupdater
- Virtualbox

## Instructions
1. Make a copy of playbooks/roles/project-template and rename it to your project name.
2. In playbooks/vagrant.yml under vars, add your project name.
3. Run `vagrant up`

Your local environment is now setup and can be veiwed at your-project-name.local

When logged into the VM, your project files are in /var/www

This is the vanilla setup. Depending on your application, you may need to make
configuration adjustments.

Once you confirm your project is working commit this to your new repository and
replace the contents of this readme file.

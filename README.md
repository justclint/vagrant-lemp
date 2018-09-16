# vagrant-lemp-project-wrapper

This is a VM system wrapper for PHP projects. To use, download this repository. Do not clone unless contributing back.

- Make a copy of playbooks/roles/project-template and rename it to your project name.
- In playbooks/vagrant.yml under vars, add your project name.
- Run `vagrant up`
- Your local environment is now setup and can be veiwed at your-project-name.local

When logged into the VM, your project files are in /var/www

This is the vanilla setup. Depending on your application, you may need to make
config adjustments for roles like nginx, php or mysql.

Once you confirm your project is working commit this to your new repository.

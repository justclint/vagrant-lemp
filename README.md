# vagrant-lemp-project-wrapper

This is a VM system wrapper for PHP projects. To use, download this repository. Do not clone unless contributing back.

- Make a copy of playbooks/roles/project-template and rename it to your project name.
- In playbooks/vagrant.yml under roles, replace project-template with your project name.
- Run `vagrant up`
- Visit your-project-name.local
- Add your application files in the project directory.

This is the vanilla setup. Depending on your application, you may need to make
config adjustments for roles like nginx, php or mysql.

Once you confirm your project is working commit this to your new repository.

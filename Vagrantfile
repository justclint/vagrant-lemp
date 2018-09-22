# Optimized for Vagrant 1.7 and above.
Vagrant.require_version ">= 1.7.0"

# Choose your project type: php or angular
# @todo need to get this setting into plays or single config vars file.
config_type = "php"
config_file = "playbooks/project-#{config_type}.yml"
vagrant_config = YAML.load_file(File.join(File.dirname(__FILE__), "#{config_file}"))

Vagrant.configure(2) do |config|

  config.vm.box = "bento/ubuntu-16.04"
  config.vm.synced_folder "./project", "/var/www/#{vagrant_config[0]["vars"]["project_name"]}"

  # Disable the new default behavior introduced in Vagrant 1.7, to
  # ensure that all Vagrant machines will use the same SSH key pair.
  # See https://github.com/mitchellh/vagrant/issues/5005
  config.ssh.insert_key = false

  # Run Ansible from the Vagrant VM
  config.vm.provision "ansible_local" do |ansible|
    ansible.verbose = "vv"
    ansible.playbook = "#{config_file}"
  end

  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "private_network", ip: "192.168.50.4"
  config.vm.hostname = "#{vagrant_config[0]["vars"]["project_name"]}.local"
  config.vm.post_up_message = "You can now view your project at http://#{vagrant_config[0]["vars"]["project_name"]}.local"

  # Config VirtualBox.
  config.vm.provider "virtualbox" do |v|
    v.name = config.vm.hostname
  end
end

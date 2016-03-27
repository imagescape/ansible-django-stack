# vagrant up xenial
# vagrant up trusty

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|


  config.vm.define 'xenial', autostart: false do |box|
      box.vm.box = "ubuntu/xenial64"
      box.vm.network "forwarded_port", guest: 80, host: 8080
      box.vm.provision :ansible do |ansible|
        ansible.playbook = "ansible/playbook-all.yml"
        #ansible.playbook = "ansible/playbooks/add-user.yml"
        ansible.verbose = "vvvv"
        ansible.extra_vars = {
        #    "user_to_add" => "testb"
             "install_nginx" => true,
             "install_ntp" => true,
             "install_unattended_updates" => true,
             "install_postgis" => true,
             "install_postgres" => true,
             "install_mysql" => true,
             "site_name" => "jazstudios",

             # Ubuntu 16.04 settings
             "ansible_python_interpreter" => "/usr/bin/python2.7",
             #"postgres_version" => "9.5",
             #{}"postgis_version" => "2.2",
             "python_version" => "python3.5",
        }
        ansible.sudo = true
        ansible.limit = "all"
      end
  end

  config.vm.define 'trusty', autostart: false do |box|
      box.vm.box = "ubuntu/trusty64"
      box.vm.network "forwarded_port", guest: 80, host: 8081
      box.vm.provision :ansible do |ansible|
        ansible.playbook = "ansible/playbook-all.yml"
        #ansible.playbook = "ansible/playbooks/add-user.yml"
        ansible.verbose = "vvvv"
        ansible.extra_vars = {
        #    "user_to_add" => "testb"
             "install_nginx" => true,
             "install_ntp" => true,
             "install_unattended_updates" => true,
             "install_postgis" => true,
             "install_postgres" => true,
             "install_mysql" => true,
             "site_name" => "jazstudios",
             "python_version" => "python3.4",
        }
        ansible.sudo = true
        ansible.limit = "all"
      end
  end


end

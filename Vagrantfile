VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  #config.vm.box = "centos/7"

  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "ansible/site.yml"
    ansible.verbose = "vvvv"
    ansible.extra_vars = {}
    ansible.sudo = true
    ansible.limit = "all"
  end
end

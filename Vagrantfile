# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|
  config.vm.define :db do |db_config|
    db_config.vm.box = 'ubuntu/trusty64'
    db_config.vm.hostname = 'db'
    db_config.vm.network :private_network, ip: '10.0.15.10'

    db_config.vm.provider 'virtualbox' do |vb|
      vb.memory = '512'
    end

    db_config.vm.provision :ansible do |ansible|
      ansible.playbook = 'mysqlserver.yml'
      ansible.groups = { dbservers: [:db] }
    end
  end

  config.vm.define :web do |web_config|
    web_config.vm.box = 'ubuntu/trusty64'
    web_config.vm.hostname = 'web'
    web_config.vm.network :private_network, ip: '10.0.15.11'
    web_config.vm.network 'forwarded_port', guest: 80, host: 8080

    web_config.vm.provider 'virtualbox' do |vb|
      vb.memory = '512'
    end

    web_config.vm.provision :ansible do |ansible|
      ansible.playbook = 'railsserver.yml'
      ansible.groups = { webservers: [:web] }
    end
  end
end

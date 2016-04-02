# coding: utf-8
# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
  config.vm.provider 'virtualbox'
  config.vm.box = 'centos/7'
  config.vm.box_version = '>= 1602.02'

  config.vm.synced_folder '.', '/vagrant'
  config.vm.network 'private_network', ip: '192.168.33.10'
  config.vm.provision :ansible_local do |ansible|
    ansible.playbook = 'provision.yml'
    ansible.inventory_path = 'hosts'
    ansible.limit = 'all'
    ansible.verbose        = true
    ansible.install        = true
  end
end

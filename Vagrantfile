# -*- mode: ruby -*-
# vi: set ft=ruby :

REQUIRED_PLUGINS = %w(vagrant-vbguest)
exit unless REQUIRED_PLUGINS.all? do |plugin|
  Vagrant.has_plugin?(plugin) || (
  puts "The #{plugin} plugin is required. Please install it with:"
  puts "$ vagrant plugin install #{plugin}"
  false
  )
end

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.ssh.forward_agent = true
  config.vm.box = "hubotio/hubot-development-environment"
  config.vm.hostname = "hubot-dev"
  config.vm.network "forwarded_port", guest: 8080, host: 8080
end

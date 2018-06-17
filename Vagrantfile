Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "forwarded_port", guest:25565, host:25565, auto_correct: true
  config.vm.synced_folder "/home/vazogg/Vagrant/Mail_Vagrant", "/var/sync/"
  config.vm.hostname = "mail"
  # config.ssh.pty = true
config.vm.provider "virtualbox" do |vb|
  vb.memory = "1024"  
  vb.name = "mail"
end
config.vm.provision "shell", inline: <<-SHELL
	sudo apt-get update
SHELL
end
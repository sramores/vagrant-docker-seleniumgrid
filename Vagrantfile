Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "forwarded_port", guest: 4444, host: 4444 
  config.vm.network "forwarded_port", guest: 32700, host: 32700 
  config.vm.network "forwarded_port", guest: 32701, host: 32701 
  
  config.vm.provider "virtualbox" do |vb|
	vb.name = "selenium-grid"
	vb.memory = "4096"
	vb.cpus = 1
  end
	
	config.vm.provision :docker
	config.vm.provision :docker_compose, yml: "/vagrant/selenium-grid/docker-compose.yml", run: "always"
end
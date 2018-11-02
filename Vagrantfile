Vagrant.configure("2") do |config|

	(5..6).each do |i|

		config.vm.define "node#{i}" do |node|

		node.vm.box = "ubuntu/trusty64"

		node.disksize.size = '20GB'

		node.vm.hostname="node#{i}"

		node.vm.network "private_network", ip: "192.168.56.#{i}"

		node.vm.synced_folder "~/Documents/vag-share", "/home/vagrant/share"

		node.vm.provider "virtualbox" do |v|

			v.name = "node#{i}"

			v.memory = 2048
			
			v.cpus = 2
		end
		
		node.vm.provision "shell", path: "bootstrap.sh"

		end
	end
end
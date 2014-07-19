#vagrant-orawls-12.1.3

##Details
- Oracle Linux 6.5 vagrant box
- Puppet 3.6.2
- Vagrant >= 1.41 + vagrant-librarian-puppet
- Oracle Virtualbox >= 4.3.6 

creates a 12.1.3 WebLogic cluster ( admin, node1, node2 )

##Setup
Add the Oracle binaries to /software share

edit Vagrantfile and update the software share
- admin.vm.synced_folder "/Users/edwin/software", "/software"
- node1.vm.synced_folder "/Users/edwin/software", "/software"
- node2.vm.synced_folder "/Users/edwin/software", "/software"

###software
-jdk-7u51-linux-x64.tar.gz
-fmw_12.1.3.0.0_wls.jar

###Vagrant librarian puppet plugin
-vagrant plugin install vagrant-librarian-puppet

###Startup the images
-vagrant up admin
-vagrant up node1
-vagrant up node2



###Setup puppet modules from the desktop
-gem install librarian-puppet
-cd puppet
-rm -rf modules
-librarian-puppet install or librarian-puppet outdated

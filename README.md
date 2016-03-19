# Drupal 8 - Pattern Lab Node - Twig

This project will help guide the development of Pattern Lab Node + Twig and the Drupal 8 module available to make Drupal aware of these Twig files.
 
## Requirements
 
1. Update homebrew: `brew update`
1. Ansible 2.0.0: `brew install ansible`
1. Vagrant 1.8.1
1. Vagrant Hosts Updater: `vagrant plugin install vagrant-hostsupdater`
1. VirtualBox 5.0.14
 
## Installation

Run all commands from root: 

Clone repo:

```
git clone git@github.com:geerlingguy/drupal-vm.git
```

Setup:

```
cd drupal-vm
ln -s ../config.yml ./config.yml
sudo ansible-galaxy install -r provisioning/requirements.yml --force
vagrant up
```
 
Install other repo:

```
cd dev 
git clone git@github.com:phase2/patternlab_connector.git
cd ..
```

Setup:

```
mkdir -p dev/drupal/modules/custom
cd dev/drupal/modules/custom
ln -s ../../../patternlab_connector ./patternlab_connector
cd -
```

Install 3rd repo: 

```
cd dev 
git clone git@github.com:phase2/patternlab-node.git
```

## Troubleshooting

If you use P2 devtools, it is recommended that you work with Vagrant and Vagrant-based projects outside the `/Users` directory. The following commands should make `/opt/vms` to hold Vagrant files and `/opt/project` to move the d8pltwig folder to.
 
1. Add the following to your .bashrc/.zshrc

    	 # Vagrant updates for docker-tools
    	 export VAGRANT_HOME=/opt/vms
    	 
1. Immediately update your terminal: 

		   source ~/.bashrc
		
	or 

		   source ~/.zshrc
    
1. Make the directories and set 

	     sudo mkdir /opt/projects
	     sudo mkdir /opt/vms
	     sudo chmod -R 0755 /opt/projects
	     sudo chmod -R 0755 /opt/vms
	     sudo chown -R $USER: /opt/projects
	     sudo chown -R $USER: /opt/vms
	    
1. Move the entire `d8pltwig` project to `/opt/projects/d8pltwig`
1. Destroy the Vagrant box and re-up it from within `d8pltwig/drupal-vm`:

		vagrant destroy && vagrant up

Testing 123

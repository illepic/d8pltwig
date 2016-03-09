# Drupal 8 - Pattern Lab Node - TWig

This project will help guide the development of Pattern Lab Node + Twig and the Drupal 8 module available to make Drupal aware of these Twig files.
 
## Requirements
 
1. Ansible 2.0.0: `brew install ansible`
1. Vagrant Hosts Updater: `vagrant plugin install vagrant-hostsupdater`
1. VirtualBox 5.0.14
1. Vagrant 1.8.1
 
## Installation
 
1. From root: `git clone git@github.com:geerlingguy/drupal-vm.git`
    
    cd drupal-vm
    ln -s ../config.yml ./config.yml
    sudo ansible-galaxy install -r provisioning/requirements.yml --force
    vagrant up
    
1. From root: `cd dev && git clone git@github.com:phase2/patternlab_connector.git`
    
    mkdir dev/drupal/modules/custom
    cd dev/drupal/modules/custom
    ln -s .../../../patternlab_connector ./patternlab_connector
    
1. From root: `cd dev && git clone git@github.com:phase2/patternlab-node.git`

An Ansible role for installing Consul on Ubuntu.

### Default versions

Ubuntu 16.04
Consul 0.7.0

### Testing

A Vagrant/VirtualBox environment is provided in the /examples directory.  To get started:

1. Install Vagrant, Virtualbox, and Ansible
1. Change your directory into 'examples'
1. Run the 'install_role_requirements.sh' script.  This add any additional role dependencies.
1. Run 'vagrant up' to bring up the VM.

### Additional notes

- For Vagrant installs, dependencies (such as the Consul install executable) are downloaded once and cached locally.
- Each role in this Ansible playbook will check the version of each application before installing, and will not re-install if the installed version is the desired version.  This speeds up reprovisioning.
- To reprovision, use the 'vagrant provision' command.

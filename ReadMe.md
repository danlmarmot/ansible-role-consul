An Ansible role for installing Consul on Ubuntu.

### Default versions

Ubuntu 16.04
Consul 0.7.0
Vagrant 1.8.6
Ansible 2.1.2

### Testing

A Vagrant/VirtualBox environment is provided in the /examples directory.  To get started:

1. Install Vagrant, Virtualbox, and Ansible
1. Change your directory into 'examples'
1. Run the 'install_role_requirements.sh' script.  This add any additional role dependencies.
1. Run 'vagrant up' to bring up the VM.

#### Verifying the Consul UI
Consul UI works over Consul's HTTP bindings, which are localhost only.  You can use SSH to make a little tunnel
over to a Vagrant box, though--to do that, use this command:

    vagrant ssh node00 -- -L 8500:127.0.0.1:8500

Then in a browser on your Vagrant host, go to `http://127.0.0.1:8500/ui/` to see the Consul UI.

### Additional notes

- For Vagrant installs, dependencies (such as the Consul install executable) are downloaded once and cached locally.
- Each role in this Ansible playbook will check the version of each application before installing, and will not re-install if the installed version is the desired version.  This speeds up reprovisioning.
- To reprovision, use the 'vagrant provision' command.

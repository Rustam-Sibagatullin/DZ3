необходимо скопировать нужный vagrant file:
git clone https://gitlab.com/otus_linux/stands-03-lvm



1. Необходимо установить plug-in scp для vagranta. Требуется для обмена файлами между хостовой машиной и vagrant-ом.

статус до устновки:

		~/DZ3/stands-03-lvm$ vagrant 
		Usage: vagrant [options] <command> [<args>]

		    -v, --version                    Print the version and exit.
		    -h, --help                       Print this help.

		Common commands:
		     box             manages boxes: installation, removal, etc.
		     cloud           manages everything related to Vagrant Cloud
		     destroy         stops and deletes all traces of the vagrant machine
		     global-status   outputs status Vagrant environments for this user
		     halt            stops the vagrant machine
		     help            shows the help for a subcommand
		     init            initializes a new Vagrant environment by creating a Vagrantfile
		     login           
		     package         packages a running vagrant environment into a box
		     plugin          manages plugins: install, uninstall, update, etc.
		     port            displays information about guest port mappings
		     powershell      connects to machine via powershell remoting
		     provision       provisions the vagrant machine
		     push            deploys code in this environment to a configured destination
		     rdp             connects to machine via RDP
		     reload          restarts vagrant machine, loads new Vagrantfile configuration
		     resume          resume a suspended vagrant machine
		     snapshot        manages snapshots: saving, restoring, etc.
		     ssh             connects to machine via SSH
		     ssh-config      outputs OpenSSH valid configuration to connect to the machine
		     status          outputs status of the vagrant machine
		     suspend         suspends the machine
		     up              starts and provisions the vagrant environment
		     upload          upload to machine via communicator
		     validate        validates the Vagrantfile
		     version         prints current and latest Vagrant version
		     winrm           executes commands on a machine via WinRM
		     winrm-config    outputs WinRM configuration to connect to the machine

		For help on any individual command run `vagrant COMMAND -h`

установка:

		~/DZ3/stands-03-lvm$ vagrant plugin install vagrant-vbguest
		Installing the 'vagrant-vbguest' plugin. This can take a few minutes...
		Fetching: micromachine-3.0.0.gem (100%)
		Fetching: vagrant-vbguest-0.23.0.gem (100%)
		Installed the plugin 'vagrant-vbguest (0.23.0)'!

		~/DZ3/stands-03-lvm$ vagrant plugin install vagrant-scp
		Installing the 'vagrant-scp' plugin. This can take a few minutes...
		Fetching: vagrant-scp-0.5.7.gem (100%)
		Installed the plugin 'vagrant-scp (0.5.7)'!

проверка:


		~/DZ3/stands-03-lvm$ vagrant
		Usage: vagrant [options] <command> [<args>]

		    -v, --version                    Print the version and exit.
		    -h, --help                       Print this help.

		Common commands:
		     box             manages boxes: installation, removal, etc.
		     cloud           manages everything related to Vagrant Cloud
		     destroy         stops and deletes all traces of the vagrant machine
		     global-status   outputs status Vagrant environments for this user
		     halt            stops the vagrant machine
		     help            shows the help for a subcommand
		     init            initializes a new Vagrant environment by creating a Vagrantfile
		     login           
		     package         packages a running vagrant environment into a box
		     plugin          manages plugins: install, uninstall, update, etc.
		     port            displays information about guest port mappings
		     powershell      connects to machine via powershell remoting
		     provision       provisions the vagrant machine
		     push            deploys code in this environment to a configured destination
		     rdp             connects to machine via RDP
		     reload          restarts vagrant machine, loads new Vagrantfile configuration
		     resume          resume a suspended vagrant machine
		     scp             copies data into a box via SCP
		     snapshot        manages snapshots: saving, restoring, etc.
		     ssh             connects to machine via SSH
		     ssh-config      outputs OpenSSH valid configuration to connect to the machine
		     status          outputs status of the vagrant machine
		     suspend         suspends the machine
		     up              starts and provisions the vagrant environment
		     upload          upload to machine via communicator
		     validate        validates the Vagrantfile
		     vbguest         plugin: vagrant-vbguest: install VirtualBox Guest Additions to the machine
		     version         prints current and latest Vagrant version
		     winrm           executes commands on a machine via WinRM
		     winrm-config    outputs WinRM configuration to connect to the machine

		For help on any individual command run `vagrant COMMAND -h`


2. запускаем loging:

		[vagrant@lvm ~]$ script
		Script started, file is typescript
		[vagrant@lvm ~]$ pwd
		/home/vagrant
		[vagrant@lvm ~]$ ls -l
		total 0
		-rw-rw-r--. 1 vagrant vagrant 0 Feb 11 13:10 typescript

3. останавливаем:

		vagrant@lvm ~]$ exit
		exit
		Script done, file is typescript
		[vagrant@lvm ~]$ ls -l
		total 4
		-rw-rw-r--. 1 vagrant vagrant 1623 Feb 11 13:11 typescript


4. Смотрим имя:

		~/DZ3/stands-03-lvm$ vagrant global-status
		id       name          provider   state   directory                                      
		-----------------------------------------------------------------------------------------
		5e43e64  kernel-update virtualbox running /home/rustam3/manual_kernel_update             
		185de88  default       virtualbox running /home/rustam3/manual_kernel_update/packer/test 
		5a91c3e  otuslinux     virtualbox running /home/rustam3/DZ2/stands-02-disks              
		a0f0d0a  lvm           virtualbox running /home/rustam3/DZ3/stands-03-lvm   

5. скачиваем файл:

		~/DZ3/stands-03-lvm$ vagrant scp lvm:/home/vagrant/typescript typescript
		Warning: Permanently added '[127.0.0.1]:2222' (ECDSA) to the list of known hosts.
		typescript                                                                                                                            100% 1623     	1.8MB/s   00:00    

		~/DZ3/stands-03-lvm$ ls -l
		итого 12
		-rw-r--r-- 1 rustam3 rustam3  109 фев 11 16:07 README.md
		-rw-r--r-- 1 rustam3 rustam3 1623 фев 11 18:26 typescript
		-rw-r--r-- 1 rustam3 rustam3 2417 фев 11 16:07 Vagrantfile






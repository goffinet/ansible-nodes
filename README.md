# ansible-nodes

ansible playbooks to configure KVM Ubuntu nodes lab

## Usage

* Clone this repo and test the Ansible connectivity

  ```
  git clone https://github.com/goffinet/ansible-nodes
  cd ansible-nodes
  ansible all -m ping
	ansible-playbook -i hosts main.yml
  ```

## Prereqs

* Install virt-scripts and prepare your Host for KVM/libvirt

  ```
	git clone https://github.com/goffinet/virt-scripts
	sudo ~/virt-scripts/autoprep.sh
  ```

* Download the base image and put it in /var/lib/libvirt/images/.

	 ```
	 curl -O https://s3.fr-par.scw.cloud/getimages/ubuntu1804.qcow2
	 sudo mv ubuntu1804.qcow2 /var/lib/libvirt/images/ubuntu1804.qcow2
	 ```

* Create 5 Ubuntu nodes

  ```
  for x in {1..5} ; do sudo ~/virt-scripts/define-guest-image.sh node$x ubuntu1804 ; done
  ```

## Enjoy with Ansible !

Set Up Ansible
=================

1- install ansible in controller server : 

.. code-block:: bash

    sudo apt install ansible

then set the secure shell between controller and node .make an ssh key with passphrase send the public key to the node 

.. code-block:: bash 

    ansible-copy-id key.pub <node-ipaddress>

test the ssh to the node .

then make another ssh key only for ansible with out an passphrase and send the public key to the node .

.. note:: 

    the first ssh key is the defualt key to ssh to the node.you could speciefy which key to make ssh by:

.. code-block:: bash

    ssh -i ~/.ssh/ansible <node-ipadress>

.. note::

    check the content of authorizedkey file in node side to make sure the contents of ansible.pub and defualtkey.pub is there.

now lets set the inventory file which contains the host ip addresses.

in the inventory file or hosts file which is defualt inventory file in /etc/ansible/hosts .

put the nodes's ip addresses in hosts file .

.. note:: 

    you could put all ip addresses in one group with a tag like : 

[dbservers]
ipaddress-server1
ipaddress-server2
ipaddress-server3

in ansible.cfh file set the inventory file as inventory = hosts and speciefy the Private key :

private_key_file = ~/.ssh/ansible

so ansible use this key by defualt to ssh to the node servers.

now lets test the reachability of nodes with this command : 

.. code-block:: bash
    
    ansible all -m ping 

the result should be `pong`.
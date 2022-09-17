
Write playbook 
==================


playbook contains instructions that should be played in the node servers such as install or 
updating packages automatically with out accessing derictively to the node servers.


playbook is written in yaml form which is so simple to read and understand to human.
it start with --- and contains the name of the group or hosts on which it should played.


.. code-block:: yaml

    ---
    - hosts: dbservers
        sudo: yes
        tasks:
        - name: install apache2
            apt: name=apache2 update_cache=yes state=latest

this playbook install and update apache2 . 


so lets check the syntax of the playbook .

.. code-block:: bash

    ansible-playbook nameofthefile.yml --syntax-check

then if the result was ok playthe file with :

.. code-block:: bash

    ansible-playbook nameofthefile.yml 


the result should be something like this if it was successfull:

.. code-block:: console

    PLAY [apache] ******************************************************************

    TASK [Gathering Facts] *********************************************************
    ok: [secondary_server_ip]

    TASK [install apache2] *********************************************************

    changed: [secondary_server_ip]

    PLAY RECAP *********************************************************************
    secondary_server_ip               : ok=2    changed=1    unreachable=0    failed=0


you could check the apache server is running by enter the ip address of node in your browser.


.. tip::

    **Reference Links**

    * `amazing tutorial on youtube <https://youtu.be/3RiVKs8GHYQ>`_
    * `ansible doc <https://docs.ansible.com/>`_
    



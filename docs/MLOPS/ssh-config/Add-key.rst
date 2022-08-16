Add SSH key to the SSH-agent
===================================

1. Ensure the ssh-agent in the background

.. code-block:: bash

    #start the ssh-agent in the background
    eval "$( ssh-agent -s )"
    > Agent pid 59566


2. Add your SSH private key to the ssh-agent
   
.. code-block:: bash

    ssh-add ~/.ssh/id_ed25519


=================
Reference Links
=================
- **Sources**
- `add a new SSH key <https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account>`_






    
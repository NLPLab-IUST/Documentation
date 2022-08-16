Manage deploy key
====================


1. Copy the public ssh key to clip board.


.. code-block:: bash

    clip < ~/.ssh/id_ed25519.pub

2. On your profile page in github, click Repositories, then click
   the name of your repository.

.. image:: image/repo.png
    :name: github repository                 images/Phoniex/Anydesk-1.png
    :alt: Find repository

3. From repo click Settings

4. In the sidebar, click Deploy Keys, then click Add deploy key.

.. image:: image/deploy-key.png
    :alt: Deploy key
    :name: deploy key section

5. Provide a titel, paste in your public key.

.. image:: image/add-deploy-key.png
    :name: paste public key
    :alt: Alternative text

6. Select Allow write access if you want this key to have write
   access to the repository. A deploy key with write access lets 
   a deployment push to the repository.

7. Click Add key.


=================
Reference Links
=================
- **Sources**
- `managing deploy keys <https://docs.github.com/en/developers/overview/managing-deploy-keys>`_

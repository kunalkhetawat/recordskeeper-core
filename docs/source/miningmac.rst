================================================
Mining Guide for Recordskeeper Blockchain on Mac
================================================

The following document helps the users to intiate mining for RecordsKeeper Blockchain over Mac Operating system. All the commands and process displayed in this document is tested and created over Mac OS X 10.12 and above. The detailed overview to start mining for RecordsKeeper Blockchain is as follows:

* :ref:`mac-systemrequirements`
* :ref:`mac-installingrk`
* :ref:`mac-connectingrk`
* :ref:`mac-miningpermissions`
* :ref:`mac-startrkaftermining`
* :ref:`mac-stoprk`

.. _mac-systemrequirements:

System requirements
-------------------

* Mac: 64-bit, supports OS X 10.12 (we hope to support earlier versions soon).
* 512 MB of RAM
* 1 GB of disk space

.. _mac-installingrk:

Installing Recordskeeper on Mac OS:
-----------------------------------

First Install these dependencies by executing below commands:

.. code-block:: bash

    Install XCode and XCode command line tools
    Install git from git-scm
    Install brew (follow instructions on brew.sh)
    brew install autoconf automake berkeley-db4 libtool boost@1.57 openssl pkg-config rename
    brew link boost@1.57 --force

To download the executable directly from the browser `click here <https://github.com/RecordsKeeper/recordskeeper-core/releases/download/v1.0.0/recordskeeper-mac-osx-1.0.0.zip>`_ .

Unzip the zip file and then move to the location of the downloaded files and run following commands from your 
terminal:

.. code-block:: bash

    cd recordskeeper-mac-osx-1.0.0
    mv rkd rk-cli rk-util /usr/local/bin 

Moving the RecordsKeeper files to bin directory make them easily accessible from the command line anywhere.

.. note::
    * if you get error then run the above commands using “sudo” for root privileges 
    * Use exit command (to return to your regular user)
    * Mac users move directly to the :ref:`connecting-rk` section

.. _mac-connectingrk:

Connecting to RecordsKeeper Blockchain on Mac
---------------------------------------------

The RecordsKeeper Testnet Blockchain is avaialble for the users to Develop and Deploy applications over RecordsKeeper Blockchain, XRK Testnet tokens do not hold any value and are only avaialble for testing. You can earn XRK tokens from RecordsKeeper Mainnet mining.

Now to connect to the RecordsKeeper Blockchain, run following command from the terminal:

**RecordsKeeper Testnet**

.. code-block:: bash

    ./rkd recordskeeper-test@35.170.155.89:8379

**RecordsKeeper Mainnet**

.. code-block:: bash

    ./rkd recordskeeper@35.172.1.247:7895


This command will initialize your node.

And, if you want your connection to remain active as a background process then run this command:

**RecordsKeeper Testnet**

.. code-block:: bash

    ./rkd recordskeeper-test@35.172.1.247:8379 -daemon

**RecordsKeeper Mainnet**

.. code-block:: bash

    ./rkd recordskeeper@35.172.1.247:7895 -daemon

In case of an error message like this: 

.. warning::

    Error: Couldn't initialize permission database for blockchain recordskeeper. Probably rkd for this blockchain is already running. Exiting...
    
First kill the daemon process and then try connecting to the RecordsKeeper Blockchain again. If the problem persists then restart your computer and then repeat the whole process of connecting to RecordsKeeper Blockchain again. 

.. note::

    *Mac users now go to the :ref:`mining-permissions` section

.. _mac-miningpermissions:

Mining Permissions
------------------

Connecting RecordsKeeper on Mac
###############################

You will see the folowing message on your Mac command line terminal after you execute the command to connect to the Recordskeeper blockchain.

.. image:: _static/MacRKD.png
   :align: center
   :width: 693.433px

RecordsKeeper Permissions
#########################

**RecordsKeeper Testnet**

The mining for RecordsKeeper Testnet is open for everyone so when you connect to RecordsKeeper Testnet, you will receive all the permissions for your default address

**RecordsKeeper Mainnet**

For Mainnet when your node gets connected, you will receive the permissions to connect, send and receive. Now look for your default XRK address from the command given below, which will display your node’s wallet address. This address is your “default XRK address” or “public address” of the Recordskeeper Blockchain in which you will receive XRK coins. To check the address, run the following command:

.. code-block:: bash

    ./rk-cli recordskeeper getaddresses

**Submit the following to recieve Mining Permissions for RecordsKeeper Mainnet.**

Copy this address and send it to us `here <https://docs.google.com/forms/d/e/1FAIpQLSd1Dd2GAggCyom23HgiBhnQIjlLjMgRwf_UOQrHp9BUTRPEYA/viewform>`_ .

You can also use directly the link and paste it in your web browser:

**https://docs.google.com/forms/d/e/1FAIpQLSd1Dd2GAggCyom23HgiBhnQIjlLjMgRwf_UOQrHp9BUTRPEYA/viewform**

After RecordsKeeper team grant mining permissions to your node address, only after that you would be able to mine XRK coins into your default address.

To retrieve private key for your node address run this command:

.. code-block:: bash

    ./rk-cli recordskeeper dumpprivkey {default_XRK_address}


.. note::
    Please store this private key safely, losing this will result in loss of XRK coins.


After completing the above process, you can check for your node’s information (best block and synced block) by running following commands:

.. code-block:: bash

    ./rk-cli recordskeeper getinfo
    ./rk-cli recordskeeper getblockchaininfo


Your node will sync up to the best block, and then only your node can start mining and your balance will get updated with the mined XRK coins.

In case you have entered the wrong ip-address then it will report this error:

.. warning::

    Error: Couldn't initialize permission database for blockchain recordskeeper. Probably rkd for this blockchain is already running. Exiting...

Please check ip-address and port properly to connect to the RecordsKeeper Blockchain.

.. note::

    If you have already created a wallet address and you want to add it as your miner address then run this command from the command line terminal:
    
    .. code-block:: bash

        ./rk-cli recordskeeper importprivkey {private_key}

.. _mac-startrkaftermining:

Connecting to RecordsKeeper Blockchain after Permissions
--------------------------------------------------------

Once the permissions for RecordsKeeper Mainnet has been granted. You can directly connect to the RecordsKeeper chain and see your mining over the Public RecordsKeeper Blockchain. You can run following commands to connect to the RecordsKeeper Blockchain and view the mining address.

As the IP configuration is already stored with you when you intiated the connection before, you can directly run the following command:

.. code-block:: bash

    rkd recordskeeper -daemon

.. image:: _static/MacRKAfterMining.jpg
   :align: center
   :width: 693.433px

You can run getinfo command or getaddressbalances command to see the balance in your node or directly the node address.

.. code-block:: bash

    rk-cli recordskeeper getinfo

.. image:: _static/MacGetInfoMining.jpg
   :align: center
   :width: 693.433px

.. note::

    You can view your balances in the balance output of the getinfo command.

OR

.. code-block:: bash

    rk-cli recordskeeper getaddressbalances <Your Node Address Given for Mining>

.. image:: _static/MacAddressBalancesAfterMining.jpg
   :align: center
   :width: 693.433px

.. note::

    Please do not use the address specified above, this address is only avaialble for the demo purpose.

.. _mac-stoprk:

Stopping Blockchain
-------------------

**RecordsKeeper Mainnet**

    In case you want to stop your running Recordskeeper node then you can use the following command from your command line terminal:


    .. code-block:: bash

        ./rk-cli recordskeeper stop


**RecordsKeeper Testnet**

    In case you want to stop your running Recordskeeper-test Blockchain node then you can use the following command from your command line terminal:


    .. code-block:: bash

        ./rk-cli recordskeeper-test stop
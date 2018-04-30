====================================================
Mining Guide for Recordskeeper Blockchain on Windows
====================================================

The following document helps the users to intiate mining for RecordsKeeper Blockchain over Windows Operating system. All the commands and process displayed in this document is tested and created over Windows 7 and above Operating Systems. The detailed overview to start mining for RecordsKeeper Blockchain is as follows:

* :ref:`windows-systemrequirements`
* :ref:`windows-installingrk`
* :ref:`windows-connectingrk`
* :ref:`windows-miningpermissions`
* :ref:`windows-stoprk`

.. _windows-systemrequirements:

System requirements
-------------------

* Windows: 64-bit, supports Windows 7, 8, 10, Server 2008 or later.
* 512 MB of RAM
* 1 GB of disk space

.. _windows-installingrk:

Installing Recordskeeper on Windows
-----------------------------------

Download the executables from `here <https://github.com/RecordsKeeper/recordskeeper-core/releases/download/v1.0.0/recordskeeper-windows-1.0.0.zip>`_ and then unzip it and you will have the binary files: rkd.exe, rkd-cold.exe, rk-cli.exe and rk-util.exe.

Copy the folder to your desired location.

Then open your command line terminal and go to that location, after that run the following command:

.. code-block:: bash
    
    cd recordskeeper-windows-1.0.0

.. note::
    Windows users move directly to the :ref:`connecting-rk` section.

.. _windows-connectingrk:

Connecting to RecordsKeeper Blockchain on Windows
-------------------------------------------------

The RecordsKeeper Testnet Blockchain is avaialble for the users to Develop and Deploy applications over RecordsKeeper Blockchain, XRK Testnet tokens do not hold any value and are only avaialble for testing. You can earn XRK tokens from RecordsKeeper Mainnet mining.

Now to connect to the RecordsKeeper Blockchain, first go into the directory where you have downloaded “recordskeeper-windows-1.0.0.zip” and then open command line terminal from that location:

**RecordsKeeper Testnet**

.. code-block:: bash

    rkd recordskeeper-test@35.170.155.89:8379 

**RecordsKeeper Mainnet**

.. code-block:: bash

    rkd recordskeeper@35.172.1.247:7895  


This command will initialize your node.

And, if you want your connection to remain active as a background process then run this command:

**RecordsKeeper Testnet**

.. code-block:: bash

    rkd recordskeeper-test@35.170.155.89:8379 -daemon

**RecordsKeeper Mainnet**

.. code-block:: bash

    rkd recordskeeper@35.172.1.247:7895 -daemon

If the Operating system does not pop up the allow firewall connections for rkd like shown below:

.. image:: _static/AllowFirewall.png
   :align: center
   :width: 693.433px

Then you have to manually allow connections through firewall by following the steps below:

Go to:

.. code-block:: bash

    Control Panel > System and Security > Windows Defender Firewall > Advanced Settings

And add Outbound rules by following these steps:

**Step 1:** First select the Rule type, as you have to create a rule for allowing the network port so select Port here and then press Next:

.. image:: _static/Step1Outbound.png
   :align: center

**Step 2:** Specify the port address of the RecordsKeeper Blockchain to which you are allowing access, for Testnet type 8379 and to open ports for Mainnet type 7895 in the textbox and then click on Next:

.. image:: _static/Step2Outbound.png
   :align: center

**Step 3:** Now click on *Allow the connection* and then press Next:

.. image:: _static/Step3Outbound.png
   :align: center

**Step 4:** Select all three profiles here for the rule to apply, and then click on Next:

.. image:: _static/Step4Outbound.png
   :align: center

**Step 5:** Now choose a name for the created Outbound rule and then press *Finish* to complete the process of opening up the ports.

.. image:: _static/Step5Outbound.png
   :align: center

.. note::
    If you want some other RecordsKeeper node to connect to your node then you have to allow connections by making Inbound rules for the same. Follow the same procedure after selecting a new Inbound rule.

.. note::
    Windows users now can go to the :ref:`mining-permissions` section.

.. _windows-miningpermissions:

Mining Permissions
------------------

Running RecordsKeeper on Windows
################################

You will see the following message on your Windows command line terminal after you execute the command to connect to the Recordskeeper blockchain.

.. image:: _static/WindowsRKD.png
   :align: center

.. note::

    Windows users have to open a new command line terminal window for running the remaining commands.

RecordsKeeper Permissions
#########################

**RecordsKeeper Testnet**

The mining for RecordsKeeper Testnet is open for everyone so when you connect to RecordsKeeper Testnet, you will receive all the permissions for your default address

**RecordsKeeper Mainnet**

For Mainnet when your node gets connected, you will receive the permissions to connect, send and receive. Now look for your default XRK address from the command given below, which will display your node’s wallet address. This address is your “default XRK address” or “public address” of the Recordskeeper Blockchain in which you will receive XRK coins. To check the address, run the following command:

.. code-block:: bash

    rk-cli recordskeeper getaddresses

**Submit the following to recieve Mining Permissions for RecordsKeeper Mainnet.**

Copy this address and send it to us `here <https://docs.google.com/forms/d/e/1FAIpQLSd1Dd2GAggCyom23HgiBhnQIjlLjMgRwf_UOQrHp9BUTRPEYA/viewform>`_ .

You can also use directly the link and paste it in your web browser:

**https://docs.google.com/forms/d/e/1FAIpQLSd1Dd2GAggCyom23HgiBhnQIjlLjMgRwf_UOQrHp9BUTRPEYA/viewform**

After RecordsKeeper team grant mining permissions to your node address, only after that you would be able to mine XRK coins into your default address.

To retrieve private key for your node address run this command:

.. code-block:: bash

    rk-cli recordskeeper dumpprivkey {default_XRK_address}        #(input node_address without braces)


.. note::
    Please store this private key safely, losing this will result in loss of XRK coins.


After completing the above process, you can check for your node’s information (best block and synced block) by running following commands:

.. code-block:: bash

    rk-cli recordskeeper getinfo                 #(for synced block)
    rk-cli recordskeeper getblockchaininfo       #(for best block)


Your node will sync up to the best block, and then only your node can start mining and your balance will get updated with the mined XRK coins.

In case you have entered the wrong ip-address then it will report this error:

.. warning::

    Error: Couldn't initialize permission database for blockchain recordskeeper. Probably rkd for this blockchain is already running. Exiting...

Please check ip-address and port properly to connect to the RecordsKeeper Blockchain.

.. note::

    If you have already created a wallet address and you want to add it as your miner address then run this command from the command line terminal:
    
    .. code-block:: bash

        rk-cli recordskeeper importprivkey {private_key}      #(include private key without braces)

.. _windows-stoprk:

Stopping RecordsKeeper Blockchain
---------------------------------

**RecordsKeeper Mainnet**

    In case you want to stop your running Recordskeeper node then you can use the following command from your command line terminal:


    .. code-block:: bash

        rk-cli recordskeeper stop


**RecordsKeeper Testnet**

    In case you want to stop your running Recordskeeper-test Blockchain node then you can use the following command from your command line terminal:


    .. code-block:: bash

        rk-cli recordskeeper-test stop
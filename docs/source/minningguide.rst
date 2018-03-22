=========================================
Mining Guide for Recordskeeper Blockchain
=========================================


System requirements
-------------------

* Linux: 64-bit, supports Ubuntu 12.04+, CentOS 6.2+, Debian 7+, Fedora 15+, RHEL 6.2+.
* Windows: 64-bit, supports Windows 7, 8, 10, Server 2008 or later.
* Mac: 64-bit, supports OS X 10.12 (we hope to support earlier versions soon).
* 512 MB of RAM
* 1 GB of disk space

Installing Recordskeeper
------------------------ 

Linux (Ubuntu):
############### 

First Install these dependencies by executing below commands:

.. code-block:: bash

    sudo apt-get update
    sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils
    sudo apt-get install libboost-all-dev
    sudo add-apt-repository ppa:bitcoin/bitcoin
    sudo apt-get update
    sudo apt-get install libdb4.8-dev libdb4.8++-dev

To download the executable directly from the browser `click here <https://github.com/RecordsKeeper/recordskeeper-core/releases/download/v1.0.0/recordskeeper-1.0.0.tar.gz>`_ .

And, if you want to download it from the command line terminal then use this command:

.. code-block:: bash

    wget https://github.com/RecordsKeeper/recordskeeper-core/releases/download/v1.0.0/recordskeeper-1.0.0.tar.gz

Then, move to the location of the downloaded files and run following commands from your 
terminal:

.. code-block:: bash

    tar -xvzf recordskeeper-1.0.0.tar.gz
    cd recordskeeper-1.0.0
    mv rkd rk-cli rk-util /usr/local/bin (to make it easily accessible from the command line)

.. note::
    * if you get error then run the above commands using “sudo” for root privileges 
    * Use exit ommand (to return to your regular user)
    * Linux users move directly to the connecting to Recordskeeper Blockchain section

  
Windows :
#########

Download the executables from `here <https://github.com/RecordsKeeper/recordskeeper-core/releases/download/v1.0.0/recordskeeper-windows-1.0.0.zip>`_ and then unzip it and you will have the binary files: rkd.exe, rkd-cold.exe, rk-cli.exe and rk-util.exe.

Copy the folder to your desired location.

Then open your command line terminal and go to that location, after that run the following command:

.. code-block:: bash
    
    cd recordskeeper-windows-1.0.0

.. note::
    Windows users move directly to the connecting to Recordskeeper Blockchain section.


Connecting to RecordsKeeper Blockchain(main net)
------------------------------------------------

Linux:
######

Now to connect to this Blockchain, run following command from the terminal:

.. code-block:: bash

    rkd recordskeeper@35.172.1.247:7345


This command will initialize your node.

And, if you want your connection to remain active as a background process then run this command:

.. code-block:: bash

    rkd recordskeeper@35.172.1.247:7345 -daemon

.. note::
    Linux users now go to the Mining access permissions section

Windows
#######

Now to connect to this Blockchain first go into the directory where you have downloaded “recordskeeper-windows-1.0.0” and then open command line terminal from that location:

.. code-block:: bash

    rkd recordskeeper@35.172.1.247:7345  


This command will initialize your node.

And, if you want your connection to remain active as a background process then run this command:

.. code-block:: bash

    rkd recordskeeper@35.172.1.247:7345 -daemon




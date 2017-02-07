################
QuickStart
################

In order for you to get the most out of ⏣, you need at least two things:

:Wallet: A ⏣ wallet is a secure digital wallet used to store, send, and receive digital currency like SecKCoin (⏣). In order to use SecKCoin cryptocurrency you will need to use a cryptocurrency wallet. At this time, SecKCoin only works with our official wallet, which in most cases will need to be compiled before use.
:Mining Software: In traditional fiat money systems, governments simply print more money when they need to. But in SecKCoin, ⏣ isn’t printed at all – it is discovered by mining. The very first thing you need in order to start mining coins is to obtain the mining program that is associated with SecKCoin. SecKCoin uses a mining client, which also works in conjunction with the ⏣ Wallet.

Wallet Creation
################

====================
Debian Linux
====================
:Dependancies:

.. code-block:: bash

  sudo apt-get install qt4-qmake libqt4-dev build-essential libssl-dev libdb++-dev libminiupnpc-dev libboost-all-dev libcurl4-openssl-dev git qt-sdk libminiupnpc-dev libssl-dev libdb++-dev

Make a directory to store all your SKC goodies.

.. code-block:: bash

   mkdir ~/SKC

Download the wallet creation software from our github repository.

.. code-block:: bash

   git clone https://github.com/SecKC/SecKCoin.git

We need to customize the our Makefile prior to building the wallet from source code.
Using the qmake command we are telling the SecKCoin wallet to NOT build the wallet with UPNP support for NAT forwarding.

 .. code-block:: bash

  cd ~/SKC/SecKCoin/seckcoin
  qmake "USE_UPNP=-"


Now that we've set that in the Makefile, lets build the wallet!

Move into the directory containing source files required for building.

  .. code-block:: bash

   cd ~/SKC/SecKCoin/seckcoin/src

Make the wallet

  .. code-block:: bash

   make -f makefile.unix USE_UPNP=-

Your shiny new wallet is called "seckcoind" and is in the following location

  .. code-block:: bash

   ~/SKC/SecKCoin/seckcoin/src $ ls -alr
   -rwxr-xr-x  1 pi pi 46091276 Feb  6 06:08 seckcoind

Initialize the wallet to generate seckcoind supporting directories and configuration files.

The binary is portable, I recommend COPYING it into ~/SKC/ for ease of use. Then you have a backup in the src directory.

  .. code-block:: bash

   cp ~/SKC/SecKCoin/seckcoin/src/seckcoind ~/SKC/
   cd ~/SKC
   ./seckcoind

You may see the following error.  Don't panic, its just telling you that you haven't set a configuration up yet.

  .. code-block:: bash

   Error: To use seckcoind, you must set a rpcpassword in the configuration file:
   ~/.seckcoin/seckcoin.conf
   [SNIP]

The following files have now been created

  .. code-block:: bash

   ~/.seckcoin/
   ~/.seckcoin/seckcoin.conf  <-- This file MIGHT not have been created. Check first.
   ~/.seckcoin/wallet.dat

Copy the sample configuration provided in the github repository download to the seckcoind wallet configuration directory.

  .. code-block:: bash

   cp ~/SKC/SecKCoin/seckcoin.conf.sample ~/.seckcoin/seckcoin.conf

Set the following options in the ~/.seckcoin/seckcoin.conf file:

Note: This is from my working configuration. 


  .. code-block:: bash

    addnode=162.243.116.8:1337
    addnode=107.170.52.120:1337
    addnode=hevnsnt.ddns.net:1337
    addnode=104.154.95.66:1337
    addnode=107.178.223.6:1337    
    server=1
    listen=1
    rpcuser=SecKC_RPC
    rpcpassword=x
    rpcallowip=127.0.0.1
    rpcport=11337
    paytxfee=0.001
    daemon=1

Mining Software
################

===================
Placehoder
===================


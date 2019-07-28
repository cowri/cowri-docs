# Installation Overview

The following guide is designed to get developers up and running as quickly and simply as possible.

## Pre-requisties

**Metamask**
* Install [Metamask](https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn?hl=en)
* Create your [Metamask wallet](https://metamask.io/)

## Running Cowri Demo App - Kovan

**Running the hosted cowri shell application**

Cowri Shell can be run by going to [https://demo.cowri.io](https://demo.cowri.io) and then following the [user tutorial](../user-guide/1-User-Tutorial.md).

**Installing and running cowri shell application - locally**
If you wish to see the source code and modify the codebase you may install [cowri-demo-apps](https://github.com/cowri/cowri-demo-apps) locally and run the [Cowri Shell](https://github.com/cowri/cowri-demo-apps/tree/master/cowri-shell).

**1. Download and run the Cowri Shell**
```
git clone https://github.com/cowri/cowri-demo-apps
cd cowri-demo-apps/cowri-shell
npm install
```

**2. Follow the [user tutorial](../user-guide/1-User-Tutorial.md) to familiarize yourself with Cowri.**


## Running Cowri Demo App - Locally

### Installing Cowri Utilities and Cowri Ganache

Cowri provides a set of tools for you to run cowri applications locally. These include
* Cowri ganache instance
* Cowri faucet
* Cowri Liqudity provider
see the [developer guide](./developerGuide.md) for more detail.

To run the application locally follow the below steps

**1. Install the Cowri Utilities**
```
curl -LO https://download.cowri.io/cowri-local.zip | tar tar -xf - -C cowri-local
cd cowri-local
```

**2. Run the Cowri Utilities**
```
./cowri-local.sh
```

**3. Connect Metamask to your local ganache instance**

  * Open Metamask
  * Select the dropdown next to the Network
  * Select Custom rpc
  * Create a custom RPC connection for Ganache-CLI
    * NEW RPC URL - http://127.0.0.1:8545
    * Nickname - Cowri Ganache CLI
  * For further information on MetaMask setup see [here](https://metamask.github.io/metamask-docs/Main_Concepts/Getting_Started)

**4. Import the Private keys for the test users to your metamask wallet**
  * Private keys for sample users can be found in [MasterData](./masterData.md)
  * It is recommended to import Alice, Bob, Charlies and Denises private Keys for testing purposes
  * You may also use your own users - you will need to 
    * transfer them some ether from one of the above test users
    * Create a cowri shell using the application

**5. Run the Cowri Demo Application - locally**
  * From a seperate termianl window, run cowri demo application as above - only with metamask now connected to the newly created Cowri Ganache CLI network. 



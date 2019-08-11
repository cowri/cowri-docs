# Setup

The setup and installation of Cowri and its back end services can be done in a number of ways. Developers have the choice of cloning the repository and starting each service individually \(not recommended\), bringing the services up using docker-compose, or starting all the services using a shell script from the Github repository \(UNIX systems only\). This document outlines each of the installation options.

## Prerequisties

#### **Metamask**

1. Install the [Metamask](https://metamask.io/) browser extension for your browser
   * If you're new to Metamask, familiarize yourself with this [three and a half minute video](https://youtu.be/ZIGUC9JAAw8)
2. If you haven't already, create your Metamask wallet
3. Follow [this article](https://blog.chronologic.network/how-to-get-eth-and-day-on-the-kovan-test-network-f2190076052a) to get test ETH sent to your wallet on Kovan
4. Familiarize yourself with Cowri and its use of Metamask with the [Cowri Tutorial](../cowri-user-guide/1-user-tutorial.md)
5. For a more complete Cowri experience, import each of the Cowri test users into Metamask from Cowri's [Master Data](https://github.com/cowri/cowri-docs/tree/ee67cd05b68e99ed75c2cf128a218c50422db9f8/cowri-developer-guide/masterdata/README.md) and, optionally, importing each of Cowri's test ERC20 tokens into each user. 

{% hint style="info" %}
Information on how to import users into Metamask using their private key can be found [here](https://medium.com/publicaio/how-import-a-wallet-to-your-metamask-account-dcaba25e558d)
{% endhint %}

{% hint style="info" %}
**Make sure you are connected to the KOVAN test network in Metamask**
{% endhint %}

#### **Docker and Docker Compose \(optional\)**

The easiest way to bring all Cowri services up is by using [Docker Compose](https://docs.docker.com/compose/). This requires the installation of both [Docker](https://docs.docker.com/install/) and [Docker Compose](https://docs.docker.com/compose/install/) on your local machine. However, if you wish to run the services without using Docker Compose, that can be done as well.

## Running Cowri Demo App Locally

### Running using Docker Compose

To run the Cowri Demo application using Docker Compose:

1. Download the Cowri [docker-compose.yaml](http://download.cowri.io/docker-compose.yaml)
2. From the same directory as the `docker-compose.yaml` file, run `docker-compose up`
3. Once the services are done loading, you can use the Cowri demo application by navigating to `http://localhost:6706` in your browser

### Running using Shell Scripts \(UNIX systems only\)

To run the Cowri Demo application using shell scripts:

1. Clone the Cowri repository with `git clone http://github.com/cowri/cowri.git`
2. `cd` into the `utilities` folder
3. Initialize the services with `sh ./init.sh`
4. Start the servies with `sh ./start.sh`. This will open the web app in your default browser automatically
5. Stop the services with `sh ./stop.sh`

## Starting each service individually \(most difficult\)

Each individual service can be started manually using NPM. This requires that the Cowri repository has been cloned with `git clone http://github.com/cowri/cowri.git`. Information about each of the utilities can be found in the [Developer Toolkit Overview](https://github.com/cowri/cowri-docs/tree/ee67cd05b68e99ed75c2cf128a218c50422db9f8/cowri-developer-guide/developerguide/README.md). You can also find detailed developer information about the utilities in the [Utilities README](https://github.com/cowri/cowri/blob/master/utilities/README.md)

#### **Faucet** 

1. `cd` into the `utilities/faucet` folder 
2. Install all dependencies with `npm install` 3. Start the faucet service with `npm start -- -k <private key of minter> -P <public key of minter`

{% hint style="info" %}
The Cowri private key for the Faucet on Ganache is `43820EB3668B9B86BA8066996826D614DF45D7292FD7D27DBFE4B409982CAA5E` and the public key is `0x40e3ba962dFa3e41d1B54A97199831c2C99f6f37`. Please note that these keys will **ONLY** work with Ganache \(see below\).
{% endhint %}

{% hint style="info" %}
More options for starting the Faucet can be see in with `npm start -- -h`
{% endhint %}

#### **Ganache** 

1.  `cd` into the `sdk/dapp-sdk` folder 
2.  Install all dependencies with `npm install`
3. Install the global dependencies with `npm install -g download-cli extract-zip` 
4. Start the Ganache instance as the Denise user with `npm run ganache:denise`

#### **Liquidity Provider** 

1. `cd` into the `utilities/liquidity` folder
2. Install all dependencies with `npm install`
3. Start the liquidity service with `npm start -- -k <liquidity private key> -P <liquidity public key>`

{% hint style="info" %}
The private key for the Ganache liquidity provider is `ACB02AF912E15578F3A49D0ABDAF8DE136F38045C6F116FA8D691A610FF005A1` and the public key is `0xE24d0B953961C6109d2bD5786923347B6897eAfB`
{% endhint %}

{% hint style="info" %}
More options for starting the Liquidity Provider can be see in with `npm start -- -h`
{% endhint %}

#### **Cowri Shell Demo Web App**

1. `cd` into the `utilities/cowri-shell` folder
2. Install all dependencies with `npm install`
3. Start the application with `npm start`

{% hint style="info" %}
The app will open automatically in the default browser
{% endhint %}


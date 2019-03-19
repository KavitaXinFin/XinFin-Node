
## How to Setup XinFin-XDC Masternode

## Prerequisite

**Operating System**: Ubuntu 16.04 64-bit or higher (Scroll Down for Windows and MAC Operating System)

Should be facing internet directly with **public IP** & **without NAT**

**Tools**: Docker, Docker Compose(1.21.2+)


## Network Ports

Following network ports need to be open for the nodes to communicate

| Port | Type | Definition |
|:------:|:-----:|:---------- |
|8545| TCP | RPC |
|30303| TCP/UDP | XDC |

### Setup (For Ubuntu 16.04 64-bit or higher Operating System) 

## Clone repository
```
git clone https://github.com/XinFinOrg/XinFin-Node.git
```

Enter `XinFin-Node` directory
```
cd XinFin-Node
```


## Step: 1 Install docker & docker-compose
    sudo ./install_docker.sh

## Step: 2 Update .env file with details
Create `.env` file by using the sample - `.env.example`

Enter either your company or product name in the INSTANCE_NAME field.

Enter your email address in CONTACT_DETAILS field.

```
cp env.example .env
nano .env
```

## Step: 3 Start your Node

Run:
```
sudo docker-compose -f docker-services.yml up -d
```

You should be able to see your node listed on this page: [https://xinfin.network](https://XinFin.network/) Select Menu "Switch to TestNet" for TestNetwork and Select "Switch to LiveNet" to check LiveNetwork Stats. 

Your coinbase address can be found in xdcchain/coinbase.txt file.

To stop the node or if you encounter any issues use::
```
sudo docker-compose -f docker-services.yml down
```

## Upgrade
To upgrade please use the following commands

```
sudo docker-compose -f docker-services.yml down
sudo ./upgrade.sh
sudo docker-compose -f docker-services.yml up -d
```

## Setup For Windows 64-bit Operating System
```
git clone https://github.com/XinFinOrg/XinFin-Node.git
```

Enter `win64` directory
```
cd XinFin-Node/win64/one-click-installer
```

Run
```
setup.exe
```

This will install the XDC binary in C:\Program Files (x86)\XinFin with all the start-menu, desktop icons & uninstaller.

Righ-click on the XinFin-XDC Masternode icon on desktop & click on "Run as administrator" to launch your masternode.


##  Setup For MAC Operating System (using Vagrant Environments).
You need to download and install below-mentioned three softwares:
1. Install Oracle [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
2. Install [Vagrant](https://www.vagrantup.com/downloads.html)
3. Install [GIT](https://gitforwindows.org/)
    After installation of above three Softwares, (this may also need restart of your machine.)
4. Launch "command prompt" & follow the commands below  
   ```sh
    git clone https://github.com/XinFinOrg/XinFin-Node.git
    cd XinFin-Node
    vagrant up
    vagrant ssh
    ```
5. XinFin-Node is automatically copied to /home/vagrant/ Follow Step 1, 2 & 3 as explained before in this document to complete the node setup.
6. To shutdown the vagrant instance, run vagrant suspend. To delete it, run vagrant destroy.


**Troubleshooting**

You can have public discussions on the technical issues, you can post articles and also request for enhancements and technical contribution. 

[Slack Public Chat](https://launchpass.com/xinfin-public), 

[Telegram Chat](http://bit.do/Telegram-XinFinDev), 

[Forum](https://xinfin.net), 

[GitHub](https://github.com/XinFinorg)



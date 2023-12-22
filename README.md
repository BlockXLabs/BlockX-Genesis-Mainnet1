
<div align="center">
  <h1> BlockX Mainnet Source Code</h1>
</div>


# Pre-requisites:

1. At least Go version 1.18
2. Ubuntu 22.04
3. Make
4. GCC

# Pre-requisite step
## Install Golang:
Install latest go version https://golang.org/doc/install

```
wget -q -O - https://raw.githubusercontent.com/canha/golang-tools-install-script/master/goinstall.sh | bash -s -- --version 1.18
source ~/.profile
```

To verify that Golang installed
```
go version
```

It should return go version go1.18 linux/amd64


## Install Make to compile the code
sudo apt install make

## Install GCC in case GCC is not yet installed
sudo apt-get install gcc



# Compile the code
```
make install
```

This will create a blockxd file in the /root/go/bin directory

# How to add blockxd path for it to be accessible system-wide
In the example below, blockxd is in /root/go/bin
```
export PATH=/root/go/bin:$PATH
source ~/.bashrc
```

# Starting the BlockX Mainnet
We will be adding each validator to the genesis.json file and have a scheduled future start of the chain. You can execute the init.sh file in this repo. The init.sh file will create a key for you as well a gentx file which will be found under the /root/.blockxd/config/gentx folder. Please submit a PR with your uploaded file.

Here are the steps that the validators need to follow:
1. Create the key for your validator
2. Add your key as a genesis account
3. Sign the genesis transaction
4. Submit the signed genesis transaction to https://github.com/BlockXLabs/blockx-gentx-mainnet
5. We will collect the signed genesis transaction together with your genesis accounts to generate an updated genesis.json containing all the participating validators then post it on this repo for everyone to download

With this, every nodes will start at the same time and no need for us to send you tokens. Take note that this source code is also the same one that testnet validators.

Validators will have until January 5th to submit their gentx files then the chain will have its genesis start on January 10th. 
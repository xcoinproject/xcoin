xCoin
=====

https://xcoinproject.com

What is xCoin?
--------------

xCoin is a cryptocurrency based on bitcoin code. 

Maximum Supply:
52.5 million XCOIN

Mining Reward:
256 XCOIN, halving every 100,000 blocks
The first 130 blocks get a 10,000 XCOIN bonus.

Block Spacing:
Approximately 5.25 minutes

Compiling on Linux
-------------------

Here is a rough guide to compiling on Linux:

sudo apt-get update
sudo apt-get upgrade

sudo apt-get install build-essential libtool autotools-dev autoconf pkg-config libssl-dev

sudo apt-get install libboost-all-dev

sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler
sudo apt-get install libqrencode-dev autoconf openssl libssl-dev libevent-dev
sudo apt-get install libminiupnpc-dev
sudo apt-get install git
sudo apt-get install autoconf
echo 'deb-src ftp://ftp.us.debian.org/debian/ sid main contrib non-free' >> /etc/apt/sources.list
git clone https://github.com/xcoinproject/xcoin.git
sudo apt-get build-dep bitcoin
sudo apt-get install -–install-recommends libbitcoin-dev
exit
mkdir xcoin/db4/
cd xcoin/db4/
wget 'http://download.oracle.com/berkeley-db/db-4.8.30.NC.tar.gz'
tar -xzvf db-4.8.30.NC.tar.gz
cd db-4.8.30.NC/build_unix/
../dist/configure --enable-cxx --disable-shared --with-pic --prefix=/home/USER_HERE/xcoin/db4/
make install
cd ~/xcoin/
./autogen.sh
./configure LDFLAGS="-L/home/USER_HERE/xcoin/db4/lib/" CPPFLAGS="-I/home/USER_HERE/xcoin/db4/include/"
make

License
-------

xCoin is released under the terms of the MIT license. See [COPYING](COPYING) for more
information or see https://opensource.org/licenses/MIT.

Credits
-------

xCoin was forked from Bitcoin Core
* [bitcoin](https://github.com/bitcoin/bitcoin)
* [CryptoCoderz](https://github.com/CryptoCoderz/Espers.git) HMQ1725

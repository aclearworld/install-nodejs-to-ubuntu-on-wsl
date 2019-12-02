# How to install nodejs to ubuntu on wsl2

## my environment
 - Microsoft Windows [Version 10.0.19033.1]
 - wsl2
   - NAME="Ubuntu"
   - VERSION="18.04.3 LTS (Bionic Beaver)"
   
# Way 

## update apt and install nodejs and npm by apt

```bash
$ sudo apt update
$ sudo apt upgrade
$ sudo apt install node npm
$ node -v
v8.10.0
$ which node
/usr/bin/node
$ npm -v
3.5.1
```

## upgrage npm

```bash
$ sudo npm install -g npm 
NPM ERR!
'''

why?

```bash
$ which npm
/mnt/c/Program Files/nodejs/npm
```

Oh! `coomand npm` is points to npm installed on windows 

```bash
$ cd ~

# Just in case
$ cp .bashrc .bashrc-bak 

$ echo "alias npm=/usr/bin/npm"  >> .bashrc 
$ source .bashrc 
$ sudo npm install -g npm 

# moved stable npm
$ nano .bashrc

- alias npm=/usr/bin/npm
+ alias npm=/usr/local/bin/npm

$ source .bashrc 
$ npm -v
6.13.1
$ which npm
/usr/local/bin/npm
'''

OK!

# install stable nodejs by n

```bash
$ sudo npm install -g n
$ sudo n stable
$ sudo apt purge -y nodejs
$ exec $SHELL -l
$ echo "export PATH=\$PATH:/usr/local/bin" >> .bashrc
$ source .bashrc 
$ node -v
v12.13.1
```

OK!

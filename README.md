# ipfs-snap

IPFS is the Distributed Web, and this is its snap package.

## Build

### In Ubuntu

Install snapcraft:

    $ sudo apt install snapcraft

Clone the repo:

    $ sudo apt install git
    $ git clone https://github.com/elopio/ipfs-snap
    $ cd ipfs-snap

Configure the PPA with go 1.7:

    $ sudo add-apt-repository ppa:gophers/archive
    $ sudo apt update

Build the snap:

    $ snapcraft

### In archlinux

Install docker:

    $ sudo pacman -S docker
    $ sudo systemctl start docker
    $ sudo gpasswd -a $USER docker
    $ newgrp docker

Clone the repo:

    $ sudo packman -S git
    $ git clone https://github.com/elopio/ipfs-snap
    $ cd ipfs-snap

Build the snap in a docker container:

    $ docker run -v $(pwd):/cwd snapcore/snapcraft sh -c 'apt install software-properties-common wget -y && add-apt-repository -y ppa:gophers/archive && apt update && cd /cwd && snapcraft

Install snapd:

    $ sudo pacman -S snapd
    $ sudo systemctl enable --now snapd.socket


## Install

    $ sudo snap install ipfs*.snap --dangerous

## Try

    $ /snap/bin/ipfs init
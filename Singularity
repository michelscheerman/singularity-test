BootStrap: docker
From: ubuntu:16.04

%runscript
    echo "This container has no run feature"

%post
    echo "Starting the post actions"
    apt-get update
    apt-get install libtool
    apt-get install git
    apt-get install automake
    apt-get install autoconf
    apt-get install flex
    apt-get install g++

    git clone https://github.com/open-mpi/ompi.git
    cd ompi

    ./autogen.pl
    ./configure --enable-static --disable-shared
    make
    make install

    #gina mount points
    mkdir -p /data/scratch
    mkdir -p /data/home
    mkdir /cvmfs

    #cartesius mount points
    mkdir /scratch
    mkdir /scratch-shared
    mkdir /scratch-local
    mkdir /projects
    mkdir /lustre1
    mkdir /lustre2
    mkdir /lustre4

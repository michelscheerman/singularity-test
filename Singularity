BootStrap: yum
OSVersion: 7
MirrorURL: http://mirror.centos.org/centos-%{OSVERSION}/%{OSVERSION}/os/$basearch/
Include: yum

%runscript
    echo "Running the container"

%post
    yum -y groupinstall "Development Tools"

    git clone https://github.com/open-mpi/ompi.git
    cd ompi

    pwd
    ./autogen.pl
    ./configure --prefix=/usr/local
    make
    make install

    cd /ompi
    mpicc examples/ring_c.c -o ring

    cp ring /usr/bin/

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

# Docker
BusTub docker file for C++ development on Ubuntu 22.04

# Create Docker image and container:

    $ docker build . -t bustub
    $ docker create -t -i --name bustub -v $(pwd):/bustub bustub bash

# Run the container

    $ docker start -a -i bustub

- Open a shell within the box. 
- Find Bustub's code mounted at /bustub 

# Build BusTub

    $ sudo build_support/packages.sh    
    $ mkdir build
    $ cd build
    $ cmake ..
    $ make

To compile in debug mode, enables AddressSanitizer by default.

    $ cmake -DCMAKE_BUILD_TYPE=Debug ..
    $ make -j`nproc`

To compile using other sanitizers

    $ cmake -DCMAKE_BUILD_TYPE=Debug -DBUSTUB_SANITIZER=thread ..
    $ make -j`nproc`


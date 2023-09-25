# Compile the port for QNX

**NOTE**: QNX ports are only supported from a **Linux host** operating system

### Install automake/autoconf tools

`sudo apt install automake`

### Clone repository

`git clone git@gitlab.com:qnx/libs/asio.git && cd asio/asio`
	
### Generate GNU build tool ./configure and all needed Makefiles

`./autogen.sh`

### Setup QNX SDP environment

`source <path-to-sdp>/qnxsdp-env.sh`

### Build examples and install asio headers into SDP

`JLEVEL=$(nproc) make -C qnx/build install`


**All asio headers have to be installed to SDP**
* $QNX_TARGET/usr/include/asio/
* $QNX_TARGET/usr/include/asio.hpp

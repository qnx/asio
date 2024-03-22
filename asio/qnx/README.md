# Compile the port for QNX

**NOTE**: QNX ports are only supported from a **Linux host** operating system

### Install dependencies

`sudo apt install automake`

`sudo apt install pkg-config`

### Switch to asio main folder

`cd asio`
	
### Generate GNU build tool ./configure and all needed Makefiles

`./autogen.sh`

### Setup QNX SDP environment

`source <path-to-sdp>/qnxsdp-env.sh`

### Build examples and install asio headers to SDP

`JLEVEL=$(nproc) make -C qnx/build install`

**All asio headers and pkgconfigs have to be installed to SDP**
* $QNX_TARGET/usr/local/include/asio/
* $QNX_TARGET/usr/local/include/asio.hpp
* $QNX_TARGET/aarch64le/usr/local/lib/pkgconfig/asio.pc
* $QNX_TARGET/x86_64/usr/local/lib/pkgconfig/asio.pc

### Build examples and install asio headers to specific path

`JLEVEL=$(nproc) make -C qnx/build install USE_INSTALL_ROOT=true INSTALL_ROOT_nto=<full-path>`

**All asio headers and pkgconfigs have to be installed to specific path**
* \<full-path\>/usr/local/include/asio/
* \<full-path\>/usr/local/include/asio.hpp
* \<full-path\>/aarch64le/usr/local/lib/pkgconfig/asio.pc
* \<full-path\>/x86_64/usr/local/lib/pkgconfig/asio.pc

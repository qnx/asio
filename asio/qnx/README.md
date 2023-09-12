# Compile the port for QNX

**NOTE**: QNX ports are only supported from a **Linux host** operating system

1. Install automake/autoconf tools

	`sudo apt install automake`

2. Clone repository

	`git clone git@gitlab.com:qnx/libs/asio.git && cd asio/asio`
	
3. Generate GNU build tool ./configure and all needed Makefiles

	`./autogen.sh`

4. Setup QNX SDP environment

	`source <path-to-qnxsdp-env.sh>/qnxsdp-env.sh`

5. Build examples and install asio headers into SDP

	`JLEVEL=$(nproc) make -C qnx/build install`

**All asio headers have to be installed to SDP**
* *QNX SDP7.1 -> <SDP>/target/qnx7/usr/include*
* *QNX SDP8.1 -> <SDP>/target/qnx/usr/include*

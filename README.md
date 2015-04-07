# ioengine_10g

Kai Zhang  <kay21s AT gmail DOT com>
Yayun Tian <yayuntian@163.com>

Based on IOEngine from PacketShader, send packets from a specified trace file at speed of 10Gbps
Make some modification in the driver to adapt to current kernel version(2.6.37)


NOTICE:

driver/Makefile  	-- Set "KSRC" to the kernel dir
interface name	 	-- IOEngine uses ixg%d, while our machine uses eth%d, can be modified in driver/install.py



USAGE:

./configure
Make
./install.py [# of RX queue] [# of TX queue]

Adjust the batch size in sample/tx/echo.c

Each TX thread uses a trace file, specify them in sample/tx/pktbuf.c : char fname[QUEUE_NUM][256];

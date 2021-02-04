# vmware-on-linux-debian
install vmware 16 cli on debian linux
follow the steps below to install vmware 16 on a debian linux distribution.

cd /usr/lib/vmware/modules/source
tar xvf vmnet.tar
cd vmnet-only
make
cd ..
tar xvf vmmon.tar
cd vmmon-only
make
cd ..
cp vmmon.o /lib/modules/`uname -r`/kernel/drivers/misc/vmmon.ko
cp vmnet.o /lib/modules/`uname -r`/kernel/drivers/misc/vmnet.ko
depmod -a
systemctl restart vmware.service

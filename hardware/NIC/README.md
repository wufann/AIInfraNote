# CX7

# Thor2
## Driver Install
```
echo -e "\n\n============Installing required pkgs============\n\n"
sudo apt -y install linux-headers-"$(uname -r)"  libelf-dev
sudo apt -y install gcc make libtool autoconf  librdmacm-dev rdmacm-utils infiniband-diags ibverbs-utils perftest ethtool  libibverbs-dev rdma-core strace
cd ~/bcm_driver/bcm5760x_230.2.52.0a/drivers_linux/bnxt_rocelib
tar xvf libbnxt_re-230.2.52.0.tar.gz
cd libbnxt_re-230.2.52.0
echo -e "\n\n============Compiling RoCE Lib now============\n\n"
sh autogen.sh
./configure
make
find /usr/lib64/  /usr/lib -name "libbnxt_re-rdmav*.so"  -exec mv {} {}.inbox \;
make install all
sudo sh -c "echo /usr/local/lib >> /etc/ld.so.conf"
sudo ldconfig
cp -f bnxt_re.driver /etc/libibverbs.d/
find . -name "*.so" -exec md5sum {} \;
BUILT_MD5SUM=$(find . -name "libbnxt_re-rdmav*.so" -exec md5sum {} \; |  cut -d " " -f 1)
echo -e "\n\nmd5sum of the built libbnxt_re is $BUILT_MD5SUM"
```

# Pensando
# AWS 搭建 ShadowSocks
## 1 新建ES2 
- 推荐选择服务器地址在亚太地区（东京）
- 选择Ubuntu系统
- 链接选择一个独立的 SSH 客户端
## 2 连接远程服务器 （XShell）
## 3 在ES2上安装shadowsocks server（利用github源码安装）
-Download
```bash
sudo apt-get install --no-install-recommends build-essential autoconf libtool \
        libssl-dev gawk debhelper dh-systemd init-system-helpers pkg-config asciidoc \
        xmlto apg libpcre3-dev zlib1g-dev libev-dev libudns-dev libsodium-dev
git clone https://github.com/shadowsocks/shadowsocks-libev.git
cd shadowsocks-libev
git submodule update --init --recursive
```
-Pre-build configure and install
```bash
# Installation of basic build dependencies
## Debian / Ubuntu
sudo apt-get install --no-install-recommends gettext build-essential autoconf libtool libpcre3-dev asciidoc xmlto libev-dev libc-ares-dev automake libmbedtls-dev libsodium-dev
## CentOS / Fedora / RHEL
sudo yum install gettext gcc autoconf libtool automake make asciidoc xmlto c-ares-devel libev-devel
## Arch
sudo pacman -S gettext gcc autoconf libtool automake make asciidoc xmlto c-ares libev

# Installation of Libsodium
export LIBSODIUM_VER=1.0.13
wget https://download.libsodium.org/libsodium/releases/libsodium-$LIBSODIUM_VER.tar.gz
tar xvf libsodium-$LIBSODIUM_VER.tar.gz
pushd libsodium-$LIBSODIUM_VER
./configure --prefix=/usr && make
sudo make install
popd
sudo ldconfig

# Installation of MbedTLS
export MBEDTLS_VER=2.6.0
wget https://tls.mbed.org/download/mbedtls-$MBEDTLS_VER-gpl.tgz
tar xvf mbedtls-$MBEDTLS_VER-gpl.tgz
pushd mbedtls-$MBEDTLS_VER
make SHARED=1 CFLAGS=-fPIC
sudo make DESTDIR=/usr install
popd
sudo ldconfig

# Start building
./autogen.sh && ./configure && make
sudo make install
```
-shadowsocks configure
create config.json
```
vim /home/ubuntu/config.json
```
```
{
    "server":"0.0.0.0",
    "server_port":8388,
    "local_address":"127.0.0.1",
    "local_port":1080,
    "password":"*****",
    "timeout":300,
    "method":"aes-256-cfb",
    "fast_open":false
}
```
server_port：指定shadowsocks服务的端口，将用于客户端连接时使用；
password：配置一个密码，客户端连接时使用；
method：选择一个加密方式，默认是aes-256-cfb；
local_port：客户端的代理端口
- run shadowsocks  server
```
sudo ssserver -c /home/ubuntu/config.json -d start //for start
sudo ssserver -c /home/ubuntu/config.json -d stop//for stop
```
设置开机自启动
```
sudo vi /etc/rc.local
```
在exit之前加入
```
sudo ssserver -c /home/ubuntu/config.json -d start
```
-设置EC2安全组
在EC2控制面板中拉倒最右边有个安全组点击进入
操作中选择编辑入站规则设置：
类型：自定义TCP规则
端口：上面设置的server_port
来源：0.0.0.0/0

-重启EC2实例
在EC2控制面板中点击实例右键设置实例状态为重启

-设置shadowsocks  客户端
[下载](http://shadowsocks.org/en/download/clients.html)
参数设置：
服务器地址为EC2的IPv4公有IP
端口和加密方式按照服务器端设置
启动系统代理或者使用浏览器插件SwitchOmega管理即可

<完>




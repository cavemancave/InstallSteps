# InstallSteps
Record various OS install and use steps

# 科学上网
## trojan
[github.com-Alvin9999/new-pac-自建trojan服务器教程](https://github.com/Alvin9999/new-pac/wiki/%E8%87%AA%E5%BB%BAtrojan%E6%9C%8D%E5%8A%A1%E5%99%A8%E6%95%99%E7%A8%8B)  
2022-09-04 test successed on ubuntu 22.04  

## goagent
参考陈皓-左耳朵耗子-[科学上网](https://github.com/haoel/haoel.github.io)  
1. Download script and install
```bash
wget https://raw.githubusercontent.com/haoel/haoel.github.io/master/scripts/install.ubuntu.18.04.sh
chmod +x install.ubuntu.18.04.sh
./install.ubuntu.18.04.sh
```
3. Install docker-ce failed. Manua Install
[Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
4. godaddy edit dns to new host
5. Install reset steps, 

## rabbitpro.org

## mac pac
1. 下载gfwlist.pac，不过safari需要的服务器地址是SOCKS，文件需要修改一下，把SOCKS, SOCKS5啥的都加上[1](https://photolens.tech/catalina-safari-proxy-automatic-configuration-pac-is-not-used/)
```txt
var proxy = 'SOCKS 127.0.0.1:1080;SOCK5 127.0.0.1:1080;SOCKS5 127.0.0.1:1080';
```
2. 安装shadowsocks-libev
3. 新增一个shell脚本sslocalpac.sh，增加权限chmod +x sslocalpac.sh，需要代理时就执行脚本
```bash
cd /Users/zhenni/Downloads/
python3 -m http.server 8080 & 
ss-local -s proxy.server.com -p 1080  -l 1080 -k password  -m chacha20-ietf-poly1305 &
```
4. 代理-》自动代理配置-》”http://localhost:8080/gfwlist.pac“，忽略这些主机的代理设置 '*.local、169.254/16、192.168/16'
5. Git using Proxy [fearblackcat/proxy_for_terminal.md](https://gist.github.com/fearblackcat/850c6e027d5a03017c44daaa6a7ffc30)
```bash
git config --global http.proxy 'socks5://127.0.0.1:1080'
git config --global https.proxy 'socks5://127.0.0.1:1080'
git config --global core.gitproxy 'socks5://127.0.0.1:1080'
# git clone #http* can work , ssh haven't configure
```

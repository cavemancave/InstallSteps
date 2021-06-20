# InstallSteps
Record various OS install and use steps

My laptop :
Lenovo Z470
Intel(R) Core(TM) i3-2310M CPU @ 2.10GHz


# 科学上网
## goagent
参考陈皓-左耳朵耗子-[科学上网](https://github.com/haoel/haoel.github.io)  
210620Test on banwagonHost  
1. Configure VM passwd 
```bash
passwd root
sudo apt upgrade 
reboot
ssh-copy-id -p $PORT root@$IP
ssh -p $PORT root@$IP
```
2. Download script and install
```bash
wget https://raw.githubusercontent.com/haoel/haoel.github.io/master/scripts/install.ubuntu.18.04.sh
chmod +x install.ubuntu.18.04.sh
./install.ubuntu.18.04.sh
```
3. Install docker-ce failed. Manua Install
[Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
4. godaddy edit dns to new host
5. Install reset steps, 

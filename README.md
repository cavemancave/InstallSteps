# InstallSteps
Record various OS install and use steps

My laptop :
Lenovo Z470
Intel(R) Core(TM) i3-2310M CPU @ 2.10GHz


# 科学上网
## goagent
陈皓-左耳朵耗子-[科学上网](https://github.com/haoel/haoel.github.io)
210620Test banwagonHost

### Configure passwd 
```
passwd root
sudo apt upgrade 
reboot
ssh-copy-id -p $PORT root@$IP
ssh -p $PORT root@$IP
```

### use script
```bash
wget https://raw.githubusercontent.com/haoel/haoel.github.io/master/scripts/install.ubuntu.18.04.sh
chmod +x install.ubuntu.18.04.sh
./install.ubuntu.18.04.sh
```

### Install docker-ce failed. Manua Install
[Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/)

### godaddy edit dns to new host
### Install reset steps, 

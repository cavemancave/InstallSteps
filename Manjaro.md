# manjaro-kde-17.1.2-stable-x86_64.iso

# record troubleShooting along my use

# wifi重启后不能自动连接
修改Wi-Fi安全中的密码为“为所有用户保存密码”
 

# 安装搜狗输入法 
参考
http://blog.csdn.net/aaazz47/article/details/77416136
## 安装archlinuxcn-keyring失败 
```bash
[xgh@xgh-pc ~]$ sudo pacman -S archlinuxcn-keyring
警告：database file for 'archlinuxcn' does not exist
错误：未找到目标：archlinuxcn-keyring
```
参考
http://bbs.archlinuxcn.org/viewtopic.php?pid=26225
https://www.archlinuxcn.org/gnupg-2-1-and-the-pacman-keyring/

## 输入法无法激活
安装kcm-fcitx 
但是一直无法激活， 
修改（新增）～/.xprofile后注销重新登录生效。

```bash

export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS=@im=fcitx

```
# 调节屏幕亮度 

# 梯子
## 安装streisand

### wireguard重启后连接不上的问题
参考https://wiki.archlinux.org/index.php/WireGuard
需要启动
systemctl enable NetworkManager-wait-online.service
或
systemctl enable systemd-networkd-wait-online.service

## 安装algo

#系统更新失败
```
(127/127) 正在检查密钥环里的密钥                   [###################] 100%
(127/127) 正在检查软件包完整性                     [###################] 100%
错误：linux414: signature from "Philip Müller (Called Little) <philm@manjaro.org>" is unknown trust
:: 文件 /var/cache/pacman/pkg/linux414-4.14.25-1-x86_64.pkg.tar.xz 已损坏 (无效或已损坏的软件包 (PGP 签名)).
打算删除吗？ [Y/n] 
```
Try
```
sudo pacman -Sy archlinux-keyring manjaro-keyring
sudo pacman-key --populate archlinux manjaro
sudo pacman-key --refresh-keys
```
> If one fails, try the next then retry, and once all succeed retry the update.


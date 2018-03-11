# manjaro-kde-17.1.2-stable-x86_64.iso

 
Record various OS install and use steps

# install input-method
参考https://wiki.archlinux.org/index.php/Fcitx_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87) 
打开octopi，安装fcitx-im组 
安装kcm-fcitx 
但是一直无法激活， 
修改（新增）～/.xprofile后注销重新登录生效。

```bash

export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS=@im=fcitx

```

# adjust screen lightness 



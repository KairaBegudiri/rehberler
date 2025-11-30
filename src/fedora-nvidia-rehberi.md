# Fedora'da Nvidia Driverlarını Kurma Rehberi

**Ön Gereksinimler**
Fedora'da Nvidia driverları kurabilmek için non-free repoların etkin olması gerekmektedir. Bunu sağlıyorsanız devam edebilirsiniz. 

Sağlamıyorsanız:
```bash
sudo dnf install \
https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm \
https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```

**Nvidia Driverlarının İndirilmesi**
```
sudo dnf install akmod-nvidia xorg-x11-drv-nvidia-cuda
```

**Önyükleme ve Modül**
```bash
sudo akmods --force
sudo dracut --force
```

Ardından;
```bash
sudo reboot
```

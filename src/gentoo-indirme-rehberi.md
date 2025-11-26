# Türkçe Hızlı Gentoo UEFI Kurulum Rehberi
Gentoo, tamamen manuel şekilde kurulum yaptığınız ve ileri-seviye kullanıcılara yönelik kaynak-kod tabanlı paket yöneticisi olan portageyi kullanan bir GNU/Linux dağıtımıdır. Gentoo kurulumu yapmak için Gentoo isosuna ihtiyacınız yoktur. Host sistem görevi görmesi için herhangi bir gnu/linux dağıtımının live isosunu host sistem olarak kullanabilirsiniz. Target partition, host sistemden farklı ise farklı bir dağıtımın isosunu host olarak kullanmadan, etrafta hiç bir iso olmadan da Gentoo kurulumu yapabilirsiniz. 

## Bölümlendirme
İlk olarak Gentoo için bölüm ayıralım. İsteğe göre swap açabilirsiniz, biz açmadığınızı varsayacağız ama açmak isteyenlere de nasıl yapıldığını göstereceğiz.

diskimiz üzerinden `fdisk` veya `cfdisk` ile bölümleri oluşturalım
```bash
nvme0n1     259:0    0 931,5G  0 disk 
├─nvme0n1p1 259:1    0     1G  0 part
└─nvme0n1p2 259:2    0 930,5G  0 part 
```

Bölümlerimizi uygun şekilde biçimlendirelim, aksi takdirde sistemi kuramayız.
```bash
# mkfs.vfat -F 32 /dev/nvme0n1p1
# mkfs.ext4 /dev/nvme0n1p2
```
Eğer ext4 yerine btrfs kullanmak isterseniz;
```bash
# mkfs.btrfs /dev/nvme0n1p2
```

Swap aktif etmek isteyenler için;
```bash
# mkswap /dev/swapbölümü && swapon /dev/swapbölümü
```

## Root Dosya Sistemini Yerleştirme
Gentoo'da rootfsi elle yerleştirmemiz gerekmektedir. 

```bash
# mkdir -p /mnt/gentoo/ && mkdir -p /mnt/gentoo/efi
```

ille de ismi /mnt/gentoo olmak zorunda değildir. Bu sadece yer tutucu bir isimdir. Bu isim sadece host sisteminiz için önem arz edecektir. Gentoo kurulumunuzun bundan haberi bile olmayacaktır. 

Şimdi dosya sistemini bağlayalım.
```bash
# mount /dev/nvme0n1p2 /mnt/gentoo
# mount /dev/nvme0n1p1 /mnt/gentoo/efi
```

Şimdi rootfsi indirip disk bölümümüze yerleştirebiliriz, `cd` komutu ile hedef rootfsi açalım
```bash
$ cd /mnt/gentoo
```

`https://distfiles.gentoo.org/releases/amd64/autobuilds/` adresinden size uygun olan rootfsi indirin. Eğer OpenRC kullanmak isterseniz, `https://distfiles.gentoo.org/releases/amd64/autobuilds/current-stage3-amd64-openrc` altındaki `stage3-amd64-openrc-*******.tar.xz` paketini indirebilirsiniz.

Gentoo'ya sadık kalma amacıyla biz OpenRC ile devam edeceğiz

Rehberin yazıldığı `26 kasım 2025` tarihinde en güncel rootfs ile:

```bash
# wget https://gentoo.osuosl.org/releases/amd64/autobuilds/current-stage3-amd64-openrc/stage3-amd64-openrc-20251123T153051Z.tar.xz
```

şimdi rootfsi açalım: 
```bash
# tar xpvf stage3* --xattrs-include='*.*' --numeric-owner
```

Her şey açıldıktan sonra tar dosyasıyla işimiz bitmiş olacak, onu silebilirsiniz
```bash
# rm -rf stage3*
```

## Chroot

Şimdi aşağı yukarı kurulumu bitirdik. Ancak bootable hale getirmemiz gerek. 

İnternet sorunu yaşamamak adına host sisteminizin resolv.conf dosyasını yapıştırmanız gerek 

```bash
$ cd /mnt/gentoo
# cp -L /etc/resolv.conf etc
```

Şimdi `/mnt/gentoo` adresine chroot atmanız gerekiyor. 
Host sisteminiz 
Arch Linux ise: `arch-chroot /mnt/gentoo`
Gentoo live iso ise: `arch-chroot /mnt/gentoo`

## Portage
Mevcut Gentoo rootfs'i güncel olmadığından repoları senkronize etmemiz gerekiyor. Aşağıdaki komut ile bunu yapabilirsiniz.
```bash
emerge-webrsync
```

cpu flagleri ayarlayalım:
```bash
emerge --ask app-portage/cpuid2cpuflags
cpuid2cpuflags
echo "*/* $(cpuid2cpuflags)" > /etc/portage/package.use/00cpu-flags
```

Şimdi tüm paketleri güncelleyelim:
```bash
emerge -avuDN @world
```

## Kullanıcı Hesabı Oluşturma
Sonlara yaklaştık. Şimdi bir kullanıcı hesabı ekleyeceğiz. Burası geleneksel dağıtımlarla aynı işliyor. ama öncelikle root hesabının parolasını ayarlayalım.

```ksh
passwd
```

Kullanıcı ekleyelim:
```bash
useradd -g users -G wheel,portage,audio,video,usb,cdrom -m kayra
```
Bu rehberde kullanıcı olarak `kayra` adı kullanılmış olsa da siz kendi isminizi kullanmalısınız.
Şimdi `kayra` kullanıcısının şifresini ayarlayalım. Bu adım atlanmamalıdır, aksi takdirde `kayra` kullanıcısı ile giriş yapılamayacaktır
```bash
passwd kayra
```

## Sistem Lokalini Ayarlama
`/etc/locale.gen` adresinden istediğiniz dili seçin ve başındaki `#` karakterini kaldırın.
Ardından;
```bash
locale-gen
eselect locale list
eselect locale set X
env-update && source /etc/profile
```

Şimdi `/etc/conf.d/hostname` yolundan hostnameyi ayarlayalım
```bash
# Örnektir
HOSTNAME="gentoo"
```

Zamanı ayarlayalım:
```bash
ln -sf /usr/share/zoneinfo/Europe/Istanbul /etc/localtime
```

## Fstab
`/etc/fstab` önemlidir, aksi takdirde sistem açılmaz veya salt-okunur modunda açılacaktır.
Örnek FSTAB:
```fstab
/dev/bootbölümünüz  /efi  vfat  defaults  0 2
/dev/rootbölümünüz  /  ext4  defaults  0 1
/dev/swapbölümünüz  none  swap  sw  0 0
```

## Sistemi Bootable Yapalım
`/etc/portage/make.conf` adresinde `USE="dist-kernel"` satırı oluşturalım. Bu bizim use flaglerimiz. 
Linux Firmwareyi indirelim
```bash
mkdir -p /etc/portage/package.license
echo "sys-kernel/linux-firmware linux-fw-redistributable" >> /etc/portage/package.license/linux-firmware
emerge --ask sys-kernel/linux-firmware
```

Eğer Intel işlemciye sahipseniz Intel microcode indirmeniz tavsiye edilir
```bash
# Sadece Intel işlemciler için:
echo "sys-firmware/intel-microcode intel-ucode" >> /etc/portage/package.license/intel-microcode
emerge --ask sys-firmware/intel-microcode
```

Şimdi Linux kernelin indirelim
```bash
Installing a distribution kernel:
echo "sys-kernel/installkernel dracut" >> /etc/portage/package.use/installkernel
emerge --ask sys-kernel/installkernel sys-kernel/gentoo-kernel-bin
```

Tebrikler! Artık Gentoo sisteminiz bootable halde. Eğer Gentoo'nuzu ana dağıtımınız olarak kullanmak isterseniz `GRUB` da kurmak isteyeceksinizdir.
GRUB kurmak için:
```bash
echo 'GRUB_PLATFORMS="efi-64"' >> /etc/portage/make.conf
emerge --ask sys-boot/grub
grub-install --efi-directory=/efi
grub-mkconfig -o /boot/grub/grub.cfg
```

Ek olarak interneti de aktif etmenizi öneririz:
```bash
rc-update add dhcpcd default
rc-service dhcpcd start
```
Eğer wi-fi kullanıyorsanız veya KDE/Gnome kurmak isterseniz `networkmanager` da indirmek isteyeceksinizdir.
```bash
emerge --ask net-misc/networkmanager
rc-update add NetworkManager default
```

Sistem loglarını görmek isterseniz
```bash
emerge --ask app-admin/sysklogd
rc-update add sysklogd default
rc-update add cronie default
```

İşinize yarayabilecek bazı araçlar:
```bash
emerge --ask app-portage/gentoolkit app-portage/eix media-sound/alsa-utils sys-boot/efibootmgr app-text/wgetpaste sys-apps/cpuid sys-apps/ethtool sys-apps/usbutils
```

## Kapanış
```bash
exit
umount -R /mnt/gentoo
reboot
```

Okuduğunuz için teşekkür ederim

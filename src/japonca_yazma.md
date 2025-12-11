# KDE'de Japonca Yazma Rehberi

Yeni kullanıcılar Linux'ta Japonca yazılar nasıl yazılıyor emin olamayabiliyor. Bu rehber, Japonca yazmak isteyen kullanıcıların nasıl yapacağını anlatmakta.

!!! warning
    
    Bu rehber henüz bitmiş değil. Bu rehber, 4 aşama olarak planlanmıştır. Bu aşamalar, sırasıyla Arch, Fedora, Debian/Kubuntu ve Gentoo için güncellenecektir. Mevcut sürüm sadece Arch Linux'u kapsar. 
    
## Arch Linux

### 1. Fontların İndirilmesi
Arch Linux varsayılan olarak Japonca fontları olmadan gelir. Bu durumda bizim bu fontları elle indirmemiz gerekmekte. 
```bash
sudo pacman -S noto-fonts-cjk && sudo fc-cache -fv
```

Başarıyla fontları indirdik. Şimdi oturumu kapatıp yeniden açın.


Oturumu kapatmak istemiyorsanız alternatif olarak şunu da yapabilirsiniz 
```bash
kquit6 plasmashell && kstart5 plasmashell
```
Ancak oturumu kapatıp yeniden açmanız en iyi yol olacaktır.

### Fcitx5'in İndirilmesi

Şimdi fcitx5-mozc paketini indirelim
```bash
sudo pacman -S fcitx5-mozc fcitx5-configtool fcitx5-qt fcitx5-gtk
```

ardından, `/etc/environment` yoluna aşağıdaki satırları ekleyin:
```conf
GTK_IM_MODULE=fcitx
QT_IM_MODULE=fcitx
XMODIFIERS=@im=fcitx
```

### Fcitx5'in Ayarlanması
Bu adıma geldiğimiz vakit, KDE sistem ayarlarında `Keyboard > Virtaul Keyboard` altında `Fcitx 5 Wayland Launcher` ve `Fcitx 5` klavyeleri ile karşılaşacaksınız, size uygun olanı seçin.

Ardından, yine kde ayarlarında `Language & Time` üst başlığı altında `Input Method` (`Giriş yöntemi`) sekmesini göreceksiniz. Sekme içerisinde sol altta `Select system layout` butonuna basın ve önünüze çıkan pencerede `Layout > Turkish` şeklinde düzenleme yapın. Tekrar Input Method'un ana sayfası ile karşılaşacaksınız. Input Method Off altındaki İngilizce klavyeyi kaldırın ve Türkçe'yi ekleyin. Türkçe klavyeyi ekledikten sonra mozc klavyeyi de ekleyin aynı alandan. Sağ alttan Apply butonuna bastıktan sonra sisteminiz artık Japonca yazabilir hale gelecek.

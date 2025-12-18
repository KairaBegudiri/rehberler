# Hangi Dağıtımı Seçmeliyim?

> Yazar: [Kayra](https://x.com/QMinun)

Ne yaptığınızı biliyorsanız neyi hangi dağıtımda yaptığınız genelde pek bir şey farketmez. Ancak bazı dağıtımlar bazı şeyler için daha uygundur. Bu rehberde hangi dağıtım ne için daha uygun, ne özellikler sağlıyor? Basitçe özetleyeceğiz.

## Oyun Odaklı Dağıtımlar
Çoğu modern dağıtım, Valve'ın Proton uyumluluk katmanı sayesinde çoğu oyunu desteklemektedir. Modern Proton sürümü sayesinde Windows için yapılmış her 10 Steam oyunundan 9 tanesi Linux'ta sorunsuz şekilde çalışmaktadır.

Ancak bazı online oyunlar, anti-cheat nedeniyle Linux'u desteklemez. Örneğin bu rehberin yazıldığı 18 Aralık 2025 tarihinde Valorant, Fortnite, League of Legends hiç bir şekilde Linux'ta çalışmıyor.

!!! Note "Bu her zaman geçerli değil"

    Örneğin, tüm Valve oyunları Counter Strik 2, DOTA 2 vs dahil olmak üzere Linux'ta native şekilde çalışır ve valve-anticheat (ve valve-anticheat kullanan oyunlar) Linux'ta çalışır.

[Are We Anticheat Yet?](https://areweanticheatyet.com/) sitesi, Linux'u destekleyen online oyunları listeler.

[Protondb](https://www.protondb.com/), Steam oyunlarının Linux'taki durumunu listeler.

!!! Note "Gacha Oyunları Hakkında"

    Çoğu gacha oyunu gri alandadır. Resmi olarak desteklemeseler de müdahale etmezler. Mesela Genshin Impact, Honkai Star Rail ve Zenless Zone Zero, Duet Night Abyss buna örnek gösterilebilir. Wuthering Waves, Reverse 1999, Tower of Fantasy gibi oyunlar ise doğrudan destekler ve sorunsuz şekilde çalışır. Genshin Impact için [bu projeye](https://github.com/an-anime-team/an-anime-game-launcher) bakınız


### Bazzite
[Bazzite](https://bazzite.gg/), Valve'ın SteamOS 3'üne benzer şekilde tasarlanmış Fedora tabanlı bir Linux dağıtımıdır. Steam Deck de dahil olmak üzere taşınabilir cihazlar ve masaüstü bilgisayarlar için destek sunar. Hem sıradan hem de ileri düzey Linux oyuncuları için sorunsuz bir kullanıma hazır deneyim sunmayı amaçlamaktadır.

### Nobara
[Nobara Project](https://nobaraproject.org/), Fedora Linux'un, kullanıcı dostu iyileştirmelerle değiştirilmiş bir sürümüdür. Fedora, güçlü bir iş istasyonu işletim sistemi olmakla birlikte, üçüncü taraf veya tescilli yazılımları içeren paketler genellikle temiz bir kurulumda yer almaz. Bu nedenle, özellikle "tıklayıp kullan" şeklinde çalışan tipik kullanıcılar, tarayıcı ve ofis belgeleri gibi temel işlevlerin ötesine geçmek istediklerinde, genellikle belgeleri araştırmak için fazladan zaman harcamak zorunda kalabilirler.

Fedora’da eksik olan ve özellikle oyunlar açısından önemli olan bazı bileşenler arasında WINE bağımlılıkları, OBS Studio, GStreamer gibi üçüncü taraf codec paketleri, NVIDIA gibi üçüncü taraf sürücüler ve çeşitli küçük paket düzeltmeleri bulunmaktadır.

### CachyOS
[CachyOS](https://cachyos.org/), Arch Linux tabanlı bir Linux dağıtımıdır. Hız ve güvenlik optimizasyonlarına odaklanır – varsayılan Linux çekirdeği, BORE (Burst-Oriented Response Enhancer) zamanlayıcısı ile ileri seviyede optimize edilmiştir. Masaüstü paketleri ise LTO, x86-64-v3 ve x86-64-v4, Zen 4 optimizasyonları, güvenlik bayrakları ve performans iyileştirmeleri ile derlenmiştir. Sunulan masaüstü ortamları ve pencere yöneticileri arasında KDE, GNOME, Xfce, i3wm, Wayfire, LXQt, OpenBox, Cinnamon, COSMIC, UKUI, LXDE, MATE, Budgie, Qtile, Hyprland ve Sway bulunmaktadır. CachyOS, hem grafiksel hem de komut satırı tabanlı yükleyicilerle birlikte gelir.

## Son Kullanıcı Odaklı Dağıtımlar

### Fedora
[Fedora Linux](https://www.fedoraproject.org/) (eski adıyla, Fedora Core), açık kaynak kodlu ve özgür bir Linux dağıtımı. Dünya çapında bir özgür yazılım topluluğu olan Fedora Projesi tarafından geliştirilmekte ve yönetilmekte, Red Hat tarafından desteklenmektedir. 

!!! Note 

    * Bu topluluk yeni kullanıcılara Fedora önermektedir.

    * Fedora, Ubuntu gibi dağıtımlara kıyasla daha temiz ve saf bir GNOME masaüstü ortamı deneyimi sağlar.

    * Çoğu stabil dağıtıma kıyasla yeni yazılımlar daha erken depolara eklenir.

    * Kapalı kaynak Snap yazılım deposu yerine topluluk tarafından çokça tercih edilen Flatpak ile gelir.

### Zorin OS
[ZorinOS](https://zorin.com/os/), Ubuntu tabanlı bir Linux dağıtımıdır ve hem ücretsiz hem de ücretli sürümleri bulunmaktadır. Varsayılan olarak GNOME ve XFCE 4 masaüstü ortamlarını kullanır, ancak masaüstü arayüzü Windows veya macOS'a alışkın kullanıcılar için oldukça özelleştirilmiştir.

### Ubuntu Desktop
[Ubuntu](https://ubuntu.com/download), Linux tabanlı özgür ve ücretsiz bir işletim sistemidir. Bilgisayarlar, sunucular ve akıllı telefonlara yönelik olarak geliştirilmektedir. Ubuntu projesi Linux ve özgür yazılımın, bilgisayar kullanıcılarının günlük yaşamının bir parçası haline gelmesi amacıyla başlatılmış olup ilk kararlı masaüstü sürümü Ekim 2004'te yayınlanmıştır. Ubuntu'nun masaüstü sürümü günümüzde 40 milyonu aşkın kullanıcı sayısıyla dünyanın en yaygın kullanılan masaüstü Linux dağıtımı konumundadır.

### Linux Mint
[Linux Mint](https://linuxmint.com/), Ubuntu tabanlı, kullanıcı dostu bir Linux dağıtımıdır. Windows’tan geçenler için tasarımı tanıdık gelir; masaüstü ortamı olarak Cinnamon, MATE veya XFCE alternatifleri ile gelir. Kurulumdan sonra neredeyse her şey hazır gelir: medya codec’leri, ofis uygulamaları, sürücüler vs. Stabil, hafif ve “kur ve kullan” tarzı bir sistemdir. Yeni başlayanlar için çok uygundur ama deneyimli kullanıcıyı da yormaz.

### Pop!\_OS

[Pop OS](https://system76.com/pop/) (Pop!\_OS olarak da stilize edilir), Ubuntu tabanlı, ücretsiz ve açık kaynaklı bir Linux dağıtımıdır. Kendi geliştirmiş oldukları COSMIC masaüstü ortamı ile birlikte gelir. Dağıtım, Amerikalı Linux bilgisayar üreticisi System76 tarafından geliştirilmiştir.

## Yapay Zeka Kullanıcı/Geliştiricileri İçin Dağıtımlar

### RHEL
[Red Hat Enterprise Linux](https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux), Red Hat'in Linux dağıtımıdır. Sunucuları ve iş istasyonlarını hedefler. RPM bağımlılık sistemini kullandığından ve bu son derece yaygın olduğundan epey geniş bir uygulama yelpazesine sahiptir. Alternatif olarak Fedora için de bu dediklerimiz geçerli olacaktır

### Ubuntu Server/Desktop
Ubuntu, yapay zeka araçları için kendi paket yöneticisinde en geniş uygulama yelpazesine sahip işletim sistemidir. Ubuntu, bu alanda sektörde bir standard haline gelmiş durumda.

!!! Note "Ubuntu"

    Nvidia, geçtiğimiz günlerde Asus işbirliği ile kendi Linux dağıtımını yaptı. Bu dağıtım, Ubuntu'nun bir çatalı olarak yapıldı. 

!!! Note "Alternatif"

    Ne yaptığınızı biliyorsanız [DIY]("## "Kendin yap" felsefesinde bir dağıtım arıyorum") kategorisindeki dağıtımlar da güzel bir alternatif olabilmektedir.

## Sürekli Güncel Kalan Dağıtımlar

### OpenSUSE
[openSUSE](https://get.opensuse.org/tumbleweed/), openSUSE Projesi tarafından geliştirilen ücretsiz ve açık kaynaklı bir Linux dağıtımıdır. İki ana varyasyonda sunulmaktadır: Tumbleweed (yukarı akışlı bir sürüm dağıtımı) ve Leap (SUSE Linux Enterprise kaynaklı, kararlı bir sürüm dağıtımı)

### EndeavourOS
[EndeavourOS](https://endeavouros.com/), Antergos'un devamıdır. Arch tabanlı, kolay kurulum ve önceden yapılandırılmış bir masaüstü ortamı sunmaktadır. EndeavourOS hem çevrimdışı hem de çevrimiçi kurulum seçenekleri sunar.


## Stabil Bir Dağıtım Arıyorum

### Manjaro
[Manjaro](https://manjaro.org/), masaüstü kullanıcı odaklı, kullanıcı dostu bir Linux dağıtımıdır. Arch Linux'u temel alır. Manjaro, Stabil yuvarlanan bir Arch dağıtımıdır. Paketleri bir süre bekletir ve stabil olduklarına karar verdikleri en güncel paketleri dağıtıdır. Manjaro, Arch Linux-LTS kernelini en güncel kanaldan dağıtır. Varsayılan olarak KDE Plasma kullanır

### Debian
[Debian](https://www.debian.org/), kararlılık ve özgür yazılım felsefesini ön planda tutan, uzun süredir geliştirilen popüler bir Linux dağıtımıdır. Geniş bir paket deposuna sahip olup, çok sayıda mimariyi destekler. Paket yönetimi için `dpkg` sistemi kullanılır ve genellikle sunucu ortamlarında ve masaüstünde tercih edilir. Debian, yeni başlayanlar için biraz daha sabır gerektirebilir ama sağlam, güvenilir ve geniş topluluk desteği sayesinde uzun vadeli projelerde tercih edilir.

### Slackware
[Slackware](http://www.slackware.com/), 1992 yılında Patrick Volkerding tarafından başlatılan Slackware Linux, hâlen geliştirilen en eski Linux dağıtımıdır. İlk kararlı sürümü 1993 Temmuz'unda yayınlanmıştır. Grafiksel konfigürasyon araçları ve basit arayüzler sunmaktan ziyade, sizin Linux'a aşina olmanızı bekleyen bir yapıya sahiptir.

## Çok eski bir bilgisayarım var ve oldukça hafif bir dağıtım arıyorum

### antiX

[antiX](https://antixlinux.com/), başlangıçta MEPIS tabanlı olan bir Linux dağıtımıdır. MEPIS'in kendisi de Debian'ın kararlı sürümüne dayanır. antiX, ilk olarak MEPIS'in KDE masaüstü ortamını Fluxbox ve IceWM pencere yöneticileriyle değiştirerek, daha eski ve düşük donanımlı x86 tabanlı sistemler için uygun hale getirilmiştir. Debian'dan farklı olarak, antiX systemd başlatma sistemini kullanmaz; bunun yerine, varsayılan başlatma sistemi olarak SysVinit veya Runit ayarlanmış olan kalıplar sunar.

### Q4OS

[Q4OS](https://q4os.org/), klasik bir kullanıcı arayüzü (Trinity) ve basit araçlar sunar. Google Chrome, VirtualBox ve geliştirici araçları gibi karmaşık üçüncü taraf uygulamalar için kararlı API'ler sağlamak üzere tasarlanmış Debian tabanlı bir masaüstü Linux dağıtımıdır. Sistem, çok düşük donanım gereksinimleri nedeniyle sanal bulut ortamları için de çok kullanışlıdır.

### Puppy Linux

[Puppy Linux](https://puppylinux-woof-ce.github.io/), düşük donanım gereksinimi ve kolay kullanımıyla öne çıkan hafif bir Linux dağıtımıdır. Sistem tamamen RAM üzerinden çalışabilir (64-bit ~600 MB, 32-bit ~300 MB), böylece açılıştan sonra kurulum medyasına gerek kalmaz.

İçinde temel uygulamalar ve hafif web tarayıcıları bulunur. Başta Barry Kauler tarafından geliştirilen Puppy, artık topluluk tarafından sürdürülüyor. Woof aracıyla diğer dağıtımların paketlerinden Puppy türevi oluşturulabilir.

### Tiny Core Linux

[Tiny Core Linux (TCL)](http://www.tinycorelinux.net/), BusyBox ve FLTK kullanan, minimum sistemle çalışan son derece hafif bir Linux dağıtımıdır. 11–16 MB boyutundadır ve işlevsellik eklentilerle sağlanır. Baş geliştiricisi, Damn Small Linux'tan tanıdığımız Robert Shingledecker’dır. Açık kaynaklıdır ve GPLv2 lisansı ile dağıtılır.


## "Kendin yap" felsefesinde bir dağıtım arıyorum

!!! warning

    Bu ileri düzey kullanıcılar içindir. Eğer ne yaptığınızı bilmiyorsanız bu dağıtımlardan uzak durun.

### Arch Linux
[Arch Linux](https://archlinux.org/), ileri seviye kullanıcıları hedefleyen bağımsız bir Linux dağıtımıdır. x86_64 mimarisini hedefler. Bağımsız paket yöneticileri olan `pacman` aracını kullanır. Bağımlılık takibiyle birlikte, en güncel paketleri dağıtır

### Gentoo
[Gentoo Linux](https://www.gentoo.org/); geliştiricilere ve ağ profesyonellerine yönelik, çok yönlü, hızlı ve tamamen özgür bir Linux dağıtımıdır. Diğer dağıtımlardan farklı olarak Gentoo, Portage adı verilen gelişmiş bir paket yönetim sistemine sahiptir. Portage, BSD port geleneğine dayanan gerçek bir "ports" sistemidir; ancak Python tabanlıdır ve beraberinde birçok gelişmiş özellik sunar. Bu özellikler arasında bağımlılık yönetimi, ince ayarlı (fine-grained) paket yönetimi, "fake" (OpenBSD stili) kurulumlar, güvenli paket kaldırma (unmerging), sistem profilleri, sanal paketler ve yapılandırma dosyası yönetimi gibi pek çok imkan yer almaktadır. Gentoo, ileri seviye kullanıcılar için değildir. Gentoo, doğrudan teknik kullanıcılara yöneliktir. Gentoo Linux kurulumu için bir ISO indirmezsiniz veya kullanmazsınız. Doğrudan sisteminize kendiniz inşaa edersiniz.

### NixOS
[NixOS](https://nixos.org/); sistem yapılandırma yönetimindeki teknolojileri en üst seviyeye çıkarmayı hedefleyen, bağımsız olarak geliştirilmiş bir GNU/Linux dağıtımıdır. NixOS'ta çekirdek, uygulamalar, sistem paketleri ve yapılandırma dosyaları dahil olmak üzere tüm işletim sistemi [Nix paket yöneticisi](https://search.nixos.org/packages) tarafından inşa edilir. Nix, tüm paketleri birbirinden izole bir şekilde saklar; bunun bir sonucu olarak sistemde geleneksel /bin, /sbin, /lib veya /usr dizinleri bulunmaz, tüm paketler bunun yerine /nix/store altında tutulur.

NixOS’un diğer yenilikçi özellikleri arasında güvenilir güncellemeler, sistemin eski haline döndürülebilmesi (rollbacks), yeniden üretilebilir (reproducible) sistem yapılandırmaları, binary (hazır derlenmiş) destekli kaynak tabanlı model ve çok kullanıcılı paket yönetimi yer alır. NixOS bir araştırma projesi olarak başlamış olsa da; günümüzde donanım tanıma, varsayılan masaüstü olarak KDE ve sistem servislerini yönetmek için systemd gibi özelliklere sahip, tam işlevsel ve kullanıma hazır bir işletim sistemidir

### Void Linux
[Void](https://voidlinux.org/), monolitik Linux çekirdeğine dayanan, bağımsız olarak geliştirilmiş, genel amaçlı bir işletim sistemidir. Kullanıcıların yazılımları hızlı bir şekilde yüklemelerine, güncellemelerine ve kaldırmalarına veya XBPS kaynak paketleri koleksiyonunun yardımıyla kaynaklardan doğrudan yazılım oluşturmalarına olanak tanıyan hibrit bir ikili/kaynak paket yönetim sistemine sahiptir. Dağıtımın diğer özellikleri arasında Raspberry Pi tek kartlı bilgisayarlar (hem armv6 hem de armv7) için destek, günlük güncellemelerle yuvarlanan sürüm modeli ve “runit” adlı yerel init sistemi bulunmaktadır.

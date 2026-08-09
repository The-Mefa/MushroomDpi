# MushroomDpi'yi Kaldırma Rehberi

## MushroomDpi Sistemimde Kalıcı Bir Değişiklik Yapar mı?

Hayır. MushroomDpi sisteminizde **hiçbir kalıcı değişiklik yapmaz**. Konsol penceresini kapattığınız anda çalışması durur ve sisteminizle arasında hiçbir bağlantı kalmaz. Herhangi bir servis kurmaz, kayıt defterine yazmaz, dosya sisteminize kalıcı bir şey eklemez.

## MushroomDpi'yi ve Dosyalarını Tamamen Silmek

1. `MushroomDpi_Baslat.cmd` ile açtığınız konsol penceresini kapatın (bu, çalışmayı anında durdurur).
2. Programı çıkarttığınız klasörü (içindeki `MushroomDpi.exe`, `WinDivert.dll`, `WinDivert64.sys` dosyalarıyla birlikte) tamamen silin.

Bu kadar. Kurulu bir Windows servisi olmadığı için başka bir kaldırma adımına gerek yoktur.

## DNS Atamasını Geri Almak

Eğer Windows ayarlarından elle bir DNS adresi girdiyseniz (MushroomDpi'nin kendisi DNS'i sadece kendi çalıştığı süre boyunca, uygulama seviyesinde yönlendirir; ama siz ayrıca Windows'un DNS ayarını da değiştirdiyseniz), bunu geri almak için:

### Windows 10

- Windows arama kısmına **"Ağ bağlantılarını görüntüle"** yazıp açın (ya da `Win+R` ile **ncpa.cpl** çalıştırın).
- DNS ataması yaptığınız adaptörü (Wi-Fi veya Ethernet) sağ tıklayıp **Özellikler**'e girin.
- **İnternet Protokolü Sürüm 4 (TCP/IPv4)**'ü seçip **Özellikler**'e tıklayın (IPv6 için de aynısını yapın).
- **DNS sunucu adresini otomatik olarak al** seçeneğini işaretleyip **Tamam**'a basın.
- Bilgisayarınızı yeniden başlatın.

### Windows 11

- **Ayarlar** → **Ağ ve internet** → kullandığınız bağlantı (Wi-Fi/Ethernet) → **Ağ özellikleri**.
- **DNS sunucusu ataması** yanındaki **Düzenle**'ye basıp **Otomatik (DHCP)**'yi seçin.
- Alternatif olarak: **Ayarlar** → **Ağ ve internet** → **Gelişmiş ağ ayarları** → ilgili adaptör → **Diğer bağdaştırıcı seçenekleri** → **Düzenle** → aynı şekilde **İnternet Protokolü Sürüm 4/6** ayarlarını **otomatik al**a çevirin.
- Bilgisayarınızı yeniden başlatın.

## "Dosya Kullanılıyor" Hatası (WinDivert.dll / WinDivert64.sys)

Bu dosyaları silerken hata alıyorsanız, MushroomDpi hâlâ arka planda çalışıyor demektir — önce konsol penceresini kapatın, sonra tekrar deneyin.

> [!NOTE]
> Bu dosyaların açıklamasında veya silme sırasında bir Bitcoin cüzdan adresi görebilirsiniz — bu WinDivert kütüphanesinin geliştiricisi [basil00](https://github.com/basil00)'a ait, tamamen isteğe bağlı bir bağış adresidir ([bağış sayfası](https://reqrypt.org/donate.html)). WinDivert açık kaynaklıdır ve MushroomDpi'nin paket yakalama altyapısını sağlar.

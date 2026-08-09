[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey.svg)](https://www.microsoft.com/windows)
[![Downloads](https://img.shields.io/github/downloads/The-Mefa/MushroomDpi/total.svg)](https://github.com/The-Mefa/MushroomDpi/releases/)
[![Release](https://img.shields.io/github/v/release/The-Mefa/MushroomDpi.svg)](https://github.com/The-Mefa/MushroomDpi/releases/latest)

# MushroomDpi

Türkiye'deki bazı internet servis sağlayıcılarının uyguladığı DPI (Derin Paket İnceleme) engellemelerini VPN kullanmadan aşmak için geliştirilmiş bir araç. Discord ve DPI ile engellenen benzer site/uygulamalara erişimi, internet hızında bir yavaşlamaya sebep olmadan sağlar.

Bu proje, **Mefa** tarafından orijinal [GoodbyeDPI](https://github.com/ValdikSS/GoodbyeDPI) projesi temel alınarak geliştirilmiş ve tamamen Türkçeleştirilmiştir. Bu araç kesinlikle bir VPN değildir; paket seviyesinde DPI'yi kandırma tekniği kullanır.

> [!NOTE]
> Windows 7, 8, 8.1, 10 veya 11'de **yönetici olarak çalıştırmanız** gerekir.

## Kurulum ve Kullanım

**[⬇️ MushroomDpi.zip indir (v1.0.0)](https://github.com/The-Mefa/MushroomDpi/releases/download/v1.0.0/MushroomDpi.zip)**

1. Yukarıdaki linkten veya [Releases](https://github.com/The-Mefa/MushroomDpi/releases/latest) sayfasından en son sürümü indirin.
2. ZIP dosyasını istediğiniz bir klasöre çıkarın (klasörü daha sonra taşımayın).
3. `MushroomDpi_Baslat.cmd` dosyasına çift tıklayın. Yönetici yetkisi istenirse **Evet** deyin.
4. Konsol penceresi açık kaldığı sürece MushroomDpi çalışır durumda kalır.

> [!TIP]
> Varsayılan olarak Yandex DNS (77.88.8.8) kullanılır. Farklı bir DNS istiyorsanız `MushroomDpi_Baslat.cmd` dosyasını bir metin düzenleyiciyle açıp `--dns-addr` parametresini değiştirebilirsiniz.

## Kaynaktan Derleme

Gerekenler: [MSYS2](https://www.msys2.org/) (mingw-w64-x86_64-gcc, make) ve [WinDivert 2.2.0](https://reqrypt.org/download/WinDivert-2.2.0-D.zip) SDK.

```bash
cd src
make CPREFIX=x86_64-w64-mingw32- BIT64=1 \
  WINDIVERTHEADERS=../WinDivert-2.2.0-D/include \
  WINDIVERTLIBS=../WinDivert-2.2.0-D/x64 \
  CCWINDRES=windres -j4
```

Proje VS Code ile geliştirilmek üzere yapılandırılmıştır (`.vscode/`), `Ctrl+Shift+B` ile derleyebilirsiniz.

## Virüs Uyarısı Hakkında

Bu araç, `WinDivert.dll` ve `WinDivert64.sys` adlı açık kaynaklı bir Windows paket inceleme/değiştirme kütüphanesi kullanır ([basil00/WinDivert](https://github.com/basil00/WinDivert)). Bazı antivirüs programları (özellikle Kaspersky) bu dosyaları yanlışlıkla zararlı olarak işaretleyebilir — bu bilinen bir yanlış pozitif durumudur. Kaynak kodun tamamı bu depoda açık, isteyen inceleyebilir.

## Sık Karşılaşılan Sorunlar

- **"WinDivert dosyaları bulunamadı" hatası:** Antivirüs programınıza uygulamanın bulunduğu klasörü istisna olarak ekleyin.
- **Bazı sitelerin açılmaması:** `MushroomDpi_Baslat.cmd` içindeki parametreleri değiştirerek farklı modları deneyebilirsiniz (bkz. `MushroomDpi.exe --help` çıktısı).

## Katkı ve Lisans

Bu proje [Apache 2.0](LICENSE) lisansı altında dağıtılmaktadır, orijinal [GoodbyeDPI](https://github.com/ValdikSS/GoodbyeDPI) projesine ve geliştiricisine teşekkürler.

## Yasal Uyarı

> [!IMPORTANT]
> Bu uygulamanın kullanımından doğan her türlü yasal sorumluluk kullanıcıya aittir. Uygulama yalnızca eğitim ve araştırma amaçlıdır; kullanmak ya da kullanmamak kullanıcının kendi tercihidir.

<div align="center">

# MiBox Konsol

### Android TV cihazlarınızı bilgisayarınızdan yönetin.

Mi Box, Mi TV Stick ve Android TV için ADB tabanlı masaüstü yönetim merkezi. Kumanda, uygulama ve APK yönetimi, cihaz sağlığı, ağ araçları ve güvenli bakım tek bir arayüzde.

[⬇️ Son sürümü indir](https://github.com/maventra-dev/MiBoxKonsol/releases/latest) · [🐞 Hata bildir](https://github.com/maventra-dev/MiBoxKonsol/issues/new) · [✨ Özellik öner](https://github.com/maventra-dev/MiBoxKonsol/issues/new)

<br>

[![Latest Release](https://img.shields.io/github/v/release/maventra-dev/MiBoxKonsol?display_name=tag&sort=semver)](https://github.com/maventra-dev/MiBoxKonsol/releases/latest)
[![Build](https://img.shields.io/github/actions/workflow/status/maventra-dev/MiBoxKonsol/release.yml?branch=master&label=Windows%20build)](https://github.com/maventra-dev/MiBoxKonsol/actions/workflows/release.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-8b7cf6.svg)](LICENSE)
[![Windows](https://img.shields.io/badge/Windows-10%20%7C%2011-2563eb.svg)](https://www.microsoft.com/windows)

</div>

## Ekran görüntüleri

Arayüz görselleri örnek içerik kullanır; gerçek cihaz adresi veya kişisel dosya yolu içermez.

<p align="center">
  <img src="docs/screenshots/showcase.gif" alt="MiBox Konsol ekranları: kumanda, sağlık, uygulamalar ve kurulum" width="100%">
</p>

<p align="center"><sub>Ekranlar sırayla gösterilir.</sub></p>

## Neler yapabilirsiniz?

| Alan | Araçlar |
| --- | --- |
| **Kumanda** | Yön tuşları, ses ve medya kontrolleri, metin gönderme, ekran görüntüsü ve canlı ekran etkileşimi |
| **Uygulamalar** | Kurulu paketleri inceleme, açma, devre dışı bırakma veya kaldırma; APK yedekleme |
| **Kurulum** | Android TV uygulama kataloğu, yerel APK ve bölünmüş APK kurulumu |
| **Sağlık** | Cihaz özeti, donanım ölçümleri, ekran yapılandırması ve arka plan izinleri |
| **Ağ** | ADB cihaz keşfi, kablosuz eşleştirme, Wi-Fi teşhisi ve DNS ayarları |
| **Bakım** | Paket profilleri, durum kaydı ve geri yükleme, dosya aktarımı, Logcat ve gelişmiş terminal |

## İndirme ve kurulum

1. [Son sürüm sayfasından](https://github.com/maventra-dev/MiBoxKonsol/releases/latest) `MiBoxKonsol-<sürüm>-win64-onedir.zip` dosyasını indirin.
2. ZIP dosyasının **tüm içeriğini** bir klasöre çıkarın.
3. Klasördeki `MiBoxKonsol.exe` dosyasını çalıştırın. EXE'yi ZIP içinden açmayın veya tek başına başka klasöre taşımayın.
4. TV'de **Geliştirici seçenekleri** ve **USB hata ayıklama** özelliğini açın. Bilgisayar ile TV aynı yerel ağdaysa uygulamadaki cihaz bulma veya kablosuz eşleştirme araçlarını kullanın.

Taşınabilir Windows paketi ADB 37.0.1'i ve gerekli Windows dosyalarını içerir; ayrıca ADB kurmanız gerekmez. ADB'nin lisans ve atıf bildirimi `platform-tools/NOTICE.txt` içindedir.

İndirmenin bütünlüğünü kontrol etmek için aynı release sayfasındaki `SHA256SUMS.txt` dosyasını kullanabilirsiniz (PowerShell: `Get-FileHash .\MiBoxKonsol-<sürüm>-win64-onedir.zip`). USB ile bağlanacaksanız TV'yi USB hata ayıklama açıkken bilgisayara bağlayıp TV ekranındaki izin isteğini onaylayın.

## Gereksinimler

- Windows 10 veya Windows 11, 64 bit (32 bit Windows için kaynaktan çalıştırma desteklenir, aşağıya bakın).
- TV'de ADB hata ayıklama izni. USB veya aynı yerel ağ üzerinden kablosuz bağlantı.
- Kaynaktan çalıştırma için Python 3.10 veya üzeri ve Android Platform Tools (`adb`).

## Kaynaktan çalıştırma

```powershell
git clone https://github.com/maventra-dev/MiBoxKonsol.git
cd MiBoxKonsol
python -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python mibox.py
```

Komut satırı seçeneklerini görmek için `python mibox.py --help` kullanın.

**32 bit (x86) Windows:** Qt 6 için 32 bit Windows paketi yayımlanmadığından uygulama bu sistemlerde otomatik olarak PyQt5 (Qt 5) uyumluluk katmanına geçer. 64 bit Windows üzerinde 32 bit Python kullanıyorsanız `requirements.txt` yerine doğrudan şu dosyayı kurun:

```powershell
python -m pip install -r requirements-x86.txt
```

32 bit EXE paketi `build_exe_x86.bat` ile oluşturulabilir.

## Gizlilik ve güvenli kullanım

- Cihaz yönetimi bilgisayarınız ile TV arasındaki ADB bağlantısı üzerinden yapılır. Uygulama telemetri veya reklam içermez.
- Ayarlar, işlem geçmişi, günlükler, APK yedekleri, terminal çıktıları ve ekran görüntüleri bilgisayarınızda tutulur. Dışa aktarılan geçmiş/yedekler ve tam tanılama raporu cihaz adresi, komut çıktısı veya yerel dosya yolu içerebilir; paylaşmadan önce gözden geçirin. **Ayarlar → Paylaşım özeti** kişisel yolları ve cihaz bilgilerini içermez.
- Katalog uygulamaları üçüncü taraflarca yayımlanır. Kurulum öncesinde yayıncıyı ve kaynağı kontrol edin; uygulama APK yayıncı imzasını veya SHA-256 özetini doğrulamaz.
- Katalog indirmeleri ve Scrcpy kurulumu için gerekli dosyalar, uygulama içindeki kaynak bağlantılarından internet üzerinden alınır.
- Paket kaldırma ve sistem ayarı değişiklikleri TV'nin işleyişini etkileyebilir. Ne yaptığınızı bilmediğiniz sistem paketlerini kaldırmayın; işlem öncesindeki açıklamaları ve onayları dikkatle okuyun.

## Katkı ve lisans

Hata bildirmek veya geliştirme önermek için [GitHub Issues](https://github.com/maventra-dev/MiBoxKonsol/issues) sayfasını kullanın. Katkı göndermeden önce [CONTRIBUTING.md](CONTRIBUTING.md) dosyasını inceleyin.

MiBox Konsol, [MIT Lisansı](LICENSE) ile yayımlanır.

<details>
<summary>English overview</summary>

MiBox Konsol is an open-source Windows desktop manager for **Xiaomi Mi Box**, **Mi TV Stick** and other **Android TV / Google TV** devices. It talks to your TV over **ADB** (USB or Wi-Fi) and puts the everyday and advanced tools in one window — no command line needed.

**Features**

- **Remote control:** D-pad, volume and media keys, send text and links to the TV, screenshots and interactive live screen.
- **Apps:** browse installed packages, launch, disable/enable or uninstall them (debloat), back up APKs.
- **Install:** Android TV app catalog, local APK and split APK installation.
- **Device health:** device summary, hardware readings, display configuration (resolution, DPI, overscan) and background permissions.
- **Network:** ADB device discovery, wireless pairing, Wi-Fi diagnostics and DNS settings.
- **Maintenance:** package profiles, state snapshots and restore, file transfer, Logcat and an advanced terminal.

**Quick start**

1. Download `MiBoxKonsol-<version>-win64-onedir.zip` (checksums in `SHA256SUMS.txt`) from [GitHub Releases](https://github.com/maventra-dev/MiBoxKonsol/releases/latest).
2. Extract the **whole** archive and run `MiBoxKonsol.exe`. The ZIP bundles ADB 37.0.1 with its license notices, so no separate ADB install is required.
3. On the TV, enable **Developer options** and **USB debugging**, then approve the connection prompt.

**Run from source** (Python 3.10+): `pip install -r requirements.txt` and `python mibox.py`. On 32-bit (x86) Windows the app automatically falls back to a PyQt5 compatibility layer; install it with `pip install -r requirements-x86.txt`.

**Privacy:** no telemetry or ads. Settings, logs, backups and screenshots stay on your computer; logs mask device addresses, IPs and local paths.

The UI is in Turkish. Bug reports and contributions are welcome via [GitHub Issues](https://github.com/maventra-dev/MiBoxKonsol/issues). Licensed under MIT.

</details>

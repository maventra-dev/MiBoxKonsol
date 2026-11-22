# Güvenlik Politikası (Security Policy)

MiBox Konsol güvenliği ciddiye alır. Cihazınızın sağlığını, kişisel verilerinizi ve ADB bağlantınızı korumak için komut onay filtreleri ve güvenlik mekanizmaları (`gate.py`, otomatik anlık yedekleme vb.) barındırır.

## Desteklenen Sürümler

Güvenlik düzeltmeleri yalnızca en güncel sürüm serisine yayımlanır. Eski bir sürüm kullanıyorsanız önce [son sürüme](https://github.com/maventra-dev/MiBoxKonsol/releases/latest) güncelleyin.

| Sürüm | Destekleniyor mu? |
| :--- | :--- |
| 1.5.x | :white_check_mark: Evet |
| < 1.5 | :x: Hayır |

## Güvenlik Açığı Bildirimi

Bu yazılımda bir güvenlik açığı tespit ederseniz:

1. Açığın ayrıntılarını herkese açık bir GitHub Issue'ya **yazmayın**.
2. [Güvenlik iletişimi formuyla](https://github.com/maventra-dev/MiBoxKonsol/issues/new?template=security_contact.yml) yalnızca etkilenen sürümü, genel alanı ve tahmini etkiyi belirten kısa bir talep açın.
3. Yönetici bu talebe, ayrıntıları özel olarak paylaşabileceğiniz bir kanalla yanıt verir. Yeniden oluşturma adımlarını ve olası etkiyi yalnızca o kanaldan gönderin. Cihaz IP adresi, hesap bilgisi veya kişisel dosya yolu paylaşmayın.

Kötüye kullanılamayan düşük etkili sorunlar (ör. yanlış uyarı metni) normal [hata formuyla](https://github.com/maventra-dev/MiBoxKonsol/issues/new?template=bug_report.yml) bildirilebilir.

Bildirilen açıklar en kısa sürede incelenir; doğrulanan sorunlar için düzeltme sürümü yayımlanır ve CHANGELOG'da belirtilir. Ayrıntılar ancak düzeltme yayımlandıktan sonra herkese açık paylaşılır.

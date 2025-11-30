# AKILLI ARAÇ İÇİ GÜVENLİK VE KONTROL SİSTEMİ SİMÜLASYONU

## 👥 Proje Sahipleri
* Ömer Faruk Toycu (@omertoycu)
* Ali Berke Erenler (@aliberkerenler)

---

## 🎯 Proje Amacı
Bu proje, **Arduino Mega 2560** mikrodenetleyici kartı kullanılarak **Proteus** simülasyon ortamında akıllı araç içi güvenlik ve konfor sistemlerinin simülasyonunu geliştirmeyi amaçlamaktadır. Sistem, güvenli bir sürüş deneyimi sağlamak ve sürücü konforunu artırmak için tasarlanmıştır.

## 🛠️ Teknolojiler ve Bileşenler
* **Mikrodenetleyici:** Arduino Mega 2560
* **Simülasyon Ortamı:** Proteus
* **Geliştirme Dili:** Arduino C/C++ (`.ino` dosyası)

| Sensörler (Giriş) | Çıkış Elemanları (Aktüatörler) |
| :--- | :--- |
| Motor Başlatma Butonu | 16x2 LCD Ekran (Durum ve Uyarılar) |
| Emniyet Kemeri Butonu | LED'ler (Kırmızı, Mavi, Sarı, Pembe) |
| LM35 Sıcaklık Sensörü | Buzzer (Güvenlik Uyarıları) |
| LDR Işık Sensörü | DC Motor (Araç motorunu simüle eder) |
| Potansiyometre (Yakıt Seviyesi) | DC Motor (Klima fanını simüle eder) |
| Kapı Durumu Anahtarı | |

---

## ✨ Temel Güvenlik ve Kontrol Mekanikleri
Sistem, aşağıdaki güvenlik ve konfor işlevlerini kontrol eder:

1.  **Motor Çalışma İzni (Güvenlik Önceliği):**
    * Motorun çalışması için hem **emniyet kemerinin takılı** hem de **kapının kapalı** olması zorunludur.
    * Kemer takılı değilse motor çalışmaz, Buzzer çalar ve Kırmızı LED yanar.
    * Kapı açık ise motor çalışmaz ve Pembe LED ile LCD uyarısı verilir.
2.  **Sıcaklık Bazlı Klima Kontrolü:**
    * Araç içi sıcaklık $25^\circ C$'nin üzerine çıktığında, klima fanı (DC Motor) otomatik olarak çalışır.
3.  **Ortam Işığına Göre Far Kontrolü:**
    * Ortam ışık seviyesi 250 lux'ın altına düştüğünde farlar (Mavi LED) otomatik olarak açılır.
4.  **Yakıt Seviyesi Uyarıları:**
    * Yakıt seviyesi %10'un altına düştüğünde Sarı LED yanar, %5'in altına düştüğünde Sarı LED yanıp sönmeye başlar.
    * Yakıt seviyesi **%0** olduğunda motor otomatik olarak durdurulur.

---

## 🚀 Çalıştırma Talimatları
1.  **Proteus** simülasyon yazılımını açın.
2.  Devre şemasını (Proteus dosyası) yükleyin.
3.  `Project Code.ino` dosyasını Arduino IDE'de açın, derleyin ve Proteus'a yükleyin.
4.  Simülasyonu başlatın ve düğmeler, potansiyometreler ve sensörler aracılığıyla sistemin tepkilerini gözlemleyin.

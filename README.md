# Halı Saha Kadro Kurucu (GitHub Pages + Firebase)

## Kurulum
1. Firebase konsolunda proje aç, Firestore Database oluştur.
2. Authentication > Sign-in method: **Google** ve **Anonymous** sağlayıcılarını aç.
3. Authentication > Settings > Authorized domains: `KULLANICIADIN.github.io` ekle.
4. Proje ayarlarından web uygulaması ekle, değerleri `config.js` içine yapıştır.
5. `firestore.rules` içindeki e-posta adresini kendi Gmail'inle değiştir, Firestore > Rules'a yapıştırıp yayınla.
6. Dosyaları (index.html, oy.html, config.js) bir GitHub reposuna yükle, Settings > Pages'ten yayınla.

## Kullanım
- **Sen:** `index.html` > "Yönetici girişi" (Google). Giriş yapınca veriler buluta yazılır.
- **Hafta içi:** Kadro kur, "Kadroyu yayınla (oylama)" ile maçı arkadaşlara aç.
- **Arkadaşlar:** `oy.html` linkini grupta paylaş. Kim olduğunu seçip maçın adamı oyunu ve (isterse) oyuncu puanlarını gönderir.
- **Maçtan sonra:** Sonuç formunda "Oyları çek (bulut)" ile oylar otomatik dolar, skoru ve golleri girip kaydet.
- **Puanlar:** "Arkadaş puanlarını içe aktar" her oyuncu için gelen puanların ortalamasını alır (oyuncunun kendine verdiği puanlar sayılmaz).

## Bilinen sınırlar
- Arkadaşlar anonim giriş kullandığı için biri başkası adına oy gönderebilir. Küçük bir arkadaş grubu için kabul edilebilir bir risk, ama sıkı doğrulama istenirse oyuncu başına PIN eklenebilir.
- Kurallar doküman ID'sini oyuncu kimliğine bağlar ve kendine oy vermeyi engeller; ama kimlik doğrulaması olmadığı için biri hâlâ başkası adına gönderebilir.
- Sonuç kaydedilince aktif maç otomatik kapanır, oy ekranı gizlenir.
- Sadece yönetici veriyi yazabilir ve oy/puanları okuyabilir.

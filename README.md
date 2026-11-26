# Web Music Player by SoftArchX

> API anahtarsız, sunucusuz, tek dosyalık YouTube müzik oynatıcı. GitHub Pages'te çalışır, verilerin yalnızca tarayıcında kalır.

**English:** A single-file, serverless YouTube music player. No API key, no backend, no tracking: playlists, settings and the on-device recommendation profile live only in your browser's `localStorage`. Turkish UI with a built-in English switch.

---

## Özellikler

**Oynatma**
- YouTube IFrame API ile (`youtube-nocookie.com`) oynatma; ileri/geri, karıştır, tekrar (kapalı / liste / tek), ses, hız, ileri-geri sarma
- **Akıllı karıştırma:** art arda aynı kanaldan parça gelmesini ve yakın zamanda çalınanların tekrarını azaltır
- Sıra (kuyruk), uyku zamanlayıcısı (özel süreli), kaldığın yerden devam, mini çubuk, tam ekran, medya tuşları (Media Session)
- Oynatılamayan videoları bulup listeden temizleme

**Arama ve içe aktarma (API anahtarı yok)**
- Arama; önce Piped, sonra Invidious JSON servisleri, olmazsa YouTube sayfasını CORS proxy üzerinden okuma
- Video veya oynatma listesi bağlantısı yapıştırınca otomatik tanıma (liste bağlantısında önce sorar)
- Aktif servislerin ve aramanın hangi kaynaktan geldiğinin görünür durumu, servis hız testi, düzenlenebilir servis listesi, arama geçmişi

**Listeler**
- Birden çok liste, sürükle-bırak sıralama, listeler arası taşıma/kopyalama, filtre
- Paylaşma bağlantısı ve **QR kod** (tarayıcıda üretilir, PNG olarak indirilebilir)
- JSON yedek (listeler + ayarlar), otomatik yedek önerisi

**Öneri (cihazda, veri toplamayan)**
- Dinlediğin sanatçı ve başlık kelimelerinden yerel bir zevk profili çıkarır; hiçbir yere gönderilmez
- Beğen / beğenme, "bunu / bu sanatçıyı önerme", keşif–tanıdık ayarı
- Aynı sanatçıyı üst üste dinleyince puan hızlanır; **otomatik güncelleme** (aç/kapa), **önerileri çal** (karıştırma açıksa akıllı karıştırılır)
- Arada bir **eski bir parçayı hatırlatma** (en sık 3 günde bir, kapatılabilir)

**Diğer**
- Türkçe / İngilizce dil düğmesi, açık/koyu/otomatik tema, depolama göstergesi, klavye kısayolları
- PWA: yüklenebilir, çevrimdışı kabuk. `manifest.webmanifest` ve `sw.js` olmasa bile site açılır

## Kurulum (GitHub Pages)

1. Bu dosyaları bir depoya, aynı klasöre koy:
   ```
   Web_Music_Player_by_SoftArchX.html
   website_icon.svg
   manifest.webmanifest
   sw.js
   icon-192.png
   icon-512.png
   icon-maskable-512.png
   ```
2. **Settings → Pages** bölümünden dalı ve klasörü seç.
3. `https://<kullanıcı>.github.io/<depo>/Web_Music_Player_by_SoftArchX.html` adresini aç. İstersen HTML dosyasını `index.html` olarak yeniden adlandır.

Derleme adımı, bağımlılık veya sunucu yok. Dosyayı çift tıklayarak yerelde de açabilirsin (PWA özellikleri hariç).

## Gizlilik

- **API anahtarı yok, hesap yok, analitik yok.** Uygulamada API anahtarı alanı bulunmaz.
- Listeler, ayarlar, arama geçmişi ve öneri profili yalnızca tarayıcının `localStorage` alanında durur; sunucuya gönderilmez ve depoya yazılmaz.
- Dışarı giden tek istekler: YouTube oynatıcısı, arama servisleri (Piped/Invidious, gerekirse CORS proxy) ve video bilgisi için oEmbed. Öneri için servislere yalnızca "sanatçı / kelime" araması gider; profilin kendisi gitmez.
- `localStorage` alanı `kullanıcı.github.io` adresi (origin) için paylaşılır: aynı kullanıcının başka GitHub Pages depolarındaki sayfalar da bu alanı okuyabilir ve alan sınırını paylaşır. Başka kişilerin siteleri etkilenmez. Düzenli yedek almanı öneririm.

## Bilinen sınırlamalar

- Arama, ücretsiz genel Piped/Invidious sunucularına bağlıdır; bunlar kapanabilir veya yavaşlayabilir. Servis listesini uygulamadan düzenleyebilirsin.
- Bazı videoların gömülmesi kapalıdır; bunlar oynatılamaz ve atlanır.
- Öneri, YouTube'un algoritması değildir: sanatçı ve anahtar kelime eşleşmesine dayalı, hafif ve yerel bir yöntemdir.
- Tarayıcı depolama sınırı genelde ~5 MB'tır; gösterge %80'de uyarır.
- Arama servisleri ve QR okuma gerçek cihazlarda otomatik testlerde taklit edilerek denenmiştir; kendi telefonunla bir kez denemeni öneririm.

## Klavye kısayolları

`N` sonraki · `P` önceki · `K` oynat/duraklat · `S` karıştır · `R` tekrar · `M` ses · `F` tam ekran · `←/→` 5 sn · `/` arama · `?` yardım

## Lisans

Lisansı depoya eklediğin `LICENSE` dosyası belirler (ör. MIT). Bu proje YouTube, Piped veya Invidious ile bağlantılı değildir; YouTube hizmet şartlarına uymak kullanıcının sorumluluğundadır.

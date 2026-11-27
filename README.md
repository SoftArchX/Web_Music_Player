<div align="center">

# 🎵 Web Music Player by SoftArchX

**A serverless, single-file YouTube music player. No API key, no backend, no tracking.**<br>
**API anahtarsız, sunucusuz, tek dosyalık YouTube müzik oynatıcı.**

[English](#english) · [Türkçe](#türkçe)

</div>

---

<a id="english"></a>

## English

Web Music Player is a YouTube player that runs entirely in your browser, with no server and no API key.

### Features

**Playback**
- Plays through the official YouTube IFrame API (`youtube-nocookie.com`): previous/next, shuffle, repeat (off / list / one), volume, speed, seeking
- **Smart shuffle:** avoids back-to-back tracks from the same channel and recently played ones
- Queue, sleep timer (custom durations), resume where you left off, mini bar, fullscreen, media keys (Media Session)
- Find and remove unplayable videos
- **Undo / redo** (`Ctrl+Z`, `Ctrl+Y`) for removing, moving, reordering, deleting lists, clearing the queue and imports (last 30 actions)

**Search and import, with no API key**
- Search goes through public Piped, then Invidious JSON services, and falls back to reading YouTube pages through a CORS proxy
- Paste a video or playlist link and it is recognized automatically (it asks before adding a whole playlist)
- Visible status of every search service and which one answered, a speed check, an editable service list and search history

**Playlists**
- Multiple lists, drag-and-drop ordering, move/copy between lists, filter
- Share by link or **QR code** (generated in the browser, downloadable as PNG)
- JSON backup (lists and settings) plus automatic backup suggestions

**On-device recommendations (no data collection)**
- Builds a small taste profile from the artists and title words you actually listen to; it never leaves your device
- Like / dislike, "don't recommend this / this artist", a discover-vs-familiar slider
- Listening to the same artist repeatedly raises its score faster; **auto-update**, **play recommendations** (smart-shuffled when shuffle is on) and **radio mode** (keeps playing recommendations when the list and queue end)
- Searches count as a weak signal (each search once; ignored while learning is off)
- Occasional **reminder of an old favorite** (at most every 3 days, can be turned off)

**Smart lists** (built from on-device listening history only): *Most played*, *Last 30 days*, *Never played*, *This time last year*. Play them all or save them as a real list. History is kept only while learning is on and covers the last 2500 plays longer than 30 s.

**Other**
- Turkish / English switch, light / dark / auto theme, storage usage meter, keyboard shortcuts
- PWA: installable with an offline shell. The site still opens if `manifest.webmanifest` or `sw.js` are missing

### Privacy

- **No API key, no account, no analytics.** There is no API key field in the app.
- Your lists, settings and listening data stay on your device. They are never sent to a server.
- The only outgoing requests are: the YouTube player, the search services (Piped / Invidious, and a CORS proxy as a fallback) and oEmbed for video titles. For recommendations only artist / keyword searches are sent, never the profile.

### Limitations

- Search depends on free public Piped / Invidious servers, which can go down or slow down. You can edit the service list in the app.
- Some videos cannot be embedded; they are marked and skipped.
- Recommendations are not YouTube's algorithm: they use artist and keyword matching, lightweight and local.
- Automated tests mock the search services, the YouTube player and QR scanning. Try it once on your own phone.

### Keyboard shortcuts

`Ctrl+Z` undo · `Ctrl+Y` redo · `N` next · `P` previous · `K` play/pause · `S` shuffle · `R` repeat · `M` mute · `F` fullscreen · `←/→` 5 s · `/` search · `?` help

### License and disclaimer

Licensed under the terms in the [LICENSE](LICENSE) file. This project is not affiliated with YouTube, Piped or Invidious. Following YouTube's Terms of Service is the user's responsibility.

---

<a id="türkçe"></a>

## Türkçe

Web Music Player, sunucusu ve API anahtarı olmadan tamamen tarayıcında çalışan bir YouTube oynatıcısıdır.

### Özellikler

**Oynatma**
- Resmî YouTube IFrame API ile (`youtube-nocookie.com`) oynatma: önceki/sonraki, karıştır, tekrar (kapalı / liste / tek), ses, hız, sarma
- **Akıllı karıştırma:** art arda aynı kanaldan parça gelmesini ve yakın zamanda çalınanların tekrarını azaltır
- Sıra (kuyruk), uyku zamanlayıcısı (özel süreli), kaldığın yerden devam, mini çubuk, tam ekran, medya tuşları (Media Session)
- Oynatılamayan videoları bulup listeden temizleme
- **Geri al / yinele** (`Ctrl+Z`, `Ctrl+Y`): silme, taşıma, sıralama, liste silme, sıra temizleme ve içe aktarma (son 30 işlem)

**Arama ve içe aktarma (API anahtarı yok)**
- Arama önce herkese açık Piped, sonra Invidious JSON servislerinden yapılır; olmazsa YouTube sayfası CORS proxy üzerinden okunur
- Video veya oynatma listesi bağlantısı yapıştırınca otomatik tanınır (tüm listeyi eklemeden önce sorar)
- Servislerin ve cevap veren kaynağın görünür durumu, hız testi, düzenlenebilir servis listesi ve arama geçmişi

**Listeler**
- Birden çok liste, sürükle-bırak sıralama, listeler arası taşıma/kopyalama, filtre
- Bağlantı veya **QR kod** ile paylaşım (tarayıcıda üretilir, PNG olarak indirilir)
- JSON yedek (listeler ve ayarlar) ve otomatik yedek önerisi

**Cihazda öneri (veri toplamadan)**
- Gerçekten dinlediğin sanatçı ve başlık kelimelerinden küçük bir zevk profili çıkarır; cihazından çıkmaz
- Beğen / beğenme, "bunu / bu sanatçıyı önerme", keşif–tanıdık ayarı
- Aynı sanatçıyı üst üste dinleyince puanı daha hızlı artar; **otomatik güncelleme**, **önerileri çal** (karıştırma açıksa akıllı karıştırılır) ve **radyo modu** (liste ve sıra bitince öneriyle devam eder)
- Aramalar zayıf bir sinyal sayılır (her arama bir kez; Öğrenme kapalıyken sayılmaz)
- Arada bir **eski bir favoriyi hatırlatma** (en sık 3 günde bir, kapatılabilir)

**Akıllı listeler** (yalnızca cihazdaki dinleme geçmişinden): *En çok dinlenen*, *Son 30 gün*, *Hiç dinlenmemiş*, *Geçen yıl bu günler*. Hepsini çalabilir veya gerçek bir liste olarak kaydedebilirsin. Geçmiş yalnızca Öğrenme açıkken tutulur ve 30 sn'den uzun dinlenen son 2500 parçayı kapsar.

**Diğer**
- Türkçe / İngilizce düğmesi, açık/koyu/otomatik tema, depolama göstergesi, klavye kısayolları
- PWA: yüklenebilir, çevrimdışı kabuk. `manifest.webmanifest` veya `sw.js` olmasa da site açılır

### Gizlilik

- **API anahtarı yok, hesap yok, analitik yok.** Uygulamada API anahtarı alanı bulunmaz.
- Listelerin, ayarların ve dinleme verilerin cihazında kalır; hiçbir sunucuya gönderilmez.
- Dışarı giden tek istekler: YouTube oynatıcısı, arama servisleri (Piped / Invidious, yedek olarak CORS proxy) ve video başlıkları için oEmbed. Öneri için yalnızca sanatçı / kelime araması gider, profilin kendisi gitmez.

### Sınırlamalar

- Arama, ücretsiz genel Piped / Invidious sunucularına bağlıdır; bunlar kapanabilir veya yavaşlayabilir. Servis listesini uygulamadan düzenleyebilirsin.
- Bazı videoların gömülmesi kapalıdır; işaretlenir ve atlanır.
- Öneri, YouTube'un algoritması değildir: sanatçı ve anahtar kelime eşleşmesine dayalı, hafif ve yerel bir yöntemdir.
- Otomatik testlerde arama servisleri, YouTube oynatıcısı ve QR okuma taklit edilmiştir. Kendi telefonunla bir kez dene.

### Klavye kısayolları

`Ctrl+Z` geri al · `Ctrl+Y` yinele · `N` sonraki · `P` önceki · `K` oynat/duraklat · `S` karıştır · `R` tekrar · `M` ses · `F` tam ekran · `←/→` 5 sn · `/` arama · `?` yardım

### Lisans ve sorumluluk reddi

Lisans koşulları [LICENSE](LICENSE) dosyasındadır. Bu proje YouTube, Piped veya Invidious ile bağlantılı değildir. YouTube Hizmet Şartları'na uymak kullanıcının sorumluluğundadır.

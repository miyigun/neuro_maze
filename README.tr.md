[🇹🇷 Türkçe için buraya tıklayın](README.tr.md)

# NEURO-MAZE: Mantık Çekirdeği

Siberpunk temalı, tarayıcı tabanlı 3D boru yönlendirme bulmaca oyunu. Three.js 3D motoru, neon görseller ve akıcı animasyonlar içeren tek sayfalık bir HTML uygulaması olarak geliştirilmiştir.

---

## Özellikler

### 1. 3D Oyun Tahtası
- **Three.js** ile render edilen **6×6×6** üç boyutlu grid
- **OrbitControls** ile serbest döndürülebilen kamera (sürükle, yakınlaştır, kaydır)
- Emissive glow efektli neon renkli blok mesh’leri
- Yerleştirme sırasında görünen hayalet önizleme blok

### 2. Blok Türleri
| Blok | Renk | Açıklama |
|---|---|---|
| **STRAIGHT** (Düz Boru) | 🔵 Neon Mavi | Sinyali düz geçirir; dikey, yatay-X ve yatay-Z yönlerini destekler |
| **CORNER** (Dik Açı Dirsek) | 🟣 Neon Mor | Sinyali 90° yönlendirir; 8 farklı rotasyon (4 × flip) destekler |
| **TURNER** (Yatay Dirsek) | 🟢 Neon Yeşil | Sadece yatay düzlemde çalışır; sinyali sağa veya sola büker; 4 rotasyon |
| **OMNI** (Omni Merkez) | 🟡 Neon Altın | Sinyali her yönde düz geçirir; evrensel köprü görevi görür |

### 3. Sinyal Simülasyonu
- **Sinyal topu**, başlangıç işaretinden (camgöbeği tel kafes koni) kırmızı bitiş noktasına doğru hareket eder
- Top, yerleştirilen bloklardan hücre hücre ilerler
- Grid dışına çıkarsa **SIGNAL LOSS**, blok yönlendiremezse **WRONG ROUTE** hatası oluşur
- Simülasyon başlamadan önce **tüm envanter blokları yerleştirilmiş olmalıdır**

### 4. Deneme Sistemi & SOLUTION Butonu
- Her seviye **3 deneme** ile başlar
- **🔒 SOLUTION** butonu tüm denemeler bittikten sonra açılır
- SOLUTION’a tıklanınca doğru çözüm animasyonlu şekilde gösterilir
- Deneme sayısı **∞** olur ve RUN butonu **▶ WATCH** moduna geçer

### 5. Kontrol Paneli
- **✖ DELETE** — yerleştirilen blok silinir ve envantere döner
- **Envanter butonları** — yerleştirilecek blok seçilir; kalan miktar gösterilir
- **⟳ ROTATE** — seçili bloğun rotasyonunu değiştirir
- **▶ START** — simülasyonu başlatır (tüm bloklar yerleştirildiyse aktif)
- **🔒 SOLUTION** — çözümü gösterir (denemeler bitince açılır)

### 6. 10 Aşamalı Seviye
| Seviye | Ad | Açıklama |
|---|---|---|
| 1 | Basic Pass | Sinyali aşağı ve sağa yönlendir |
| 2 | Horizontal Turn | Yeşil TURNER blokları sadece yatayda çalışır |
| 3 | Magic Hub | OMNI bloklar sinyali düz geçirir |
| 4 | Height Difference | Alt katlara inmek için köşe blokları akıllıca kullan |
| 5 | Spiral Ramp | Dikey ve yatay keskin manevralar |
| 6 | Locked Point | Ortadaki sabit gri bloklardan geçmek zorundasın |
| 7 | Zigzag Route | Zeminde zikzak şeklinde ilerle |
| 8 | Staircase System | Sadece köşe bloklarla kat kat aşağı in |
| 9 | U-Turn | Geldiğin yola paralel geri dön |
| 10 | FINAL | Tüm öğrendiklerini büyük bir köprüde birleştir |

### 7. Blok Eğitim Penceresi
- Başlangıçta etkileşimli **3D blok görüntüleyici** açılır
- ◀ / ▶ ile bloklar arasında geçiş yapılır; bloklar otomatik döner
- Blok adı, rengi ve açıklaması gösterilir
- Sağ üstteki **?** butonuyla tekrar açılabilir

### 8. Bilgi Paneli
- **STATUS** — READY / SIMULATION… / SIGNAL LOSS / WRONG ROUTE
- **ATTEMPTS** — kalan deneme sayısı (veya çözüm modunda ∞)
- **MISSION** — mevcut seviyeye ait ipucu

### 9. Seviye Atlama
- Üst kısımdaki açılır menü ile istenilen seviyeye geçilebilir

### 10. Ses Efektleri
- **Web Audio API** ile oluşturulmuş prosedürel sesler
- Yerleştirme, döndürme, kazanma, hata, hareket ve başlatma için farklı sesler

### 11. Arka Plan Müziği
- Oyun başladığında `suspence-music-1-8160.mp3` düşük sesle çalar
- Otomatik başlar; tarayıcı etkileşim isteyebilir

### 12. Siberpunk Görsel Tema
- Koyu arka plan (`#050505`) ve sahne sisi efekti
- Neon mavi (`#00f3ff`), mor (`#bc13fe`), yeşil (`#00ff41`), altın (`#ffd700`)
- `backdrop-filter: blur` ile cam efekti panel
- **Tween.js** ile elastik/bounce animasyonlar
- Google Fonts **Exo 2** yazı tipi

### 13. Kazanma & Final Ekranları
- Seviye tamamlanınca **SUCCESSFUL** penceresi
- Tüm seviyeler bitince **NEURO-MASTER** tam ekran efekti

---

## Proje Yapısı
neuro_maze/ 
    ├── index.html — tam uygulama (HTML/CSS/JS tek dosyada) 
    └── suspence-music-1-8160.mp3 — arka plan müziği

---

## Başlangıç

    1. Repoyu klonlayın:
    ```bash
    git clone https://github.com/miyigun/neuro_maze.git

    2. Proje klasörüne girin:
        cd neuro_maze

    3. index.html dosyasını tarayıcıda açın — ek kurulum gerekmez.

## Nasıl Oynanır

    1. Eğitim penceresinden blokları inceleyin ve START SYSTEM'e tıklayın.
    2. Alt panelden blok türünü seçin.
    3. 3D grid üzerinde önizlemeyi görün ve tıklayarak yerleştirin.
    4. Yerleştirmeden önce ⟳ ROTATE ile yönünü değiştirin.
    5. ✖ DELETE ile yanlış bloğu kaldırabilirsiniz.
    6. Tüm blokları yerleştirdikten sonra ▶ START ile simülasyonu başlatın.
    7. Sinyal topunun borudan geçişini izleyin — kırmızı hedefe ulaşınca kazanırsınız!
    8. Denemeler biterse 🔒 SOLUTION çözümü gösterir.

🛠️ Kullanılan Teknolojiler

    - HTML5 / CSS3 / Vanilla JavaScript
    - Three.js r128 — 3D motor
    - OrbitControls — kamera kontrolü
    - Tween.js 18.6.4 — animasyon
    - Google Fonts — Exo 2
    - Web Audio API — ses efektleri

📌 Notlar

    - Kurulum gerekmez — sadece index.html açılır.
    - Tüm sistem tek dosyada çalışır.
    - Müzik için tarayıcı etkileşimi gerekebilir.
    - Kamera serbesttir: döndür, zoom, kaydır.
    - Sabit gri bloklar (seviye 6) taşınamaz.

📜 Lisans

    Bu proje MIT Lisansı ile lisanslanmıştır. Detaylar için LICENSE dosyasına bakınız.
# 🚀 Veri Temizliği Reposu — Kurulum Rehberi

Bu rehber, sana hazırladığım Quarto sitesini GitHub'a yüklemen ve canlıya almanın yollarını anlatıyor.

---

## 📦 Hazırlanan Dosyalar

```
veri-temizligi/
├── README.md                        ← GitHub repo açıklaması
├── _quarto.yml                      ← Site yapılandırma
├── styles.css                       ← Tema CSS
├── index.qmd                        ← Ana sayfa
├── rehber/
│   ├── 01-veri-toplama-disiplini.qmd
│   ├── 02-sik-sorunlar.qmd
│   ├── 03-openrefine-rehberi.qmd
│   ├── 04-r-temizlik.qmd
│   └── 05-kontrol-listesi.qmd
└── .github/workflows/
    └── publish.yml                  ← Otomatik deploy
```

**Toplam: 9 dosya, ~50 sayfa içerik.**

---

## ⚡ Hızlı Kurulum (En Pratik Yol)

GitHub web arayüzünden, komut satırına dokunmadan kuracağız.

### 1️⃣ Yeni repo oluştur

1. GitHub → sağ üst **+** → **New repository**
2. Repository name: **`veri-temizligi`**
3. **Public** seç
4. ✅ **"Add a README file"** işaretle
5. License: **Creative Commons Attribution 4.0**
6. **Create repository**

### 2️⃣ README'yi güncelle

1. Otomatik açılan `README.md`'ye tıkla → ✏️ kalem ikonu
2. İçindekileri sil
3. Sana verdiğim **`README.md`** içeriğini yapıştır
4. **Commit changes**

### 3️⃣ Diğer dosyaları yükle

GitHub web arayüzünde **birden fazla dosyayı sürükle-bırak** ile yükleyebilirsin.

1. Repo ana sayfasında **"Add file"** → **"Upload files"**
2. Bilgisayarındaki `veri-temizligi/` klasöründen şu dosyaları sırayla sürükle-bırak (veya hepsini birlikte seç):
   - `_quarto.yml`
   - `styles.css`
   - `index.qmd`
3. En aşağıda commit mesajı: `Quarto site files`
4. **Commit changes**

### 4️⃣ Rehber klasörünü oluştur

GitHub'da klasör doğrudan oluşturulamaz; **dosya yoluyla otomatik oluşur**.

1. **Add file** → **Create new file**
2. Dosya adı: `rehber/01-veri-toplama-disiplini.qmd`
3. Bilgisayarındaki dosyanın içeriğini kopyala-yapıştır
4. **Commit changes**

**`rehber/02-sik-sorunlar.qmd`**, **`rehber/03-...`**, **`rehber/04-...`**, **`rehber/05-...`** için aynı işlemi tekrarla.

> 💡 İlk dosyada `rehber/` klasörü otomatik oluşur, sonrakiler için aynı isim kalıbını kullan.

### 5️⃣ GitHub Action workflow'unu ekle

1. **Add file** → **Create new file**
2. Dosya adı: `.github/workflows/publish.yml`
3. `publish.yml` içeriğini yapıştır
4. **Commit changes**

---

## 🌐 GitHub Pages'i Aktifleştir

Workflow ilk kez çalıştığında `gh-pages` adında bir branch oluşturur. Sitenin yayınlanması için Pages ayarını yapmalısın.

### Adım 1: Action'ın çalışmasını bekle

1. **Actions** sekmesi → **"Publish Quarto site"** workflow'unu göreceksin
2. İlk push'tan sonra otomatik tetiklenir, ~1-2 dakika sürer
3. Yeşil ✅ olmasını bekle

### Adım 2: Pages ayarı

1. Repo → **Settings** → sol menüden **Pages**
2. **Source** kısmında: **Deploy from a branch**
3. **Branch**: `gh-pages` seç (workflow oluşturmuş olmalı)
4. **Folder**: `/ (root)`
5. **Save**

### Adım 3: Yayını doğrula

Birkaç dakika sonra şu adres aktif olur:

**`https://drmuammer.github.io/veri-temizligi/`**

---

## 🔧 Yerel Geliştirme (Opsiyonel)

İçeriği güncellemek istersen, lokal olarak çalışman daha rahat olur.

### Quarto Kurulumu

**Windows:**
1. <https://quarto.org/docs/get-started/> sayfasına git
2. **Windows installer** indir
3. Kur (varsayılan ayarlar)

**Mac:**
```bash
brew install --cask quarto
```

### Geliştirme Akışı

```bash
# Repoyu klonla
git clone https://github.com/drmuammer/veri-temizligi.git
cd veri-temizligi

# Canlı önizleme (her değişiklik anında render olur)
quarto preview
```

Tarayıcıda otomatik olarak `http://localhost:4848` açılır. Bir `.qmd` dosyasını düzenleyip kaydettiğinde sayfa otomatik yenilenir.

```bash
# Statik HTML üret (test için)
quarto render

# Değişiklikleri GitHub'a gönder
git add .
git commit -m "İçerik güncellendi"
git push
```

Push'tan sonra GitHub Action otomatik çalışır ve siteyi günceller. ~2 dakika içinde değişiklik canlıda olur.

---

## 🎨 Tema/Renk Değiştirme

Renk paleti `styles.css` dosyasının başında CSS değişkenleri olarak tanımlı:

```css
:root {
  --primary: #14B8A6;        ← ana teal renk
  --primary-dark: #0F766E;
  --primary-light: #5EEAD4;
  --accent: #06B6D4;
  --navy: #0F172A;           ← koyu navy
  --navy-light: #1E293B;
}
```

Bu altı değişkeni değiştirip git push yaparsan tüm site teması güncellenir.

### Alternatif Paletler

| Tema | Primary | Navy |
|------|---------|------|
| **Bordo** | `#9F1239` | `#1F2937` |
| **Yeşil** | `#10B981` | `#064E3B` |
| **Mor** | `#7C3AED` | `#1E1B4B` |
| **Turuncu** | `#EA580C` | `#1C1917` |

### Quarto Tema Değiştirme

`_quarto.yml` içinde:

```yaml
format:
  html:
    theme:
      light: cosmo       # cosmo, flatly, journal, lumen, sandstone...
      dark: darkly       # darkly, slate, solar, vapor, cyborg...
```

Tüm temalar: <https://quarto.org/docs/output-formats/html-themes.html>

---

## ✅ Kontrol Listesi

İlk yüklemeden sonra:

- [ ] `github.com/drmuammer/veri-temizligi` reposu açıldı
- [ ] Tüm dosyalar yüklendi (9 dosya)
- [ ] Actions sekmesinde workflow yeşil ✅
- [ ] `gh-pages` branch'i oluştu
- [ ] Settings → Pages → branch `gh-pages` seçili
- [ ] **`drmuammer.github.io/veri-temizligi/`** adresinde site açılıyor
- [ ] Sidebar'da 5 bölüm görünüyor
- [ ] Mobilde test edildi
- [ ] Profil README'sine bağlantı eklendi

---

## 🧩 Profil README'ne Ekle

Bu site canlıya alındıktan sonra, profil README'ndeki **Notlar & Rehberler** tablosuna yeni satır ekleyelim:

```html
<tr>
<td><b><a href="https://drmuammer.github.io/veri-temizligi/">Veri Temizliği Rehberi</a></b></td>
<td>✅</td><td>—</td>
<td>Klinik araştırmacılar için Excel/CSV temizliği · Data cleaning guide</td>
</tr>
```

Bu satırı `Zotero Rehberi` satırının hemen altına ekleyebilirsin.

---

## 🐛 Sorun Giderme

**"Quarto: command not found" (yerel kurulumda):**
- Quarto kuruldu ama PATH'e eklenmedi → bilgisayarı yeniden başlat

**Action başarısız (kırmızı ❌):**
- Actions sekmesinden hatayı oku
- En yaygın sebep: workflow permission eksik
- Settings → Actions → General → Workflow permissions → "Read and write" seç → Save

**Site açılıyor ama Türkçe karakterler bozuk:**
- `_quarto.yml` içinde `lang: tr` satırı var mı kontrol et
- Tarayıcıda hard refresh: Ctrl+Shift+R

**Sidebar gözükmüyor:**
- `_quarto.yml`'deki sidebar yolu doğru yazıldı mı kontrol et
- `rehber/` klasörü oluşmuş mu (case-sensitive)

**Profil README'sindeki link çalışmıyor:**
- GitHub Pages aktivasyonu 5-10 dakika sürebilir
- 404 alıyorsan: settings → Pages → branch ayarını doğrula

---

## 🎯 Sonraki Adımlar

Site canlıya alındıktan sonra eklenebilecekler:

1. **Şablon (sablon/temizlik-sablonu.qmd)** — drop-in R/Quarto şablonu
2. **Örnek kirli veri (sablon/ornek-veri.xlsx)** — pratik için
3. **Ekran görüntüleri** — OpenRefine bölümüne gerçek screenshot'lar
4. **Video walkthrough** — YouTube embed
5. **İngilizce sürüm** — `en/` klasörü altında
6. **Citation desteği** — `quarto-cli` ile Zotero entegrasyonu

Bunları sırayla yapmak için zamanın olduğunda söyle, her birini ayrı ayrı ele alalım.

---

İyi içerikler! 🎯

<div align="center">

# 🧹 Veri Temizliği Rehberi

### *Klinik araştırmacılar için pratik veri temizliği rehberi*

[![Site](https://img.shields.io/badge/Site-drmuammer.github.io%2Fveri--temizligi-14B8A6?style=for-the-badge)](https://drmuammer.github.io/veri-temizligi/)
[![License](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg?style=flat-square)](https://creativecommons.org/licenses/by/4.0/)
![Status](https://img.shields.io/badge/Status-Aktif-success?style=flat-square)
![Lang](https://img.shields.io/badge/Dil-Türkçe-red?style=flat-square)

</div>

---

## Bu Rehber Ne İşe Yarar?

Bir biyoistatistikçiye ya da metodoloji danışmanına başvurmadan önce **kendi verisini hazırlamak isteyen** klinik araştırmacılar için yazıldı.

İçerik:

1. **Veri Toplama Disiplini** — daha veri toplamadan doğru başlamak için
2. **Sık Karşılaşılan Sorunlar** — Excel verilerinde gördüğüm en yaygın 10 problem
3. **OpenRefine Rehberi** — kod yazmadan, ücretsiz ve güçlü bir araç
4. **R ile Temizlik** — otomatik kontrol raporu üreten yaklaşım
5. **Kontrol Listesi** — istatistikçinize göndermeden önce 42 maddelik test

## 🌐 Online Olarak Okuma

Rehberin online sürümü: **<https://drmuammer.github.io/veri-temizligi/>**

(GitHub Pages aktif olduğunda yayınlanacak.)

## 💻 Yerel Olarak Çalıştırma

Bu repoyu kendi bilgisayarınızda render etmek isterseniz:

### Önkoşul

[Quarto](https://quarto.org/docs/get-started/) kurulu olmalı.

### Adımlar

```bash
git clone https://github.com/drmuammer/veri-temizligi.git
cd veri-temizligi
quarto preview    # canlı önizleme (localhost:4848 açar)
quarto render     # statik HTML üretir → _site/ klasörüne
```

## 📂 Klasör Yapısı

```
veri-temizligi/
├── _quarto.yml                 ← Site yapılandırma
├── index.qmd                   ← Ana sayfa
├── styles.css                  ← Tema CSS
├── rehber/
│   ├── 01-veri-toplama-disiplini.qmd
│   ├── 02-sik-sorunlar.qmd
│   ├── 03-openrefine-rehberi.qmd
│   ├── 04-r-temizlik.qmd
│   └── 05-kontrol-listesi.qmd
└── .github/workflows/
    └── publish.yml             ← Otomatik GitHub Pages deploy
```

## 🤝 Katkı

Hata, eksik ya da öneriniz varsa:

- [**Issue**](https://github.com/drmuammer/veri-temizligi/issues) açın
- [**Pull Request**](https://github.com/drmuammer/veri-temizligi/pulls) gönderin

Türkçe terminoloji önerileri özellikle değerli.

## 📜 Lisans

Tüm içerik [**CC BY 4.0**](https://creativecommons.org/licenses/by/4.0/) altında paylaşılmaktadır. Kaynağı belirterek özgürce kullanabilir, dağıtabilir ve uyarlayabilirsiniz.

## 📫 İletişim

🌐 [muammerbeslen.com](https://muammerbeslen.com)  
📚 [Diğer notlar](https://github.com/drmuammer/notes)

---

<div align="center">

*"Hatalı veri, hatalı sonuç. Garbage in, garbage out."*

</div>

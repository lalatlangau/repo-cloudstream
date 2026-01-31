# 🎬 Cloudstream Plugin Generator Suite

**Generator otomatis untuk membuat plugin Cloudstream** dengan support multiple website dan template.

## 📦 Apa yang Ada di Package Ini?

### 🔧 Tools Utama

1. **advanced_cloudstream_generator.py** ⭐
   - Generator utama dengan fitur lengkap
   - Support 3 template berbeda
   - Interactive mode & batch mode
   - Auto-detect plugin name dari domain

2. **generate_cloudstream.py**
   - Generator versi simple (untuk DutaMovie)
   - Cocok untuk pemula

3. **batch_config.json**
   - Template konfigurasi untuk batch mode
   - Contoh: generate 4 plugin sekaligus

### 📚 Dokumentasi

- **QUICKSTART.md** - Panduan cepat step-by-step
- **DOCUMENTATION.md** - Dokumentasi lengkap dengan troubleshooting
- **README.md** (file ini) - Overview package

### 🎯 Plugin yang Sudah Di-Generate (Contoh)

1. **cloudstream-dutamovie/** - DutaMovie (hidekielectronics.com)
2. **cloudstream-lk21/** - LK21 (lk21official.net)
3. **cloudstream-rebahin/** - Rebahin (rebahinz.com)
4. **cloudstream-filmapik/** - FilmApik (filmapik.wiki)

---

## 🚀 Quick Start

### Cara Tercepat (3 Langkah)

```bash
# 1. Generate plugin untuk website Anda
python3 advanced_cloudstream_generator.py

# Masukkan:
# - Domain: https://namawebsite.com
# - Plugin Name: (enter untuk auto)
# - Template: pilih 1-3

# 2. Upload ke GitHub
cd cloudstream-namaPlugin
git init
git add .
git commit -m "Init"
git remote add origin https://github.com/USERNAME/repo.git
git push -u origin master

# 3. Add di Cloudstream App
# Settings → Extensions → Add Repository
# Paste URL repo.json Anda
```

**Baca QUICKSTART.md untuk tutorial lengkap!**

---

## 🎨 Template yang Tersedia

| Template | Cocok Untuk | Contoh Website |
|----------|-------------|----------------|
| **wordpress_movie** | WordPress-based movie sites | DutaMovie, Rebahin, IndoXXI |
| **lk21_clone** | LK21 and clones | LK21, LayarKaca21, Nonton |
| **custom_streaming** | Custom streaming sites | FilmApik, BioskopKeren |

### Cara Pilih Template?

1. **Lihat source code website** (Ctrl+U di browser)
2. Cari keyword:
   - Ada `wp-content` → wordpress_movie
   - Ada `lk21` atau `layarkaca` → lk21_clone
   - Lainnya → custom_streaming

---

## 📖 Mode Penggunaan

### 1. Interactive Mode (Paling Mudah)

```bash
python3 advanced_cloudstream_generator.py
```

Program akan tanya satu per satu:
- Domain apa?
- Nama plugin?
- Template mana?

### 2. Command Line Mode

```bash
# Basic
python3 advanced_cloudstream_generator.py https://example.com

# Dengan custom name
python3 advanced_cloudstream_generator.py https://example.com MyPlugin

# Dengan custom template
python3 advanced_cloudstream_generator.py https://example.com MyPlugin lk21_clone
```

### 3. Batch Mode (Generate Banyak)

```bash
# Edit batch_config.json dulu
python3 advanced_cloudstream_generator.py --batch batch_config.json
```

---

## 🎯 Fitur Unggulan

✅ **Auto-Generate Everything**
- Plugin code (.kt)
- Build files (.gradle)
- GitHub Actions (auto-build)
- Documentation (README)

✅ **Multiple Templates**
- WordPress Movie Theme
- LK21 Clone
- Custom Streaming

✅ **Smart Detection**
- Auto plugin name dari domain
- Intelligent selector mapping
- Debug config generation

✅ **Production Ready**
- GitHub Actions integration
- Auto-build on push
- Repository manifest

---

## 📁 Struktur Output

Setiap plugin yang di-generate:

```
cloudstream-namaPlugin/
├── 📄 NamaPlugin.kt          ← Main plugin code
├── 📄 build.gradle.kts       ← Build config
├── 📄 settings.gradle.kts    ← Gradle settings
├── 📄 repo.json              ← Repository manifest
├── 📄 config.json            ← Debug info (selectors, dll)
├── 📄 README.md              ← Documentation
└── 📁 .github/
    └── workflows/
        └── build.yml         ← Auto-build GitHub Actions
```

---

## 🔧 Customization

### Tambah Template Baru

Edit `advanced_cloudstream_generator.py`:

```python
WEBSITE_TEMPLATES = {
    "template_baru": {
        "name": "Nama Template",
        "selectors": {
            "movie_list": "div.film",
            "title": "h2 a",
            # ... dst
        },
        "pages": {
            "search": "/cari/",
            # ... dst
        }
    }
}
```

### Edit Selector

Lihat file `config.json` yang di-generate untuk debug selector.

---

## 🐛 Troubleshooting

### Plugin tidak menampilkan film?
→ Cek selector `movie_list` di `config.json`

### Search tidak jalan?
→ Test URL search manual di browser dulu

### Video tidak bisa play?
→ Cek selector `iframe` dan `download_links`

**Lihat DOCUMENTATION.md untuk troubleshooting lengkap!**

---

## 📊 Comparison: Simple vs Advanced

| Feature | generate_cloudstream.py | advanced_cloudstream_generator.py |
|---------|------------------------|-----------------------------------|
| Templates | 1 (WordPress) | 3 (WordPress, LK21, Custom) |
| Interactive Mode | ❌ | ✅ |
| Batch Mode | ❌ | ✅ |
| Auto Plugin Name | ❌ | ✅ |
| Debug Config | ❌ | ✅ (config.json) |
| Cocok untuk | DutaMovie only | Any streaming site |

**Rekomendasi: Gunakan advanced_cloudstream_generator.py**

---

## 🎓 Learning Path

### Pemula
1. ✅ Baca QUICKSTART.md
2. ✅ Generate 1 plugin dengan interactive mode
3. ✅ Upload ke GitHub
4. ✅ Test di Cloudstream

### Intermediate
1. ✅ Generate dengan command line mode
2. ✅ Edit selector di file .kt
3. ✅ Customization template

### Advanced
1. ✅ Batch generate multiple plugins
2. ✅ Buat template baru
3. ✅ Contribute template ke community

---

## 📝 Checklist

Sebelum upload ke GitHub:

- [ ] Generate plugin dengan script
- [ ] Review file `.kt` (cek selector)
- [ ] Test struktur dengan inspect element browser
- [ ] Update `repo.json` dengan GitHub username
- [ ] Buat branch `builds` di GitHub
- [ ] Test install di Cloudstream

---

## 🤝 Contributing

Punya template baru? Website dengan struktur unik?

1. Fork repository
2. Tambah template di `WEBSITE_TEMPLATES`
3. Test dengan website
4. Submit PR

---

## 📞 Support

Jika ada masalah:
1. Cek `config.json` untuk debug selector
2. Baca DOCUMENTATION.md
3. Inspect element website target
4. Sesuaikan selector di `.kt` file

---

## 📄 License

Free to use and modify

---

## ⭐ Tips

💡 **Simpan batch_config.json** untuk website favorit Anda

💡 **Fork template** untuk website dengan struktur unik

💡 **Dokumentasi perubahan** di README plugin

💡 **Test dulu di browser** sebelum edit selector

---

**Made with ❤️ for Cloudstream Community**

🎬 Happy Streaming! 🍿

# 🏛️ AzHua Extensions - Paviliun Kitab

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Repository publik untuk distribusi ekstensi [AzHua](https://github.com/dhasap/azhua) - aplikasi streaming Donghua dengan arsitektur modular.

## 📂 Struktur Repository

```
azhua-extensions/
├── index.json          # Katalog utama ekstensi
├── icons/              # Ikon ekstensi
│   └── anichin.png
└── README.md           # Dokumentasi ini
```

## 📋 Format index.json

File `index.json` adalah katalog yang dibaca oleh Core App AzHua untuk menampilkan daftar ekstensi yang tersedia.

```json
[
  {
    "name": "Anichin",
    "pkg": "com.azhua.ext.anichin",
    "versionCode": 2,
    "versionName": "2.0.0",
    "lang": "id",
    "icon": "https://raw.githubusercontent.com/dhasap/azhua-extensions/main/icons/anichin.png",
    "apkUrl": "https://github.com/dhasap/azhua-extensions/releases/download/v2.0.0/ext-anichin-v2.0.0.apk"
  }
]
```

### Field Penjelasan

| Field | Deskripsi |
|-------|-----------|
| `name` | Nama tampilan ekstensi |
| `pkg` | Package name (unik) |
| `versionCode` | Versi kode (integer) |
| `versionName` | Versi tampilan (string) |
| `lang` | Bahasa konten (id/en/jp/etc) |
| `icon` | URL raw gambar ikon |
| `apkUrl` | URL download APK dari Releases |

## 🚀 Cara Menambahkan Ekstensi Baru

### 1. Build APK Ekstensi

```bash
# Di project AzHua utama
./gradlew :ext-anichin:assembleRelease
```

### 2. Rename APK

```bash
mv ext-anichin/build/outputs/apk/release/ext-anichin-release-unsigned.apk \
   ext-anichin-v2.0.0.apk
```

### 3. Buat Release Baru

1. Buka https://github.com/dhasap/azhua-extensions/releases/new
2. Buat tag baru (misal: `v2.0.0`)
3. Upload APK ke lampiran
4. Publish release

### 4. Update index.json

Tambahkan entry baru ke `index.json`:

```json
{
  "name": "NamaEkstensi",
  "pkg": "com.azhua.ext.namaekstensi",
  "versionCode": 1,
  "versionName": "1.0.0",
  "lang": "id",
  "icon": "https://raw.githubusercontent.com/dhasap/azhua-extensions/main/icons/namaekstensi.png",
  "apkUrl": "https://github.com/dhasap/azhua-extensions/releases/download/v1.0.0/ext-namaekstensi-v1.0.0.apk"
}
```

### 5. Commit & Push

```bash
git add index.json icons/
git commit -m "Add extension: NamaEkstensi v1.0.0"
git push origin main
```

## 🔗 URL Raw

Core App AzHua membaca dari URL raw:

```
https://raw.githubusercontent.com/dhasap/azhua-extensions/main/index.json
```

## 📱 Ekstensi Tersedia

| Nama | Versi | Bahasa | Deskripsi |
|------|-------|--------|-----------|
| Anichin | 2.0.0 | 🇮🇩 ID | Scraper untuk anichin.co.id |

## 🤝 Kontribusi

Ingin menambahkan ekstensi baru? Fork repository ini dan buat Pull Request!

## 📜 Lisensi

[MIT License](LICENSE)

---

Dibuat dengan ❤️ untuk para kultivator Donghua

# Panduan Optimasi Video untuk Undangan Wedding

## 1. Gunakan FFmpeg untuk Kompresi (Recommended)

### Install FFmpeg
- **Windows**: Download dari https://ffmpeg.org/download.html
- **Mac**: `brew install ffmpeg`
- **Linux**: `sudo apt-get install ffmpeg`

### Command untuk Optimasi

#### Opsi A: Balanced (Rekomendasi)
```bash
ffmpeg -i cover2.mp4.mp4 -c:v libx264 -preset slow -crf 23 -b:v 3000k -c:a aac -b:a 128k cover2_optimized.mp4
```

#### Opsi B: High Quality (File lebih besar)
```bash
ffmpeg -i cover2.mp4.mp4 -c:v libx264 -preset veryslow -crf 18 -b:v 5000k -c:a aac -b:a 192k cover2_hq.mp4
```

#### Opsi C: Lightweight (File lebih kecil)
```bash
ffmpeg -i cover2.mp4.mp4 -c:v libx264 -preset fast -crf 28 -b:v 1500k -c:a aac -b:a 96k cover2_light.mp4
```

### Parameter Penjelasan
- `-crf 18-28`: Quality (18=best, 28=worst). Gunakan 23 untuk balanced
- `-preset`: Kecepatan encoding (slow=better quality tapi lama)
- `-b:v`: Video bitrate (3000k = 3 Mbps recommended)
- `-b:a`: Audio bitrate (128k cukup untuk background music)

---

## 2. Gunakan Handbrake (GUI - Lebih Mudah)

1. Download: https://handbrake.fr/
2. Open video file
3. Preset: "HQ 1080p30 Surround"
4. Video Codec: **H.264 (x264)**
5. Quality: **RF 23** (balanced)
6. Click Encode

---

## 3. Perbandingan Ukuran File

| Kualitas | Bitrate | File Size (5 min) | Recommendation |
|----------|---------|------------------|---|
| Light | 1500 kbps | ~56 MB | Mobile first |
| Balanced | 3000 kbps | ~112 MB | **Standard** |
| High | 5000 kbps | ~187 MB | Desktop only |

---

## 4. Tips Tambahan

✅ **Potong video** - Gunakan durasi 5-10 detik max untuk background  
✅ **Resize jika perlu** - 1280x720 sudah cukup untuk web  
✅ **Hapus audio** - Ganti dengan musik dari HTML (sudah ada di script)  
✅ **Gunakan format MP4 H.264** - Kompatibilitas universal terbaik  

---

## 5. Setelah Dioptimasi

1. Rename hasil optimize menjadi `cover2_optimized.mp4`
2. Copy ke folder undangan-pernikahan
3. Update di HTML jika perlu:
```html
<source src="cover2_optimized.mp4" type="video/mp4">
```

---

## Estimasi Hasil

**Sebelum**: cover2.mp4.mp4 (unknown size)  
**Sesudah**: ~100-120 MB (tergantung durasi & setting)

Dengan optimasi ini, video akan:
- ✅ Load lebih cepat
- ✅ Kualitas tetap bagus
- ✅ Kompatibel semua device
- ✅ Tidak buffering saat scroll

---

**Questions?** Hubungi untuk bantuan lebih lanjut!

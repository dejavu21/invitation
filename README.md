# Website Undangan Pernikahan 💒

Website undangan pernikahan modern yang dibuat dengan Python Flask. Fitur lengkap untuk mengelola undangan, RSVP, galeri foto, dan ucapan dari tamu.

## ✨ Fitur Utama

- 🏠 **Halaman Utama** - Countdown timer, info pengantin, preview acara
- 📅 **Detail Acara** - Informasi lengkap akad dan resepsi
- 📸 **Galeri Foto** - Koleksi foto prewedding, lamaran, dan couple
- 📝 **RSVP** - Sistem konfirmasi kehadiran tamu
- 💬 **Ucapan & Doa** - Tamu dapat mengirim ucapan
- 👤 **Admin Panel** - Dashboard untuk mengelola data RSVP
- 📱 **Responsive Design** - Tampil sempurna di semua device
- 🎨 **Modern UI/UX** - Design elegan dengan animasi smooth

## 🚀 Cara Instalasi

### 1. Clone Repository
```bash
git clone <repository-url>
cd wedding-invitation
```

### 2. Buat Virtual Environment
```bash
python -m venv venv

# Windows
venv\Scripts\activate

# macOS/Linux
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Setup Database
Database SQLite akan dibuat otomatis saat pertama kali menjalankan aplikasi.

### 5. Konfigurasi
Edit file `app.py` untuk menyesuaikan:
- Secret key
- Tanggal pernikahan
- Informasi pengantin
- Detail acara

### 6. Jalankan Aplikasi
```bash
python app.py
```

Aplikasi akan berjalan di `http://localhost:5000`

## 📁 Struktur File

```
wedding-invitation/
│
├── app.py                 # File utama Flask
├── requirements.txt       # Dependencies Python
├── README.md             # Dokumentasi
│
├── templates/            # Template HTML
│   ├── base.html         # Template dasar
│   ├── index.html        # Halaman utama
│   ├── details.html      # Detail acara
│   ├── gallery.html      # Galeri foto
│   ├── rsvp.html         # Form RSVP
│   ├── wishes.html       # Ucapan tamu
│   └── admin.html        # Panel admin
│
├── static/               # File statis (CSS, JS, Images)
│   ├── css/
│   ├── js/
│   └── images/
│
└── wedding.db            # Database SQLite (akan dibuat otomatis)
```

## 🎨 Kustomisasi

### 1. Mengubah Informasi Pengantin
Edit bagian berikut di `templates/index.html`:
```html
<h2 class="display-3 fw-bold mb-4">
    Nama Pria & Nama Wanita
</h2>
```

### 2. Mengubah Tanggal Pernikahan
Edit di `app.py`:
```python
wedding_date = datetime(2024, 12, 25, 16, 0, 0)  # Tahun, Bulan, Tanggal, Jam
```

### 3. Mengubah Warna Tema
Edit variabel CSS di `templates/base.html`:
```css
:root {
    --primary-color: #d4a574;      # Warna utama
    --secondary-color: #2c3e50;    # Warna sekunder
    --accent-color: #e8c39e;       # Warna aksen
}
```

### 4. Mengganti Foto
- Foto pengantin: Edit URL di `templates/index.html`
- Foto galeri: Edit URL di `templates/gallery.html`
- Atau upload foto ke folder `static/images/`

## 📊 Panel Admin

Akses panel admin di `/admin` untuk melihat:
- Statistik RSVP
- Daftar tamu yang akan hadir
- Jumlah total tamu
- Export data ke CSV
- Quick actions untuk mengelola tamu

## 🔧 API Endpoints

- `GET /` - Halaman utama
- `GET/POST /rsvp` - Form RSVP
- `GET/POST /wishes` - Ucapan tamu
- `GET /gallery` - Galeri foto
- `GET /details` - Detail acara
- `GET /admin` - Panel admin
- `GET /api/countdown` - API countdown timer

## 📱 Fitur Mobile

Website ini fully responsive dan optimized untuk:
- Desktop (1200px+)
- Tablet (768px - 1199px)
- Mobile (< 768px)

## 🎯 Deploy ke Production

### 1. Heroku
```bash
# Install Heroku CLI
pip install gunicorn
echo "web: gunicorn app:app" > Procfile

# Deploy
heroku create your-wedding-app
git push heroku main
```

### 2. PythonAnywhere
1. Upload semua file
2. Setup virtual environment
3. Configure WSGI
4. Update domain settings

### 3. VPS/Dedicated Server
```bash
# Install nginx dan supervisor
sudo apt update
sudo apt install nginx supervisor

# Setup gunicorn
pip install gunicorn
gunicorn -w 4 -b 0.0.0.0:8000 app:app
```

## 🔒 Keamanan

- Gunakan SECRET_KEY yang kuat di production
- Set DEBUG=False di production
- Gunakan HTTPS
- Backup database secara berkala

## 🛠️ Troubleshooting

### Error: Database tidak terbuat
```bash
python
>>> from app import db, app
>>> with app.app_context():
...     db.create_all()
>>> exit()
```

### Error: Module tidak ditemukan
```bash
pip install -r requirements.txt
```

### Error: Port sudah digunakan
```bash
# Ubah port di app.py
if __name__ == '__main__':
    app.run(debug=True, port=5001)
```

## 🤝 Kontribusi

1. Fork repository
2. Buat branch feature (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push ke branch (`git push origin feature/AmazingFeature`)
5. Buka Pull Request

## 📄 Lisensi

Project ini menggunakan MIT License. Lihat file `LICENSE` untuk detail.

## 📞 Support

Jika mengalami masalah atau butuh bantuan:
- Buat issue di GitHub
- Email: support@yourwedding.com
- WhatsApp: +62-xxx-xxx-xxxx

## 🙏 Terima Kasih

Terima kasih telah menggunakan template ini untuk hari bahagia Anda! 

---

**Made with ❤️ for your special day**

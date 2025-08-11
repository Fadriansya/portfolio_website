# 🌐 Personal Portfolio Website - Nasrullah Akbar Fadriansyah

Website portfolio interaktif dengan desain unik, menampilkan profil, pengalaman, proyek, dan form tanya jawab AI berbasis **IBM Granite** melalui API Replicate.  
Dibangun menggunakan **HTML, CSS, dan JavaScript** untuk frontend, serta **Node.js** (serverless function) untuk backend proxy AI yang di-host di **Vercel**.

---

## 📌 Demo

- **Frontend (Portfolio Website):** [https://fadriansya.github.io/portfolio_website/](https://fadriansya.github.io/portfolio_website/)
- **Backend (Proxy AI di Vercel):** `https://ai-backend-neon.vercel.app/` _(ganti sesuai URL Vercel backend Anda)_

---

## 🖼️ Deskripsi Website

Website ini bertujuan sebagai personal branding dan showcase proyek, dengan fitur unik:

- Navbar di keempat sudut layar.
- Ilustrasi wajah yang menghadap ke arah menu yang diklik.
- **AI Form** yang memungkinkan pengunjung bertanya dan mendapatkan jawaban otomatis dari **IBM Granite AI**.

---

## ✨ Fitur Interaktif

1. **Navbar Sudut Layar**  
   Menu _About_, _Experience_, _Projects_, dan _Contact_ ditempatkan di keempat sudut layar.
2. **Animasi Wajah Dinamis**  
   Ilustrasi wajah menghadap ke arah menu navigasi yang dipilih.
3. **AI Form Tanya Jawab**  
   Terintegrasi dengan **IBM Granite AI** via API Replicate, melalui backend proxy untuk keamanan.
4. **Responsive Design**  
   Tampilan optimal di desktop maupun perangkat mobile.
5. **Hosting Terpisah**

- Frontend: GitHub Pages
- Backend: Vercel (serverless function)

---

## 📂 Struktur Folder

### Frontend (`portfolio_website`)

```plaintext
portfolio_website/
│
├── assets/               # Gambar, ikon, screenshot, dll.
├── css/                  # File CSS (style utama & responsive)
│   └── style.css
├── js/                   # File JavaScript
│   ├── main.js           # Animasi wajah & interaksi navbar
│   └── ai-form.js        # Logika AI Form (fetch ke backend)
├── index.html            # Halaman utama
├── aiform.html           # Halaman AI Form
└── README.md             # Dokumentasi proyek
```

---

## ⚙️ Setup Frontend

### Menjalankan Secara Lokal

1. **Clone Repository**
   ```bash
   git clone https://github.com/fadriansya/portfolio_website.git
   cd portfolio_website
   ```
2. **Buka di Browser**

   - Klik dua kali `index.html`, atau
   - Gunakan Live Server di VS Code untuk auto-refresh.

3. **Hubungkan ke Backend**

   - Edit `js/ai-form.js`:

   ```javascript
   const API_URL = "https://ai-backend-neon.vercel.app/api/ai";
   ```

4. **Test AI Form**

   - Buka `aiform.html` di browser.
   - Ketik pertanyaan dan lihat jawaban AI.

5. **Deploy ke GitHub Pages**
   - Push semua file ke branch `main` di GitHub.
   - Aktifkan GitHub Pages di Settings → Pages → Branch: `main` → `/root`.
   - Akses website di `https://github.com/Fadriansya/portfolio_website`.

---

## ⚙️ Setup Backend

### Menjalankan Secara Lokal

1. **Clone Repository**
   ```bash
   git clone https://github.com/Fadriansya/ai-backend
   cd portfolio_backend_ai
   ```
2. **Install Dependencies**
   ```bash
   npm install
   ```
3. **Set Token API**
   - Buat file `.env`:
   ```ini
   REPLICATE_API_TOKEN=TOKEN_KAMU
   ```
4. **Jalankan**
   ```bash
   vercel dev
   ```
   Backend berjalan di `http://localhost:3000/api/ai`.

### Deploy ke Vercel

1. **Install Vercel CLI**
   ```bash
   npm install -g vercel
   ```
2. **Login**
   ```bash
   vercel login
   ```
3. **Deploy**
   ```bash
   vercel
   ```
4. **Atur Environment Variables** di dashboard Vercel:

   - `REPLICATE_API_TOKEN = TOKEN_KAMU`

5. Simpan URL Vercel dan update di `ai-form.js` frontend.

---

## 🔄 Alur AI Form

```plaintext
[Pengguna] --(pertanyaan)--> [Frontend: aiform.html]
     |
     v
[JS fetch()] --> [Backend Proxy di Vercel] --> [Replicate API] --> [IBM Granite AI]
     |
     v
[Jawaban AI ditampilkan di halaman]
```

**Keterangan:**

- Frontend tidak langsung mengakses API Replicate → menghindari kebocoran token.
- Backend proxy menyimpan `REPLICATE_API_TOKEN` sebagai environment variable di Vercel.

---

## 🛠️ Cara Modifikasi

- **Ubah Wajah/Ilustrasi:** Ganti file gambar di `assets/`.
- **Tambah Menu Baru:** Edit `index.html` dan tambahkan logika arah pandangan di `main.js`.
- **Ganti Model AI:** Ubah endpoint di backend (`ai.js`) dengan model lain di Replicate.

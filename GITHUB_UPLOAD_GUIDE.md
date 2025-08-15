# Panduan Upload ke GitHub (Sesuai Tutorial YouTube)

## Langkah-langkah Upload Proyek ke GitHub

### ✅ Langkah 1: Persiapan Awal

Pastikan Anda sudah:

- Memiliki akun GitHub
- Git sudah terinstall di komputer
- Sudah login ke GitHub

### ✅ Langkah 2: Inisialisasi Git Repository

Buka terminal/command prompt di folder proyek Anda (`d:/web ml`) dan jalankan:

```bash
# Inisialisasi git repository
git init

# Tambahkan semua file ke staging area
git add .

# Commit pertama
git commit -m "Initial commit: Item Build Manager Vue 3"
```

### ✅ Langkah 3: Buat Repository di GitHub

1. **Buka browser** dan masuk ke https://github.com
2. **Klik tombol "+"** di pojok kanan atas
3. **Pilih "New repository"**
4. **Isi form:**
   - Repository name: `item-build-manager`
   - Description: `Aplikasi Vue 3 untuk mengelola build item game`
   - Pilih "Public"
   - **JANGAN** centang "Initialize this repository with a README"
5. **Klik "Create repository"**

### ✅ Langkah 4: Hubungkan dengan GitHub

Setelah repository dibuat, GitHub akan memberikan perintah. Jalankan di terminal:

```bash
# Hubungkan dengan repository GitHub
git remote add origin https://github.com/[username-anda]/item-build-manager.git

# Push ke GitHub
git branch -M main
git push -u origin main
```

### ✅ Langkah 5: Verifikasi Upload

1. **Refresh halaman GitHub** Anda
2. **Cek apakah semua file sudah ter-upload**
3. **Akses repository Anda** di: `https://github.com/[username-anda]/item-build-manager`

### ✅ Langkah 6: Setup GitHub Pages (Optional)

1. **Di repository GitHub Anda, klik tab "Settings"**
2. **Scroll ke bagian "Pages"**
3. **Pada "Source", pilih "Deploy from a branch"**
4. **Pilih branch "main" dan folder "/ (root)"**
5. **Klik "Save"**
6. **Tunggu beberapa menit untuk deployment**
7. **Akses aplikasi di: `https://[username-anda].github.io/item-build-manager`**

### 🎯 Perintah Lengkap untuk Copy-Paste:

```bash
# Terminal/Command Prompt di folder proyek Anda (d:/web ml)
git init
git add .
git commit -m "Initial commit: Item Build Manager Vue 3"
git remote add origin https://github.com/[username-anda]/item-build-manager.git
git branch -M main
git push -u origin main
```

### 📱 Tips Cepat:

- Ganti `[username-anda]` dengan username GitHub Anda
- Jika ada error saat push, pastikan Anda sudah login ke GitHub di terminal
- Untuk login: `git config --global user.email "email@anda.com"` dan `git config --global user.name "Nama Anda"`

Proyek Anda sekarang siap untuk di-upload ke GitHub dengan cara yang sama persis seperti tutorial YouTube tersebut!

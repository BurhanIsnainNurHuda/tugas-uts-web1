# tugas-uts-web1

## Tugas UTS Pemrograman Web 1 - UT Bookstore

Website e-commerce toko buku untuk UT. Dibuat untuk memenuhi tugas UTS Mata Kuliah Pemrograman Web 1.

##  Identitas Mahasiswa

- **Nama:** [Burhan Isnain Nur Huda]
- **NIM:** [312410226] 
- **Kelas:** [TI.24.A2]
- **Mata Kuliah:** Pemrograman Web 1
- **Dosen:** [Agung Nugroho, S.Kom., M.Kom]

##  Fitur Website

- **Sistem Login** - Authentication dengan role admin dan user
- **Katalog Buku** - Menampilkan buku dengan gambar dan detail
- **Keranjang Belanja** - Fitur add to cart dan checkout
- **Tracking Pengiriman** - Lacak status pesanan
- **Responsive Design** - Bisa diakses di desktop dan mobile
- **Dark/Light Mode** - Toggle tema

##  Akun untuk Testing

### Admin
- Email: `siti@gmail.com`
- Password: `siti123`

### User  
- Email: `burhanisnain7@gmail.com`
- Password: `burhan123`

## 📁 Struktur File

tugas-uts-web1/
├── index.html # Halaman login
├── dashboard.html # Dashboard admin
├── stok.html # Katalog buku
├── checkout.html # Keranjang belanja
├── tracking.html # Tracking pengiriman
├── css/
│ └── style.css # File stylesheet
├── js/
│ ├── data.js # Data books & users
│ └── script.js # Functions JavaScript
└── img/ # Gambar buku
├── pengantar_komunikasi.jpg
├── manajemen_keuangan.jpg
├── kepemimpinan.jpg
├── mikrobiologi.jpg
├── paud_perkembangan.jpg
├── laskar_pelangi.jpg
└── kbbi.jpg


## 🛠️ Teknologi

- HTML5
- CSS3 
- JavaScript (Vanilla)
- LocalStorage untuk penyimpanan data

## 🎯 Cara Menjalankan

1. Download atau clone repository ini
2. Buka file `index.html` di browser web
3. Login dengan akun testing di atas

## 📝 Penjelasan Tugas

Website ini dibuat untuk memenuhi requirements tugas UTS:

### ✅ HTML
- Struktur semantic yang valid
- Form validation
- Modal windows
- Responsive layout

### ✅ CSS  
- Custom design dengan CSS variables
- Flexbox & Grid layout
- Dark/light theme
- Mobile responsive

### ✅ JavaScript
- DOM manipulation
- Event handling
- LocalStorage management
- Form validation & alerts

### ✅ Fitur Tambahan
- Modular file structure
- User experience yang baik
- Creative UI components

## 🔧 Fungsi Tiap Halaman

- **index.html** - Halaman login dengan validasi
- **dashboard.html** - Dashboard untuk admin
- **stok.html** - Katalog buku dengan search
- **checkout.html** - Keranjang dan form checkout  
- **tracking.html** - Tracking pengiriman pesanan

**Catatan:** Project ini menggunakan client-side JavaScript dan LocalStorage untuk simulasi database.

## Hasil Screenshoot
<img width="1918" height="951" alt="image" src="https://github.com/user-attachments/assets/c0099f07-845a-4f1c-b40c-9fdfeaa72593" />
<img width="1919" height="959" alt="image" src="https://github.com/user-attachments/assets/eeefcb2d-25f2-4901-bb98-8bb7b0885390" />

<img width="1894" height="953" alt="image" src="https://github.com/user-attachments/assets/2989d85e-e177-45fb-b513-27089f4f3efb" />
<img width="1919" height="947" alt="image" src="https://github.com/user-attachments/assets/235e4439-4c96-4b5c-9080-a7ea7b373f61" />
<img width="1918" height="951" alt="image" src="https://github.com/user-attachments/assets/636b1709-bf69-4a7d-8e9a-1db695d3cf65" />

## Source Code

##1
``index.html``

    <!DOCTYPE html>
    <html lang="id">
    <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UT Bookstore - Login</title>
    <link rel="stylesheet" href="css/style.css">
    <link href="https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css" rel="stylesheet">
    </head>
    <body class="login-page">
    <div class="login-container">
        <div class="login-header">
            <div class="logo">
                <i class='bx bx-book-reader'></i>
                <span>UT Bookstore</span>
            </div>
            <h1>Sistem Pemesanan Buku</h1>
        </div>
    <form class="login-form" onsubmit="return handleLogin(event)">
            <div class="input-group">
                <i class='bx bx-envelope'></i>
                <input type="email" id="email" placeholder="Email" required>
            </div>
       <div class="input-group">
                <i class='bx bx-lock-alt'></i>
                <input type="password" id="password" placeholder="Password" required>
            </div>
     <div class="form-options">
                <label class="checkbox">
                    <input type="checkbox" id="rememberMe">
                    <span class="checkmark"></span>
                    Ingat saya
                </label>
                <a href="#" class="forgot-password">Lupa Password?</a>
            </div>

            <button type="submit" class="btn-primary login-btn">
                Masuk
            </button>
        </form>

        <div class="demo-accounts">
            <h3>Akun Demo:</h3>
            <div class="demo-item">
                <strong>Admin:</strong> siti@gmail.com / siti123
            </div>
            <div class="demo-item">
                <strong>User:</strong> burhanisnain7@gmail.com / burhan123
            </div>
            <div class="demo-item">
                <strong>User:</strong> wahyuandika0147@gmail.com / wahyuandika123
            </div>
        </div>
    </div>
    <script src="js/data.js"></script>
    <script src="js/script.js"></script>
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Auto fill untuk testing
            document.getElementById('email').value = 'burhanisnain7@gmail.com';
            document.getElementById('password').value = 'burhan123';
        });
    </script>
    </body>
    </html>

##2

``js/data.js``

    // Data pengguna
    var dataPengguna = [
    {
        id: 1,
        nama: "Burhan Isnain",
        email: "burhanisnain7@gmail.com",
        password: "burhan123",
        role: "User",
    },
    {
        id: 2,
        nama: "Wahyu andika",
        email: "wahyuandika0147@gmail.com",
        password: "wahyuandika123",
        role: "User",
    },
    {
        id: 3,
        nama: "Agus Pranoto",
        email: "agus@gmail.com",
        password: "agus123",
        role: "User",
    },
    {
        id: 4,
        nama: "Siti Marlina",
        email: "siti@gmail.com",
        password: "siti123",
        role: "Admin",
    }
    ];
    // Data katalog buku
    var dataKatalogBuku = [
    {
        kodeBarang: "ASIP4301",
        namaBarang: "Pengantar Ilmu Komunikasi",
        jenisBarang: "Buku Ajar",
        edisi: "2",
        stok: 548,
        harga: "Rp 180.000",
        cover: "https://images.unsplash.com/photo-1481627834876-b7833e8f5570?w=200&h=260&fit=crop",
        penulis: "Prof. Dr. Ahmad Syafii, M.Si.",
        deskripsi: "Buku pengantar yang komprehensif untuk memahami dasar-dasar ilmu komunikasi."
    },
    {
        kodeBarang: "EKMA4002",
        namaBarang: "Manajemen Keuangan",
        jenisBarang: "Buku Ajar",
        edisi: "3",
        stok: 392,
        harga: "Rp 220.000",
        cover: "https://images.unsplash.com/photo-1554224155-6726b3ff858f?w=200&h=260&fit=crop",
        penulis: "Dr. Bambang Hartadi, SE., Ak., M.Si.",
        deskripsi: "Panduan lengkap manajemen keuangan untuk perusahaan dan organisasi."
    },
    {
        kodeBarang: "EKMA4310",
        namaBarang: "Kepemimpinan",
        jenisBarang: "Buku Ajar",
        edisi: "1",
        stok: 278,
        harga: "Rp 150.000",
        cover: "https://images.unsplash.com/photo-1526304640581-d334cdbbf45e?w=200&h=260&fit=crop",
        penulis: "Dr. Sri Mulyani, M.M.",
        deskripsi: "Mengembangkan keterampilan kepemimpinan efektif di era modern."
    },
    {
        kodeBarang: "BIOL4211",
        namaBarang: "Mikrobiologi Dasar",
        jenisBarang: "Buku Ajar",
        edisi: "2",
        stok: 165,
        harga: "Rp 200.000",
        cover: "https://images.unsplash.com/photo-1532187863486-abf9dbad1b69?w=200&h=260&fit=crop",
        penulis: "Prof. Dr. Maria Ulfa, M.Si.",
        deskripsi: "Dasar-dasar mikrobiologi untuk mahasiswa kedokteran dan biologi."
    },
    {
        kodeBarang: "PAUD4401",
        namaBarang: "Perkembangan Anak Usia Dini",
        jenisBarang: "Buku Ajar",
        edisi: "4",
        stok: 204,
        harga: "Rp 250.000",
        cover: "https://images.unsplash.com/photo-1544716278-ca5e3f4abd8c?w=200&h=260&fit=crop",
        penulis: "Dr. Siti Aminah, M.Pd.",
        deskripsi: "Panduan memahami perkembangan anak usia dini secara holistik."
    },
    {
        kodeBarang: "NVL001",
        namaBarang: "Laskar Pelangi",
        jenisBarang: "Novel",
        edisi: "1",
        stok: 89,
        harga: "Rp 85.000",
        cover: "https://images.unsplash.com/photo-1543002588-bfa74002ed7e?w=200&h=260&fit=crop",
        penulis: "Andrea Hirata",
        deskripsi: "Kisah inspiratif tentang perjuangan sekelompok anak di Belitung."
    },
    {
        kodeBarang: "REF002",
        namaBarang: "Kamus Besar Bahasa Indonesia",
        jenisBarang: "Buku Referensi",
        edisi: "5",
        stok: 156,
        harga: "Rp 350.000",
        cover: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=200&h=260&fit=crop",
        penulis: "Tim Penyusun KBBI",
        deskripsi: "Kamus lengkap bahasa Indonesia edisi terbaru."
    }
    ];
    // Data tracking
    var dataTracking = {
    "20230012": {
        nomorDO: "20230012",
        nama: "Rina Wulandari",
        status: "Dalam Perjalanan",
        ekspedisi: "JNE",
        tanggalKirim: "2025-08-25",
        paket: "0JKT01",
        total: "Rp 180.000",
        perjalanan:[
            {
                waktu: "2025-08-25 10:12:20",
                keterangan: "Penerimaan di Loket: TANGERANG SELATAN. Pengirim: Universitas Terbuka"
            },
            {
                waktu: "2025-08-25 14:07:56",
                keterangan: "Tiba di Hub: TANGERANG SELATAN"
            },
            {
                waktu: "2025-08-25 16:30:10",
                keterangan: "Diteruskan ke Kantor Jakarta Selatan"
            },
        ]
    },
    "20230013": {
        nomorDO: "20230013",
        nama: "Agus Pranoto",
        status: "Dikirim",
        ekspedisi: "Pos Indonesia",
        tanggalKirim: "2025-08-25",
        paket: "0UPBJJBDG",
        total: "Rp 220.000",
        perjalanan:[
            {
                waktu: "2025-08-25 10:12:20",
                keterangan: "Penerimaan di Loket: TANGERANG SELATAN. Pengirim: Universitas Terbuka"
            },
            {
                waktu: "2025-08-25 14:07:56",
                keterangan: "Tiba di Hub: TANGERANG SELATAN"
            },      
            {
                waktu: "2025-08-25 16:30:10",
                keterangan: "Diteruskan ke Kantor Kota Bandung"
            },
            {
                waktu: "2025-08-26 12:15:33",
                keterangan: "Tiba di Hub: Kota BANDUNG"
            },
            {
                waktu: "2025-08-26 15:06:12",
                keterangan: "Proses antar ke Cimahi"
            },
            {
                waktu: "2025-08-26 20:00:00",
                keterangan: "Selesai Antar. Penerima: Agus Pranoto"
            }
        ]
    }
    };
    // Fungsi helper untuk mencari user berdasarkan email
    function getUserByEmail(email) {
    return dataPengguna.find(user => user.email === email);
    }
    // Fungsi validasi login
    function validateLogin(email, password) {
    const user = getUserByEmail(email);
    return user && user.password === password;
    }
    // Fungsi untuk mendapatkan buku berdasarkan kode
    function getBookByCode(kodeBarang) {
    return dataKatalogBuku.find(book => book.kodeBarang === kodeBarang);
    }
    // Fungsi untuk mendapatkan tracking berdasarkan nomor DO
    function getTrackingByDoNumber(doNumber) {
    return dataTracking[doNumber];
    }

## 3

``js/script``

    // Fungsi untuk handle login
    function handleLogin(event) {
    if (event) {
        event.preventDefault();
    }
    const email = document.getElementById('email').value.trim();
    const password = document.getElementById('password').value;

    // Validasi input
    if (!email || !password) {
        alert('Harap isi email dan password');
        return false;
    }

    const user = validateLogin(email, password);
    
    if (user) {
        // Simpan data user ke localStorage
        localStorage.setItem('currentUser', JSON.stringify(user));
        localStorage.setItem('isLoggedIn', 'true');
        
        alert('Login berhasil!');
        
        // Redirect berdasarkan role
        setTimeout(() => {
            if (user.role === 'Admin') {
                window.location.href = 'dashboard.html';
            } else {
                window.location.href = 'stok.html';
            }
        }, 1000);
        
    } else {
        alert('Email atau password salah!');
    }

    return false;
    }
    // Fungsi untuk mengecek status login
    function checkLoginStatus() {
    const isLoggedIn = localStorage.getItem('isLoggedIn');
    const currentUser = JSON.parse(localStorage.getItem('currentUser') || 'null');
    
    if (isLoggedIn && currentUser) {
        if (currentUser.role === 'Admin') {
            window.location.href = 'dashboard.html';
        } else {
            window.location.href = 'stok.html';
        }
    }
    }
    // Fungsi untuk logout
    function handleLogout() {
    localStorage.removeItem('currentUser');
    localStorage.removeItem('isLoggedIn');
    window.location.href = 'index.html';
     }
    // Fungsi untuk menampilkan notifikasi
    function showNotification(message, type = 'info') {
    const notification = document.createElement('div');
    notification.className = `notification ${type}`;
    notification.innerHTML = `
        <div class="notification-content">
            <i class='bx ${type === 'success' ? 'bx-check-circle' : type === 'error' ? 'bx-error-circle' : 'bx-info-circle'}'></i>
            <span>${message}</span>
        </div>
           `;

    document.body.appendChild(notification);

    setTimeout(() => {
        notification.classList.add('show');
    }, 100);

    setTimeout(() => {
        notification.classList.remove('show');
        setTimeout(() => {
            if (notification.parentNode) {
                notification.remove();
            }
        }, 300);
    }, 3000);
    }

    // Theme toggle functionality
    document.addEventListener('DOMContentLoaded', function() {
    const themeToggle = document.getElementById('themeToggle');
    const currentTheme = localStorage.getItem('theme') || 'light';  
    
    document.documentElement.setAttribute('data-theme', currentTheme);
    updateThemeIcon(themeToggle, currentTheme);
    
    if (themeToggle) {
        themeToggle.addEventListener('click', function() {
            const currentTheme = document.documentElement.getAttribute('data-theme');
            const newTheme = currentTheme === 'light' ? 'dark' : 'light';
            
            document.documentElement.setAttribute('data-theme', newTheme);
            localStorage.setItem('theme', newTheme);
            updateThemeIcon(this, newTheme);
        });
    }
    });
    function updateThemeIcon(button, theme) {
    if (!button) return;
    
    const icon = button.querySelector('i');
    if (icon) {
        if (theme === 'dark') {
            icon.className = 'bx bx-sun';
        } else {
            icon.className = 'bx bx-moon';
        }
    }
    }
    // Format Rupiah helper function
    function formatRupiah(amount) {
    return 'Rp ' + amount.toLocaleString('id-ID');
    }

# Cara Membuat Stablecoin di Kii Chain
Proyek ini adalah panduan praktis untuk membuat dan menguji stablecoin berbasis ERC20 di Kii Chain. Stablecoin yang dibuat diberi nama IDR, dan dapat dimint oleh siapa saja hanya dengan memasukkan alamat wallet ke dalam form mint—tanpa perlu koneksi wallet seperti Metamask.

Tujuan dari proyek ini adalah:
- Memberikan contoh nyata pembuatan stablecoin di Kii Chain
- Menunjukkan alur minting yang terbuka dan transparan
- Mendorong builder lain untuk bereksperimen dan berkontribusi ke ekosistem Kii

# 🧩 Tahapan
1. Penjelasan Awal
Kita akan membuat token ERC20 bernama IDR yang berfungsi sebagai stablecoin. Token ini bisa dimint oleh siapa saja melalui antarmuka web sederhana. Tidak perlu koneksi wallet—cukup masukkan alamat tujuan dan klik "Mint".

2. Siapkan Solidity
Gunakan template ERC20 standar dari OpenZeppelin. Tambahkan fungsi mint(address to, uint256 amount) yang bisa dipanggil publik (untuk demo purposes).
```
function mint(address to, uint256 amount) public {
    _mint(to, amount);
}
```

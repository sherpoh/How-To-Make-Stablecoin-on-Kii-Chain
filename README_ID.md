# 🪙 Cara Membuat Stablecoin di Kii Chain
Proyek ini adalah panduan praktis untuk membuat dan menguji stablecoin berbasis ERC20 di Kii Chain. Stablecoin yang dibuat diberi nama IDR, dan dapat dimint oleh siapa saja hanya dengan memasukkan alamat wallet ke dalam form mint—tanpa perlu koneksi wallet seperti Metamask.

Tujuan dari proyek ini adalah:
- Memberikan contoh nyata pembuatan stablecoin di Kii Chain
- Menunjukkan alur minting yang terbuka dan transparan
- Mendorong builder lain untuk bereksperimen dan berkontribusi ke ekosistem Kii

## 🧩 Tahapan Pembuatan Token
### 1. Penjelasan Awal
Kita akan membuat token ERC20 bernama IDR yang berfungsi sebagai stablecoin. Token ini bisa dimint oleh siapa saja melalui antarmuka web sederhana. Tidak perlu koneksi wallet—cukup masukkan alamat tujuan dan klik "Mint".

### 2. Siapkan Solidity
Gunakan template ERC20 standar. Tambahkan fungsi mint(address to, uint256 amount) yang bisa dipanggil publik (untuk demo purposes). Simpan file TokenIDR.sol di [Remix](https://remix.ethereum.org/)

**<mark>TokenIDR.sol</mark>**
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract IDRStablecoin is ERC20 {
    constructor() ERC20("Indonesian Rupiah", "IDR") {}

    function decimals() public view virtual override returns (uint8) {
        return 6;
    }

    function mint(address to, uint256 amount) public {
        _mint(to, amount);
    }
}
```
### 3. Deploy
Deploy kontrak ke testnet Kii Chain (atau jaringan EVM kompatibel lain jika belum tersedia). Simpan alamat kontrak dan ABI untuk digunakan di frontend

### 4. Test Mint di Remix
Buka Remix IDE, paste kode Solidity, deploy, dan uji fungsi mint() dengan memasukkan alamat tujuan dan jumlah token.

### 5. Deploy ke Web (Mint)
Buat halaman HTML/JS dengan form input alamat dan jumlah token. Tambahkan tombol "Mint" yang memanggil fungsi mint() langsung ke kontrak menggunakan ethers.js.. Tidak perlu koneksi wallet.

### 6. Done
Stablecoin IDR siap digunakan dan dimint oleh siapa saja. Repositori ini bisa dijadikan template untuk stablecoin lain di ekosistem Kii Chain.

# Netplan Config Generator

Script Bash sederhana untuk membuat file konfigurasi **Netplan** (`01-netcfg-multi.yaml`) secara interaktif.  
Dengan script ini, kamu dapat menambahkan banyak interface jaringan sekaligus, baik menggunakan **DHCP** maupun **static IP**.

---

## Fitur
- Mendukung konfigurasi multiple interface.
- Pilihan DHCP atau static IP.
- Input interaktif untuk IP Address, Gateway, dan DNS.
- Output otomatis disimpan ke file `01-netcfg-multi.yaml`.

---

## Cara Menggunakan

1. Clone repository:
   ```bash
   git clone https://github.com/drprawedha/netplan_generator.git
   cd repo
   ```
2. Beri permission agar script bisa dieksekusi:
   ```bash
   chmod +x netplan-generator.sh
   ```
3. Jalankan script:
   ```bash
   ./netplan-generator.sh
   ```
4. Ikuti instruksi interaktif di terminal:
- Masukkan nama interface (contoh: ens33)
- Pilih metode konfigurasi (true untuk DHCP, no untuk static)
- Jika static, masukkan IP Address, Gateway, dan DNS
- Ulangi untuk interface lain jika diperlukan
- Setelah selesai, file konfigurasi akan dibuat di: 01-netcfg-multi.yaml

## Catatan

File hasil script (01-netcfg-multi.yaml) masih perlu dipindahkan ke direktori netplan:
```bash
sudo mv 01-netcfg-multi.yaml /etc/netplan/
sudo netplan try
```
Pastikan Anda memiliki hak akses root untuk menerapkan konfigurasi.
Gunakan dengan hati-hati, karena salah konfigurasi dapat menyebabkan server kehilangan koneksi jaringan.

## 1. Deskripsi Skenario

Mahasiswa mengajukan KRS dengan memilih mata kuliah. Sistem memvalidasi kelengkapan data, prasyarat mata kuliah, dan bentrok jadwal. Jika valid, pengajuan disimpan dengan status menunggu persetujuan dosen wali. Mahasiswa dapat memilih mengunduh bukti pengajuan. Dosen wali kemudian menyetujui atau menolak KRS dan memberikan catatan keputusan.

## 2. Tabel Kebutuhan

| ID | Kebutuhan |
|---|---|
| SIA-R01 | Mahasiswa dapat melihat jadwal kuliah. |
| SIA-R02 | Admin akademik dapat mengelola jadwal kuliah. |
| SIA-R03 | Mahasiswa dapat mengajukan KRS. |
| SIA-R04 | Sistem memvalidasi KRS saat pengajuan. |
| SIA-R05 | Mahasiswa dapat mengunduh bukti pengajuan jika memilihnya. |
| SIA-R06 | Dosen wali dapat menyetujui atau menolak KRS. |

## 3. Batas Sistem dan Aturan

**Batas sistem:**
- Pengguna telah login.
- Data mata kuliah, prasyarat, dan jadwal tersedia.
- Pembayaran, pengisian nilai, dan implementasi basis data tidak termasuk dalam tugas.

**Aturan:**
- KRS harus lolos validasi agar berhasil disimpan.
- Bukti pengajuan bersifat opsional.
- KRS yang tersimpan belum berarti telah disetujui dosen wali.
- Admin akademik tidak dimasukkan ke diagram KRS karena pengelolaan jadwal berasal dari tugas sebelumnya.

## 4. Tabel Identifikasi Aktor

| Aktor | Peran |
|---|---|
| Mahasiswa | Melihat jadwal, mengajukan KRS, dan mengunduh bukti pengajuan. |
| Dosen Wali | Memproses persetujuan atau penolakan KRS. |

## 5. Tabel Katalog Use Case

| ID | Nama Use Case | Aktor/Peran | Sumber Kebutuhan |
|---|---|---|---|
| SIA-UC01 | Lihat jadwal kuliah | Mahasiswa | SIA-R01 |
| SIA-UC03 | Ajukan KRS | Mahasiswa | SIA-R03 |
| SIA-UC04 | Validasi KRS | Bagian dari proses sistem | SIA-R04 |
| SIA-UC05 | Unduh bukti pengajuan KRS | Mahasiswa | SIA-R05 |
| SIA-UC06 | Proses keputusan KRS | Dosen Wali | SIA-R06 |

## 6. Relasi Include

| Use Case Utama | Relasi | Use Case yang Disertakan | Alasan |
|---|---|---|---|
| SIA-UC03 Ajukan KRS | `<<include>>` | SIA-UC04 Validasi KRS | Setiap pengajuan KRS wajib melalui validasi. |

## 7. Relasi Extend

| Use Case Tambahan | Relasi | Use Case Dasar | Kondisi |
|---|---|---|---|
| SIA-UC05 Unduh bukti pengajuan KRS | `<<extend>>` | SIA-UC03 Ajukan KRS | Mahasiswa memilih mengunduh bukti setelah pengajuan berhasil. |
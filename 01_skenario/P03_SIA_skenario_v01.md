Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap 
pengajuan menjalankan validasi KRS yang memeriksa kelengkapan, 
prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil, 
sistem menyimpan pengajuan berstatus menunggu persetujuan dosen 
wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih 
mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS 
dan memberikan catatan keputusan. 

## 2. Kebutuhan dan batas sistem

| ID | Kebutuhan |
|---|---|
| SIA-R01 | Mahasiswa dapat mengajukan KRS. |
| SIA-R02 | Sistem memvalidasi kelengkapan, prasyarat mata kuliah, dan benturan jadwal. |
| SIA-R03 | Mahasiswa dapat mengunduh bukti pengajuan setelah KRS berhasil disimpan. |
| SIA-R04 | Dosen wali dapat menyetujui atau menolak pengajuan KRS. |
| SIA-R05 | Mahasiswa dapat melihat status pengajuan KRS. |

# 3 Asumsi dan aturan
- Pengguna telah terautentikasi.
- Data mata kuliah, prasyarat, dan jadwal tersedia.
- Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
- Mengunduh bukti bukan syarat keberhasilan pengajuan.
- KRS yang tersimpan belum berarti disetujui.
- Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas.
- Admin akademik tidak dimasukkan sebagai aktor pada model KRS ini karena tidak terlibat dalam skenario tugas praktik.

## 4 Aktor

| Aktor | Tujuan terhadap sistem |
|---|---|
| Mahasiswa | Mengajukan KRS dan, jika memilih, mengunduh bukti pengajuan. |
| Dosen wali | Menyetujui atau menolak KRS serta memberikan catatan keputusan. |


## 5 katalog usece

| ID | Nama Use Case | Aktor | Peran dalam Model |
|---|---|---|---|
| SIA-UC01 | Ajukan KRS | Mahasiswa | Fungsi utama pengajuan KRS |
| SIA-UC02 | Validasi KRS | Bagian perilaku sistem | Perilaku yang disertakan dalam UC01 |
| SIA-UC03 | Unduh bukti pengajuan KRS | Mahasiswa | Perilaku tambahan bersyarat pada UC01 |
| SIA-UC04 | Proses keputusan KRS | Dosen wali | Fungsi utama dosen wali |
| SIA-UC05 | Lihat status pengajuan KRS | Mahasiswa | Fungsi untuk mengetahui status pengajuan |

## 6 include

| Elemen | Keterangan |
|---|---|
| Use Case Utama | SIA-UC01 — Ajukan KRS |
| Use Case Include | SIA-UC02 — Validasi KRS |
| Sumber | SIA-R02 |
| Tujuan | Memastikan data lengkap, prasyarat mata kuliah terpenuhi, dan tidak terdapat benturan jadwal. |
| Relasi | SIA-UC01 `<<include>>` SIA-UC02 |
| Alasan | Validasi merupakan bagian wajib dari setiap proses pengajuan KRS. |


## 7 extance

| Elemen | Keterangan |
|---|---|
| Use Case Dasar | SIA-UC01 — Ajukan KRS |
| Use Case Tambahan | SIA-UC03 — Unduh bukti pengajuan KRS |
| Sumber | SIA-R03 |
| Extension Point | Bukti pengajuan tersedia pada konfirmasi penyimpanan. |
| Kondisi | Mahasiswa memilih mengunduh bukti. |
| Relasi | SIA-UC03 `<<extend>>` SIA-UC01 |
| Alasan | Pengajuan tetap berhasil meskipun mahasiswa tidak mengunduh bukti. |
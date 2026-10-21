| Elemen | Keterangan |
|---|---|
| Tujuan | Menyimpan pengajuan KRS untuk diproses dosen wali. |
| Aktor utama | Mahasiswa |
| Sumber | SIA-R01, SIA-R02, SIA-R03 |
| Pemicu | Mahasiswa memilih fungsi pengajuan KRS. |
| Prasyarat | Mahasiswa telah terautentikasi dan data mata kuliah tersedia. |
| Pascakondisi berhasil | Pengajuan tersimpan dengan status Menunggu persetujuan dosen wali. |
| Pascakondisi gagal | Pengajuan tidak berhasil tersimpan. |
| Include | SIA-UC02 — Validasi KRS |
| Extend | SIA-UC03 — Unduh bukti pengajuan KRS |


## 1. SIA-UC01 — Ajukan KRS

| Elemen | Deskripsi |
|---|---|
| ID | SIA-UC01 |
| Nama Use Case | Ajukan KRS |
| Tujuan | Menghasilkan pengajuan KRS yang tersimpan untuk diproses dosen wali. |
| Aktor Utama | Mahasiswa |
| Sumber Kebutuhan | SIA-R01, SIA-R02, SIA-R03 |
| Pemicu | Mahasiswa memilih fungsi pengajuan KRS. |
| Prasyarat | Mahasiswa telah terautentikasi dan data mata kuliah tersedia. |
| Pascakondisi Berhasil | Pengajuan tersimpan dengan status Menunggu persetujuan dosen wali. |
| Pascakondisi Gagal | Pengajuan baru tidak berhasil tersimpan. |
| Include | SIA-UC02 — Validasi KRS |
| Extend | SIA-UC03 — Unduh bukti pengajuan KRS |
| Extension Point | Bukti pengajuan tersedia pada konfirmasi penyimpanan. |

## 2. SIA-UC02 — Validasi KRS

| Elemen | Deskripsi |
|---|---|
| ID | SIA-UC02 |
| Nama Use Case | Validasi KRS |
| Tujuan | Memastikan pengajuan KRS memenuhi ketentuan yang ditetapkan. |
| Aktor Utama | Tidak ada aktor langsung; dipanggil oleh SIA-UC01. |
| Sumber Kebutuhan | SIA-R02 |
| Pemicu | SIA-UC01 meminta proses validasi. |
| Prasyarat | Pengajuan telah dikirim dan data yang dibutuhkan tersedia. |
| Pascakondisi Berhasil | Seluruh pemeriksaan validasi dinyatakan lolos. |
| Pascakondisi Gagal | Sistem mengembalikan hasil validasi gagal beserta informasi masalah. |
| Relasi | `<<include>>` dari SIA-UC01. |

## 3. SIA-UC03 — Unduh Bukti Pengajuan KRS

| Elemen | Deskripsi |
|---|---|
| ID | SIA-UC03 |
| Nama Use Case | Unduh bukti pengajuan KRS |
| Tujuan | Memberikan bukti pengajuan KRS kepada mahasiswa. |
| Aktor Utama | Mahasiswa |
| Sumber Kebutuhan | SIA-R03 |
| Pemicu | Mahasiswa memilih opsi unduh bukti pada konfirmasi pengajuan. |
| Prasyarat | Pengajuan KRS berhasil tersimpan. |
| Pascakondisi Berhasil | Bukti pengajuan berhasil diunduh. |
| Pascakondisi Gagal | Pengajuan tetap tersimpan, tetapi bukti tidak berhasil diunduh. |
| Relasi | `<<extend>>` terhadap SIA-UC01. |
| Kondisi Extend | Mahasiswa memilih untuk mengunduh bukti. |
| Extension Point | Bukti pengajuan tersedia pada konfirmasi penyimpanan. |

## 4. SIA-UC04 — Proses Keputusan KRS

| Elemen | Deskripsi |
|---|---|
| ID | SIA-UC04 |
| Nama Use Case | Proses keputusan KRS |
| Tujuan | Mencatat keputusan persetujuan atau penolakan pengajuan KRS. |
| Aktor Utama | Dosen wali |
| Sumber Kebutuhan | SIA-R04 |
| Pemicu | Dosen wali memilih pengajuan KRS yang menunggu keputusan. |
| Prasyarat | Dosen wali telah terautentikasi dan pengajuan tersedia untuk diproses. |
| Pascakondisi Berhasil | Keputusan dan catatan tersimpan serta status pengajuan diperbarui. |
| Pascakondisi Gagal | Keputusan baru tidak berhasil tersimpan dan status sebelumnya dipertahankan. |

## 5. SIA-UC05 — Lihat Status Pengajuan KRS

| Elemen | Deskripsi |
|---|---|
| ID | SIA-UC05 |
| Nama Use Case | Lihat status pengajuan KRS |
| Tujuan | Memungkinkan mahasiswa mengetahui status terkini pengajuan KRS. |
| Aktor Utama | Mahasiswa |
| Sumber Kebutuhan | SIA-R05 |
| Pemicu | Mahasiswa membuka menu status pengajuan KRS. |
| Prasyarat | Mahasiswa telah terautentikasi. |
| Pascakondisi Berhasil | Status pengajuan KRS ditampilkan kepada mahasiswa. |
| Pascakondisi Gagal | Sistem menampilkan informasi jika pengajuan belum tersedia. |
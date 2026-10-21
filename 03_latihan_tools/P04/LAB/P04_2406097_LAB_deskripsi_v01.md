# use case deskripsi
| Elemen | LAB-UC11: Catat Pengembalian Peralatan |
|---|---|
| ID dan nama | LAB-UC11: Catat Pengembalian Peralatan |
| Sumber kebutuhan | LAB-R09 dan LAB-R10 |
| Tujuan | Pengembalian tercatat dan status peminjaman serta kondisi peralatan terbaru. |
| Aktor utama | Petugas Laboratorium |
| Pemicu | Petugas memilih fungsi pencatatan pengembalian dan menentukan peminjaman yang akan dikembalikan. |
| Prasyarat | Petugas telah terautentikasi; peminjaman terpilih berstatus Dipinjam. |
| Pascakondisi berhasil | Pengembalian tercatat dengan tanggal kembali dan kondisi peralatan; status peminjaman menjadi Selesai. |
| Pascakondisi gagal | Tidak ada pengembalian baru yang tercatat; status peminjaman tidak berubah. |
| Include | LAB-UC12: Periksa Kondisi Peralatan |
| Collaboration | LAB-CO02: Catat Pengembalian Peralatan |

# Alur Utama

| Langkah | Tindakan petugas | Respons sistem |
|---|---|---|
| 1 | Memilih peminjaman yang akan dikembalikan | Menampilkan data peminjaman terpilih dan statusnya |
| 2 | Mengonfirmasi alat yang kembali dan jumlahnya | Menampung konfirmasi petugas |
| 3 | Tidak ada | Memeriksa status peminjaman harus Dipinjam |
| 4 | Tidak ada | Menjalankan LAB-UC12: memeriksa dan mencatat kondisi peralatan |
| 5 | Menyimpan pencatatan pengembalian | Menyimpan tanggal kembali dan kondisi; mengubah status peminjaman menjadi Selesai |
| 6 | Melihat konfirmasi | Menampilkan ringkasan pengembalian |
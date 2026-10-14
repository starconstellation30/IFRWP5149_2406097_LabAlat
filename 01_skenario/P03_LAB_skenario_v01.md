Mahasiswa mengajukan peminjaman peralatan dengan memilih alat, jumlah, dan rentang waktu. Sistem memeriksa ketersediaan. Jika tersedia dan data lengkap, sistem menyimpan pengajuan berstatus menunggu keputusan. Pada tampilan konfirmasi, mahasiswa dapat memilih mencetak bukti pengajuan. Petugas mengelola data peralatan serta menyetujui atau menolak pengajuan. Kepala laboratorium melihat laporan peminjaman.

ID Kebutuhan
LAB-R01 Mahasiswa dapat melihat ketersediaan peralatan
LAB-R02 Petugas dapat mengelola data peralatan
LAB-R03 Mahasiswa dapat mengajukan peminjaman; sistem memeriksa
ketersediaan sebelum menyimpan pengajuan
LAB-R04 Mahasiswa dapat mencetak bukti pada konfirmasi pengajuan jika
memilihnya
LAB-R05 Petugas dapat menetapkan persetujuan atau penolakan pengajuan
LAB-R06 Kepala laboratorium dapat melihat laporan peminjaman
LAB-R01 dan LAB-R02 mempertahankan fungsi yang diperkenalkan pada
Pertemuan 2. Kebutuhan berikutnya menambah ruang lingkup analisis tanpa
mengubah arti kebutuhan lama.

Batas sistem dan aturan:
• Sistem mencatat dan menyediakan informasi; perpindahan fisik alat tidak
terjadi di dalam perangkat lunak.
• Pengguna telah terautentikasi dan memiliki hak akses sesuai peran.
• Pengajuan yang diterima sistem berstatus Menunggu keputusan, bukan
otomatis Disetujui.
Praktikum Analisis dan Desain Berorientasi Objek | 37
• Pengajuan dengan peralatan tidak tersedia tidak disimpan sebagai
pengajuan berhasil.
• Pencetakan bukti tidak menjadi syarat keberhasilan pengajuan.
• Persetujuan petugas belum dimodelkan sebagai reservasi teknis stok.
• Pengambilan, pengembalian, kondisi alat, dan denda belum dianalisis
pada potongan model ini.
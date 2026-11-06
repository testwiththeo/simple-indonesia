# Katalog Aturan: ASD-STE100 Issue 9 untuk teks perangkat lunak

Baca berkas ini untuk mode PERIKSA, mode Strict, atau bila nomor aturan dipertanyakan. SKILL.md menyebut aturan yang paling mengubah keluaran. Berkas ini memuat seluruh katalog.

53 aturan dalam 9 bagian, diadaptasi dari ASD-STE100 Issue 9 dengan contoh perangkat lunak. Aturan bertanda (S) hanya untuk mode Strict. Wording resmi ada di standar gratis asd-ste100.org.

### Bagian 1: Kata (Aturan 1.1-1.14)

| Aturan | Instruksi |
|---|---|
| 1.1-1.4, 1.6 (S) | Gunakan hanya kata yang disetujui, sesuai jenis kata, makna, dan bentuk yang tercantum. |
| 1.5 | Anda dapat menggunakan kata domain sebagai kata benda teknis ("webhook", "commit", "endpoint"). |
| 1.7 | Jangan gunakan kata benda teknis sebagai kata kerja. |
| 1.8 | Gunakan kata benda teknis proyek atau industri Anda. |
| 1.9 | Bila memilih kata benda teknis, pilih yang pendek dan jelas. |
| 1.10 | Tidak ada kata regional, slang, atau jargon sebagai kata benda teknis. |
| 1.11 | Satu item, satu nama. Jangan panggil "config" di sini dan "settings" di sana. |
| 1.12 | Anda dapat menggunakan kata kerja domain sebagai kata kerja teknis ("deploy", "compile", "merge"). Standar mengizinkan kata kerja komputer: klik, ketik, salin, tempel, hapus, simpan, instal, unduh, perbarui, dan lainnya. Bila kata kerja umum melakukan hal yang sama, gunakan itu: "temukan" bukan "deteksi". |
| 1.13 | Jangan gunakan kata kerja teknis sebagai kata benda. |
| 1.14 | Gunakan ejaan Bahasa Indonesia (KBBI). |

Dalam mode Plain, aturan 1.5, 1.8, dan 1.12 membuat kosakata domain Anda legal.

Sebelum: Anda dapat webhook event, lalu lakukan deploy.
Sesudah: Kirim event ke webhook. Lalu deploy layanan.

### Bagian 2: Kata benda majemuk (Aturan 2.1-2.2)

| Aturan | Instruksi |
|---|---|
| 2.1 | Tulis kata benda majemuk dari tiga kata atau lebih sedikit. |
| 2.2 | Bila kata benda teknis butuh lebih dari tiga kata, tulis lengkap sekali, lalu beri bentuk pendek atau hubungkan unitnya dengan tanda hubung. |

Pecah rantai kata benda panjang dengan preposisi (dari, pada, di, untuk):

Sebelum: the connection pool timeout configuration value
Sesudah: nilai timeout untuk connection pool

### Bagian 3: Kata kerja (Aturan 3.1-3.7)

| Aturan | Instruksi |
|---|---|
| 3.1 (S) | Gunakan hanya bentuk kata kerja yang diberikan kamus. |
| 3.2 | Gunakan hanya: infinitive, imperatif, present sederhana, past sederhana, future sederhana, partisipal lampau sebagai adjektiva. |
| 3.3 | Gunakan partisipal lampau hanya sebagai adjektiva ("respons yang di-cache"). |
| 3.4 | Tidak ada kata kerja bantu untuk konstruksi kompleks. Tidak ada present perfect, tidak ada "is to be installed". |
| 3.5 | Gunakan bentuk "-ing" hanya sebagai kata benda teknis atau di dalamnya, tidak pernah sebagai kata kerja. |
| 3.6 | Suara aktif. Dalam teks deskriptif, pasif legal hanya bila pelaku tidak diketahui. Untuk memperbaiki pasif tanpa pelaku, gunakan "Anda" (pembaca) atau "kami" (perusahaan): "Index tidak digunakan pada tabel ini" menjadi "Kami tidak menggunakan index pada tabel ini." |
| 3.7 | Jelaskan tindakan dengan kata kerja, bukan kata benda ("kompres berkas", bukan "lakukan kompresi berkas"). |

Kata bantu modal yang diizinkan: bisa, akan, harus. Dilarang: sebaiknya, mungkin, mungkinkah, dapat (gunaan bisa). Tangga modal di akhir berkas memberi pengganti.

### Bagian 4: Kalimat (Aturan 4.1-4.5)

| Aturan | Instruksi |
|---|---|
| 4.1 | Tulis kalimat pendek dan jelas. |
| 4.2 | Jangan hilangkan kata atau gunakan kontraksi untuk memendekkan kalimat. Pertahankan "yang", pertahankan "bahwa". |
| 4.3 | Gunakan daftar vertikal untuk teks kompleks: titik dua di awal, huruf kapital, titik hanya pada item kalimat penuh, tidak ada campuran instruksi dan fakta, tidak ada nested. |
| 4.4 | Gunakan kata penghubung antar kalimat pada topik terkait ("Lalu", "Sebagai hasil"). |
| 4.5 | Taruh adjektiva penunjuk (ini, tersebut) sebelum kata benda bila berlaku. Pengecualian: tidak ada artikel sebelum kata benda bila identifier mengikutinya: "Restart pod web-7f9b2". |

Aturan 4.2 adalah aturan anti-pendek. Bahasa Indonesia sederhana adalah kalimat pendek dengan tata bahasa lengkap, bukan gaya telegram:

Salah memendek: Pastikan berkas ada sebelum menjalankan.
Benar: Pastikan berkas ada sebelum Anda menjalankan perintah.

### Bagian 5: Penulisan prosedural (Aturan 5.1-5.5)

| Aturan | Instruksi |
|---|---|
| 5.1 | Maksimal 20 kata per kalimat. Peringatan dan kehati-hatian termasuk. |
| 5.2 | Satu instruksi per kalimat, kecuali dua tindakan terjadi bersamaan. Satu langkah boleh menambah satu kalimat untuk hasil langsung atau batas. |
| 5.3 | Tulis instruksi dalam imperatif: "Jalankan migrasi." |
| 5.4 | Taruh kondisi wajib sebelum perintah, dipisah koma: "Jika build gagal, baca log." |
| 5.5 | Catatan memberi informasi, tidak pernah instruksi atau batas. Batas menyertai tindakannya. Tes catatan: prosedur tetap berjalan bagi pembaca yang menghapus semua catatan. |

Sebelum: Anda perlu mengambil API key dari dashboard sebelum mengonfigurasi klien, yang dapat Anda lakukan di bawah Settings.
Sesudah: Ambil API key dari dashboard, di bawah Settings. Lalu konfigurasi klien dengan key ini.

### Bagian 6: Penulisan deskriptif (Aturan 6.1-6.6)

| Aturan | Instruksi |
|---|---|
| 6.1 | Beri informasi bertahap: satu fakta baru per kalimat. |
| 6.2 | Gunakan kata kunci dan frasa untuk memberi teks struktur logis. |
| 6.3 | Maksimal 25 kata per kalimat. |
| 6.4 | Kelompokkan informasi terkait dalam paragraf. |
| 6.5 | Satu topik per paragraf. |
| 6.6 | Maksimal enam kalimat per paragraf. |

### Bagian 7: Instruksi keselamatan (Aturan 7.1-7.3)

| Aturan | Instruksi |
|---|---|
| 7.1 | Gunakan kata yang menunjukkan level risiko ("PERINGATAN" = cedera, "HATI-HATI" = kerusakan). Bila dua risiko terjadi bersama, gunakan "PERINGATAN". |
| 7.2 | Mulai dengan perintah atau kondisi yang jelas. |
| 7.3 | Lalu beri risiko atau hasil yang mungkin. |

Taruh instruksi sebelum penjelasan. Gunakan pola sama untuk flag CLI destruktif dan migrasi yang tidak dapat dibatalkan.

Sebelum: Perhatikan bahwa kehilangan data mungkin terjadi dalam beberapa keadaan bila flag destruktif diaktifkan saat menjalankan terhadap production.
Sesudah: HATI-HATI: Jangan gunakan flag `--force` terhadap production. Flag menghapus baris yang tidak cocok dengan sumber.

### Bagian 8: Tanda baca dan jumlah kata (Aturan 8.1-8.7)

| Aturan | Instruksi |
|---|---|
| 8.1 | Semua tanda baca standar legal kecuali titik koma. Tulis dua kalimat sebagai gantinya. |
| 8.2 | Gunakan tanda hubung untuk menghubungkan kata yang bertindak sebagai satu unit. |
| 8.3 | Tanda kurung legal untuk referensi, nomor item, singkatan, bentuk jamak, penjelasan, alternatif. |
| 8.4 | Dalam daftar vertikal, titik dua awal mengakhiri kalimat untuk jumlah kata. Tiap item setelah titik dua dihitung sebagai kalimat baru dan mendapat anggaran 20/25 kata sendiri. |
| 8.5-8.7 | Hitung sebagai satu kata masing-masing: teks dalam kurung, kata bersambung, angka, angka dengan unit, singkatan, identifier, teks dikutip, judul, label, kata benda proper. |

Aturan 8.6 penting untuk teks perangkat lunak: `sqlpipe run --config sqlpipe.yaml` dalam backtick dihitung satu kata.

Tanda hubung (aturan skill ini, bukan standar): em-dash (`—`) menyambung dua pernyataan dan menyembunyikan logika di antaranya. Sebutkan hubungan ("karena", "tetapi", "misalnya") atau tulis dua kalimat. Spasi atau dua tanda hubung antara pernyataan adalah dash sama. Rentang (`5–10`), penanda daftar, dan flag (`--force`) bukan dash.

### Bagian 9: Praktik penulisan (Aturan 9.1-9.4, GR-1 sampai GR-8)

| Aturan | Instruksi |
|---|---|
| 9.1 | Bila penggantian kata per kata tidak bekerja, susun ulang kalimat. |
| 9.2 (S) | Gunakan tiap kata yang disetujui dengan benar: makna dan jenis kata yang disetujui. |
| 9.3 | Utamakan kata kerja satu kata daripada frasa kata kerja ("turunkan", bukan "turun"; "instal", bukan "set up"). Mode Strict: frasa kata kerja adalah pelanggaran. |
| 9.4 | Pertahankan satu gaya dan terminologi konsisten di seluruh dokumen. |

Rekomendasi umum: pertahankan "bahwa" (GR-1), kata kerja utama pertama dan alat setelah "dengan" (GR-2: "Ambil URL dengan curl"), rujukan kata ganti jelas (GR-3), "ini + kata benda" (GR-4), bahasa inklusif (GR-7). GR-6: "misalnya" untuk e.g., "yaitu" untuk i.e., hapus "dst." dan sebutkan itemnya.

### Tangga Modal

| Anda menulis | Tulis pengganti |
|---|---|
| sebaiknya (kebutuhan) | harus |
| sebaiknya (rekomendasi) | Hapus, atau nyatakan sebagai fakta: "X lebih baik karena Y." |
| sebaiknya (kondisional terbalik: "jika terjadi kegagalan") | jika: "Jika kegagalan terjadi" |
| mungkin / mungkinkah / dapat (kemungkinan) | bisa |
| mungkin (izin) | bisa |
| akan (hipotetis) | bisa, atau susun ulang: "Jika X terjadi, Y terjadi." |

## Tanda Penulisan AI

Teks AI menyimpang ke arah yang dikenal. Aturan di atas sudah menghapus sebagian. Waspadai sisanya:

- Signifikansi berlebih: tidak ada "vital", "krusial", "sebuah bukti". Nyatakan fakta.
- Paralelisme negatif: tidak ada "bukan hanya X, tetapi Y".
- Aturan tiga: tidak ada triplet dekoratif.
- Atribusi samar: tidak ada "studi menunjukkan". Sebutkan sumber, atau buang klaim.
- Rentang palsu: tidak ada "berkisar dari X ke Y" tanpa batas nyata.
- Ringkasan restating: tidak ada paragraf "kesimpulannya".
- Aside editorial: tidak ada "perlu dicatat".
- Sisa kolaborasi: tidak ada "Semoga membantu", tidak ada "Beritahu saya".
- Kebiasaan format: tidak ada tebal sebagai dekorasi, tidak ada lead-in tebal, tidak ada emoji sebagai struktur, tidak ada heading untuk dua kalimat.

Untuk kata berlebih spesifik, `references/word-swaps.md` memetakan masing-masing ke pengganti sederhana. Jika kata tidak membawa fakta, hapus saja.

## Pilihan Kata

Satu kata, satu makna, satu jenis kata, untuk seluruh dokumen (Aturan 1.11, 9.4).

- Berkas konfigurasi adalah `konfigurasi`, tidak pernah config, settings, atau options dalam dokumen sama.
- Konsep verifikasi adalah `pastikan`, tidak pernah check, verify, confirm, validate, atau ensure sebagai kata kerja. Mode Strict merutekan sisanya dengan `references/strict-vocabulary.md`.
- Swap umum: however menjadi tetapi, therefore menjadi sebagai hasil, since (= karena) menjadi karena, perform menjadi lakukan, avoid menjadi cegah, repeat menjadi lakukan lagi, acceptable menjadi diizinkan, now dihapus.

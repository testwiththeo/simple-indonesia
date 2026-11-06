---
name: simple-indonesia
description: Write or rewrite text in plain, layman-readable Bahasa Indonesia in the spirit of ASD-STE100 Simplified Technical English, for documentation, READMEs, runbooks, procedures, error messages, release notes, and explanations for readers outside the field. Use when the user says "bahasa Indonesia sederhana", "plain Indonesian", "tanpa jargon", "jelaskan sederhana", "buat readable", "tulis untuk bukan ahli", "de-slop", or asks for docs that translate well. The same rules govern the reply: answer first, prose only.
license: MIT
compatibility: claude-code cursor codex gemini-cli opencode
metadata:
  version: "1.0.0"
  standard: ASD-STE100 Issue 9 (2025-01-15), adapted to Bahasa Indonesia
---

# Bahasa Indonesia Sederhana

Tulis Bahasa Indonesia sederhana yang dipahami pembaca cerdas di luar bidangmu dalam satu bacaan. Aturan diambil dari ASD-STE100, bahasa terkendali yang dipakai dirgantara untuk manual pemeliharaan. Ada dua register: dokumen yang kamu tulis atau sunting, dan balasan yang kamu ketik di chat. Masing-masing punya aturan pendek di bawah.

## Teks (Dokumen)

Saat diminta menulis atau menyunting dokumentasi, terapkan aturan ini pada prosa:

1. Klasifikasi tiap bagian. Teks prosedural memberi tahu pembaca apa yang harus dilakukan: kalimat perintah (imperatif), maksimal 20 kata per kalimat, satu instruksi per kalimat. Teks deskriptif menjelaskan: tense sederhana, maksimal 25 kata per kalimat, satu topik per paragraf, maksimal 6 kalimat per paragraf.
2. Jangan ubah kode, identifier, perintah, flag, jalur berkas, teks error yang dikutip, nama produk, atau fakta. Jika sumber tidak memberi angka atau penyebab, pertahankan pernyataan umum.
3. Kondisi sebelum perintah, dipisah koma: "Jika build gagal, baca log."
4. Gunakan tense sederhana dan suara aktif. Sebutkan pelaku: "Anda jalankan migrasi." Jangan sembunyikan pelaku di kalimat pasif tanpa alasan. Jika pelaku tidak diketahui, gunakan "Anda" (pembaca) atau "kami" (perusahaan).
5. Kata bantu modal: bisa, akan, harus. Jangan gunakan sebaiknya, mungkin, mungkinkah, dapat (gunakan bisa). Kebutuhan "sebaiknya" menjadi "harus". Pilihan dihapus.
6. Gunakan tata bahasa lengkap. Jangan gunakan gaya telegram yang memotong kata. Pertahankan "yang" dan "bahwa". Tulis kalimat pendek, bukan gaya telegram.
7. Jangan gunakan titik koma dan jangan gunakan tanda hubung em (—). Tulis dua kalimat, atau sebutkan hubungannya.
8. Satu kata, satu makna, untuk seluruh dokumen. Gunakan "pastikan" untuk check, verify, confirm, validate, ensure. Gunakan "konfigurasi" untuk config, settings, options. Pecah rantai kata benda lebih dari tiga kata dengan preposisi ("nilai timeout untuk connection pool").
9. Beri pembaca tiap istilah dan fakta sebelum langkah yang membutuhkannya. Definisikan istilah konsep saat pertama digunakan, di bawah 10 kata, satu per kalimat. Jangan definisikan nama produk, nama standar (Postgres, S3, HTTP), atau alat yang dibahas dokumen. Sebutkan host, flag, atau langkah sebelumnya yang diperlukan perintah. "Restart layanan" menjadi "Restart layanan `sync` di host yang menjalankan tugas."
10. Nyatakan fakta, bukan pentingnya. Hapus kata yang tidak membawa fakta: sangat, sangat penting, komprehensif, powerful, leverage, "untuk", "perlu dicatat". Jangan "bukan hanya X, tetapi Y". Tidak ada triplet dekoratif. Tidak ada "kesimpulannya".
11. Gunakan format hanya jika membawa struktur. Tidak ada lead-in tebal, tidak ada tebal sebagai penekanan, tidak ada emoji, tidak ada heading lebih dari dua kalimat. Daftar vertikal untuk tiga atau lebih item paralel: titik dua di awal, huruf kapital, satu instruksi per item.
12. Peringatan: perintah atau kondisi dulu, lalu risiko. "Jangan jalankan ini terhadap production. Perintah menghapus baris."

Gunakan ejaan Bahasa Indonesia (KBBI). `references/rule-catalog.md` memuat 53 aturan Issue 9 dengan contoh perangkat lunak, untuk mode PERIKSA. Untuk pesan error, runbook, laporan insiden, catatan rilis, pesan commit, atau teks UI, baca `references/use-cases.md` dulu.

Sebelum (keluaran AI):

> **Timeout koneksi.** Jika sqlpipe hang atau gagal dengan `dial tcp: i/o timeout`, pastikan bahwa host yang menjalankan sqlpipe dapat menjangkau port Postgres (biasanya 5432) — ini sering kali aturan security group atau firewall yang memblokir koneksi. Jika Anda menyambung ke database terkelola (RDS, Cloud SQL, dll.), konfirmasi instance mengizinkan koneksi dari IP sqlpipe.

Sesudah (prosedural, berjudul, bernomor):

> ## Timeout koneksi
>
> sqlpipe berhenti dengan `dial tcp: i/o timeout` bila tidak dapat menyambung ke port Postgres (5432 secara default).
>
> 1. Pastikan host yang menjalankan sqlpipe dapat menyambung ke port Postgres. Firewall atau security group biasanya memblokirnya.
> 2. Jika database terkelola (RDS, Cloud SQL), pastikan instance menerima koneksi dari IP sqlpipe.

## Balasan (Chat)

Tiap balasan chat, di tiap mode, mengikuti aturan ini:

1. Jawab dalam prosa. Tidak ada heading, tidak ada daftar bullet, tidak ada tebal, tidak ada tabel. Blok kode legal bila pembaca harus menyalinnya.
2. Kalimat pertama memberi jawaban atau hasil. Jangan mengulang pertanyaan.
3. Tidak ada em-dash. Sebutkan hubungan ("karena", "tetapi", "misalnya") atau tulis dua kalimat.
4. Definisikan istilah konsep dalam beberapa kata saat pertama digunakan: "idempoten (aman dijalankan dua kali)". Jangan definisikan nama produk.
5. Tidak ada pembuka ("Tentu", "Pertanyaan bagus") dan tidak ada penutup ("Semoga membantu", "Beritahu saya").
6. Jangan pendekkan teks error yang dikutip, peringatan keamanan, atau konfirmasi sebelum tindakan destruktif.

Sebelum: Kegagalan berasal dari pemilihan leader control-plane saat pod churn — tidak perlu khawatir!
Sesudah: Pod restart dan antrean kehilangan leader untuk waktu singkat. Ia pulih tanpa bantuan. Anda tidak perlu melakukan apa pun.

## Periksa Sebelum Kirim

1. Balasan: cari `—`, `**`, `#`, dan baris yang mulai dengan `-`. Hapus masing-masing.
2. Dokumen: hitung kata di tiga kalimat terpanjang. Di atas 20 atau 25, pecah. Cari `'`, `telah`, `sebaiknya`, `mungkin`, `;`, `—`, `**`, `check`, `verify`, `config`, dan heading yang mencakup kurang dari tiga kalimat. Perbaiki tiap temuan. Baca tiap langkah: apakah menyebut host, flag, atau langkah sebelumnya yang pembaca harus tahu? Jika tidak, tambahkan atau arahkan ke sana.

## Mode

Plain adalah default dan mencakup semua di atas. Strict berlaku bila pengguna menyebut STE, ASD-STE100, atau compliance: baca `references/strict-vocabulary.md` sebelum menyusun dokumen, dan sebutkan sekali bahwa tidak ada alat yang menjamin kepatuhan. Balasan tetap Plain di tiap mode.

Saat diminta MEMERIKSA teks bukan menulisnya, buka `references/rule-catalog.md` dulu. Lalu laporkan tiap pelanggaran sebagai: nomor aturan dikutip dari berkas itu, teks yang melanggar, tulisan ulang yang patuh. Jangan kutip nomor aturan dari ingatan. Bila pengguna meminta compliance, akhiri dengan satu kalimat: tidak ada alat yang dapat menjamin kepatuhan ASD-STE100, dan standar dapat diunduh gratis di asd-ste100.org.

## Batas

Aturan ini untuk fakta dan instruksi, bukan teks pemasaran atau penulisan merek, karena aturan menghapus persuasi. Katakan demikian, dan tawarkan untuk dokumentasi saja.

## Referensi

- `references/rule-catalog.md`: 53 aturan Issue 9 dengan contoh perangkat lunak, untuk mode PERIKSA
- `references/word-swaps.md`: pemetaan kata berlebihan ke kata sederhana
- `references/use-cases.md`: mode dan pola untuk pesan error, runbook, laporan insiden, catatan rilis, commit, teks UI, dan persiapan terjemahan
- `references/strict-vocabulary.md`: disiplin kamus untuk mode Strict

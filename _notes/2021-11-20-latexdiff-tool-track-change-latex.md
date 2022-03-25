---
layout: post
title: 'Latexdiff: Tool Track Changes di Latex'
collection: notes
---

Saya yakin (sebagian) pengguna Microsoft Word mengenal fitur <a href="https://support.microsoft.com/en-us/office/track-changes-in-word-197ba630-0f5f-4a8e-9a77-3712475e806a" target="_blank">track changes</a> di perangkat lunak ini. Fitur ini memungkinkan kita menelusuri perubahan yang dilakukan pada sebuah dokumen Word. Dalam dunia akademik, fitur ini salah satunya dipakai dalam revisi naskah yang dikirim ke sebuah jurnal. Dari sisi pemakaian, track changes ini sangat mudah untuk dioperasikan. Bagi pengguna Latex seperti saya, mungkin ada yang bertanya, adakah fitur serupa di Latex? Jawabannya: ada.

## Mengenal Latexdiff

Berawal dari tuntutan revisi paper, saya menemukan tool track changes di Latex yang bernama `latexdiff`. Agak berbeda dengan fitur track changes di Microsoft Word, Latexdiff bekerja dengan membandingkan dua file `.tex` kemudian menghasilkan sebuah file `.tex` baru yang apabila dieksekusi akan menampilkan perubahan yang terjadi. Kita akan belajar bagaimana cara menggunakan `latexdiff` di artikel ini.

## Instalasi

Jika anda pengguna Windows seperti saya, anda perlu melakukan langkah-langkah berikut untuk proses instalasi `latexdiff` di komputer anda.

1. `latexdiff` adalah script yang ditulis dalam bahasa pemrograman Perl, karena itu instalasi `latexdiff` memerlukan instalasi Perl. Versi Perl yang dibutuhkan adalah versi 5.8 atau lebih tinggi. Untuk Windows, Perl bisa di-instal melalui dua binary: <a href="https://www.activestate.com/products/perl/" target="_blank">ActiveState Perl</a> dan <a href="https://strawberryperl.com/" target="_blank">Strawberry Perl</a>. Silakan dipilih salah satu. Saya pribadi memilih Strawberry karena sifatnya yang 100% open source dan gratis, beda dengan ActiveState yang memiliki dua opsi (gratis dan berbayar). Secara default, Strawberry Perl terinstal di `C:\Strawberry`.
2. Selesai instalasi Perl, unduh `latexdiff` dari repositori <a href="https://ctan.org/pkg/latexdiff?lang=en" target="_blank">CTAN</a>.
3. Unzip file unduhan `latexdiff`, kemudian salin isinya ke lokasi instalasi Strawberry Perl, tepatnya di `C:\Strawberry\perl\bin`.
4. `latexdiff` telah ter-instal dan siap dipakai.

## Penggunaan

Sebagaimana yang sudah saya sebutkan di atas, untuk menggunakan `latexdiff`, kita memerlukan dua file `.tex` yang akan dibandingkan. Misalnya file kita adalah `initial.tex` dan `revised.tex`. Maka cara memakainya adalah sebagai berikut,

1. Letakkan `initial.tex` dan `revised.tex` di folder yang sama.
2. Buka `command prompt` di Windows, kemudian arahkan ke folder dimana kedua file tersebut ditaruh.
3. Eksekusi syntax berikut: `latexdiff initial.tex revised.tex > diff.tex`
4. Akan muncul file baru `diff.tex` di folder yang sama. Silakan eksekusi file ini untuk melihat hasilnya. Oh ya, nama file tidak harus `diff.tex`, bisa diganti dengan nama yang lain, misalnya `revision.tex` atau yang lain.
5. Secara default, `latexdiff` menggunakan penanda-penanda berikut untuk identifikasi perubahan di output dari file `diff.tex`:
    - kata atau kalimat yang dihapus akan diberi warna merah dan dicoret
    - kata atau kalimat baru akan diberi warna biru dan diberi garis bawah bergelombang

Contoh tampilan output dari `diff.tex` adalah ini:

<figure class="center">
    <img src="{{ site.url }}{{ site.baseurl }}/images/latexdiff.png" alt="">
</figure>

Sejauh ini, saya cukup puas dengan tampilan default ini. Namun, apabila anda ingin melakukan kustomisasi lebih lanjut, silakan belajar dari <a href="https://www.overleaf.com/learn/latex/Articles/Using_Latexdiff_For_Marking_Changes_To_Tex_Documents" target="_blank">sini</a>.

Demikian, semoga bermanfaat.
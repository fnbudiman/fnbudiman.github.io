---
layout: post_blog
title: Penjumlahan Vektor
categories: [Science and Technical]
tags: [aljabar_linear]
---

Sebagaimana pada skalar, operasi-operasi matematika juga berlaku bagi vektor. Di tulisan ini, kita akan membahas operasi penjumlahan (dan sekaligus pengurangan) pada vektor. Syarat dua vektor (atau lebih) bisa dijumlahkan adalah vektor-vektor tersebut mempunyai jumlah elemen yang sama, atau dengan kata lain, ukuran vektor-vektor tersebut harus sama persis.

Dua vektor yang dijumlahkan akan menghasilkan vektor lain yang ukurannya sama dengan vektor-vektor yang dijumlahkan tersebut. Operasi penjumlahan pada vektor dilakukan dengan menggunakan operator $$+$$. Sebagai contoh,

$$\begin{bmatrix}
4\\
5\\
7\\
\end{bmatrix}
+
\begin{bmatrix}
1\\
2\\
3\\
\end{bmatrix}
=
\begin{bmatrix}
5\\
7\\
10\\
\end{bmatrix}$$

Perhatikan bahwa penjumlahan vektor dilakukan dengan menjumlahkan elemen-elemen dengan posisi yang sama pada kedua vektor. Pengurangan vektor (dilakukan dengan operator $$-$$) juga dilakukan dengan prosedur serupa. Contohnya,

$$\begin{bmatrix}
4\\
5\\
7\\
\end{bmatrix}
-
\begin{bmatrix}
1\\
2\\
3\\
\end{bmatrix}
=
\begin{bmatrix}
3\\
3\\
4\\
\end{bmatrix}$$

## Sifat Penjumlahan Vektor 

Misalnya kita punya 3 vektor, katakanlah $$a$$, $$b$$, dan $$c$$. Operasi penjumlahan pada ketiga vektor ini mempunyai sifat-sifat berikut:

- $$a+b=b+a$$, sifat ini dinamakan sifat *komutatif*
- $$(a+b)+c=a+(b+c)$$, sifat ini dinamakan sifat *asosiatif*
- $$a+0=a$$, sifat ini menunjukkan bahwa penambahan sebuah vektor dengan vektor nol sama sekali tidak mempengaruhi vektor tersebut. Ingat bahwa 0 di sini adalah vektor (bukan skalar) yang ukurannya sama dengan ukuran vektor $$a$$
- $$a-a=0$$, sifat ini menunjukkan bahwa pengurangan sebuah vektor dengan vektor itu sendiri akan menghasilkan vektor nol. Ingat kembali bahwa 0 di sini adalah vektor dan bukan skalar, ukurannya sama dengan ukuran vektor $$a$$

Pembuktian sifat-sifat ini tidak terlalu sulit. Mari kita tunjukkan sifat komutatif dengan mengambil contoh "perpindahan benda". Kita akan mengambil vektor $$a$$ dan $$b$$ untuk merepresentasikan dua perpindahan. Perhatikan ilustrasinya di Gambar 1.

<figure class="center">
    <img src="{{ site.url }}{{ site.baseurl }}/images/penjumlahan-vektor.jpg" width="500" height="auto" alt="">
    <figcaption>Gambar 1. Ilustrasi sifat komutatif penjumlahan vekor <i>a</i> dan <i>b</i></figcaption>
</figure>

Di Gambar 1, gambar sebelah kiri menunjukkan jumlahan $$a+b$$ sebagai perpindahan total dengan mengambil perpindahan $$a$$ di awal, diikuti perpindahan $$b$$. Di gambar sebelah kanan, perpindahan $$b$$ dilakukan terlebih dahulu, baru kemudian perpindahan $$a$$. Hasil perpindahan totalnya adalah $$b+a$$. Bisa dilihat bahwa panjang dan arah $$a+b$$ sama persis dengan panjang dan arah $$b+a$$. Ilustrasi ini membuktikan sifat komutatif penjumlahan vektor.

Sifat-sifat penjumlahan vektor yang lain bisa dibuktikan menggunakan ilustrasi yang sama, atau langsung menggunakan angka-angka. Insya Allah tidak terlalu sulit.

---
layout: post_blog
title: Linearisasi Perkalian Dua Variabel
categories: [Science and Technical]
tags: [aljabar_linear]
---

Dalam dunia matematika, ekspresi yang melibatkan perkalian antar variabel dikenal dengan ekspresi non-linear. Ekspresi non-linear membuat proses perhitungan matematika menjadi "boros", dalam artian beban komputasi menjadi sangat besar. Pengalaman saya sendiri, beban komputasi yang besar ini sangat terasa ketika bekerja dengan jumlah variabel yang banyak. Salah satu solusi untuk mengurangi beban ini secara signifikan adalah dengan me-linear-kan ekspresi non-linear tersebut. Bagaimana caranya? Mari kita pelajari di postingan ini.

## Teori

Ada beberapa ragam perkalian antar variabel. Yang paling sering ditemui ada dua: (i) perkalian antara dua variabel kontinyu, dan (ii) perkalian antara variabel biner dan variabel kontinyu. Variabel kontinyu yang saya maksud adalah variabel yang bisa bernilai bilangan riil berapapun, baik integer maupun non-integer. Adapun variabel biner adalah variabel integer spesial yang hanya memiliki salah satu dari dua nilai, yakni 0 dan 1. Postingan ini saya khususkan untuk jenis perkalian yang kedua.

Misalkan kita memiliki ekspresi $$xi$$, dimana $$x$$ adalah variabel kontinyu dan $$i$$ adalah variabel biner. $$x$$ memiliki batas atas $$x^u$$ dan batas bawah $$x^l$$. Langkah pertama linearisasi adalah membuat variabel baru yang nilainya sama dengan $$xi$$, katakanlah $$y$$. Jadi, $$y=xi$$.

Langkah selanjutnya sangat mudah: ekspresi $$y=xi$$ kita gantikan dengan set pertidaksamaan berikut,

$$\min\{0,x^l\}\leq y\leq \max\{0,x^u\}$$

$$x^li\leq y\leq x^ui$$

$$x-x^u(1-i)\leq y\leq x-x^l(1-i)$$

Jadi, satu ekspresi tergantikan dengan tiga ekspresi. Lebih rumit? Tidak juga. Perhatikan di ketiga ekspresi tersebut. Tidak kita jumpai satu pun perkalian antar variabel. Yang ada adalah perkalian antara variabel dan konstanta.

## Contoh Aplikasi

Ekspresi non-linear banyak dijumpai di optimisasi sebagai bagian dari fungsi pengekang. Ekspresi ini bisa menyebabkan non-convexity pada optimisasi. Optimisasi non-convex jauh lebih kompleks penyelesaiannya dibanding optimisasi convex. Sebagai contoh, perhatikan fungsi pengekang berikut.

$$\begin{equation} 0\leq x_1\leq x_2i \end{equation}$$

dimana $$2\leq x_2\leq 5$$.

Di sini kita memiliki ekspresi non-linear $$x_2i$$, dimana $$x_2$$ adalah variabel kontinyu dan $$i$$ adalah variabel biner. Untuk proses linearisasi $$x_2i$$ ini, abaikan variabel $$x_1$$. Dengan mendefinisikan $$y=x_2i$$, ekspresi $$x_2i$$ kita gantikan dengan ekspresi berikut,

$$\begin{equation} \min\{0,2\}\leq y\leq \max\{0,5\} \end{equation}$$

$$\begin{equation} 2i\leq y\leq 5i \end{equation}$$

$$\begin{equation} x-5(1-i)\leq y\leq x-2(1-i) \end{equation}$$

Ekspresi (2) bisa disederhanakan menjadi

$$\begin{equation} 0\leq y\leq 5 \end{equation}$$

Ekspresi (3), (4), dan (5) ini kemudian kita substitusikan ke ekspresi (1), sehingga menjadi

$$\begin{equation}
\begin{split}
&0\leq x_1\leq y\\
&0\leq y\leq 5\\
&2i\leq y\leq 5i\\
&x-5(1-i)\leq y\leq x-2(1-i)
\end{split}
\end{equation}$$

Selesai. Perhatikan bahwa ekspresi (6) ini ekivalen dengan ekspresi (1). Silakan dibuktikan sendiri :).

Selamat mencoba
---
layout: post_blog
title: Fungsi Linear
categories: [Science and Technical]
tags: [aljabar_linear]
---

Di catatan kali ini, kita akan belajar mengenai fungsi linear. Fungsi linear bisa mempunyai beberapa definisi. Namun, khusus dalam aljabar linear, yang dimaksud fungsi linear adalah sebuah fungsi yang memetakan sebuah vektor secara linear (*linear map*) menjadi skalar. Aplikasi fungsi linear sangat banyak ditemui dalam kehidupan sehari-hari, terlebih-lebih dalam ilmu teknik.

## 1. Definisi Umum Fungsi

Notasi fungsi $$f$$ adalah $$f:\mathbb{R}^n\rightarrow\mathbb{R}$$, yang berarti bahwa $$f$$ adalah fungsi yang memetakan/mentransformasi sebuah vektor yang tersusun dari $$n$$ bilangan riil menjadi bilangan (skalar) riil. Vektor yang dipetakan tersebut dinamakan sebagai "argumen" dari fungsi $$f$$. Apabila vektor ini kita beri nama vektor $$x$$ dengan $$n$$ elemen, maka $$f(x)=f(x_1,x_2,...,x_n)$$ adalah sebuah skalar/bilangan riil yang disebut juga sebagai "nilai" fungsi $$f$$ pada $$x$$.

Mari kita ambil beberapa contoh:

Untuk $$n=5$$, berarti $$f:\mathbb{R}^5\rightarrow\mathbb{R}$$. Contohnya,

$$f(x)=x_1^2+x_2+x_3+x_4^2+x_5$$

Untuk $$n=4$$, berarti $$f:\mathbb{R}^4\rightarrow\mathbb{R}$$. Contohnya,

$$f(x)=x_1+x_2^2+x_4$$

Dari dua contoh di atas, dapat kita pastikan bahwa untuk $$x\in\mathbb{R}^n$$, $$f(x)$$ akan selalu berupa skalar/bilangan riil. 

Terkadang juga kita akan jumpai bahwa tidak ada hubungan analitik antara fungsi dan argumennya sebagaimana dua contoh di atas. Untuk kasus ini, biasanya nilai fungsi didapatkan dari percobaan empiris. Maka untuk mendapatkan rumus dari fungsi ini, kita perlu menempuh jalur yang disebut "aproksimasi fungsi".

## 2. Fungsi Perkalian Titik Vektor

Salah satu fungsi yang mempunyai bentuk spesial adalah fungsi yang merupakan hasil perkalian titik antara dua vektor. Misalkan kita punya sebuah vektor $$a$$, dimana $$a\in\mathbb{R}^n$$. Untuk argumen fungsi $$x\in\mathbb{R}^n$$, bentuk fungsi perkalian titik-nya adalah

$$\begin{equation}
f(x)=a^Tx=a_1x_1+a_2x_2+...+a_nx_n
\end{equation}$$

Jadi fungsi $$f(x)$$ ini adalah hasil perkalian titik antara vektor $$a$$ dengan argumen fungsi $$x$$. Bisa juga kita anggap bahwa $$f(x)$$ di (1) sebagai penjumlahan dengan bobot (*weighted sum*) dari elemen-elemen $$x$$.

Selanjutnya, perhatikan bahwa fungsi di (1) memenuhi sebuah properti yang dinamakan *superposisi*. Prinsip superposisi tergambarkan dalam persamaan berikut,

$$\begin{equation}
\begin{split}
f(\alpha x+\beta y)&=a^T(\alpha x+\beta y)\\
&=a^T(\alpha x)+a^T(\beta y)\\
&=\alpha(a^Tx)+\beta(a^Ty)\\
&=\alpha f(x)+\beta f(y)
\end{split}
\end{equation}$$

Jadi, prinsip superposisi fungsi menyatakan bahwa sebuah fungsi dengan argumen yang berupa jumlahan dengan bobot dari dua (atau lebih) vektor sama dengan jumlahan dengan bobot dari fungsi-fungsi individual dengan masing-masing argumen. (Kalau bingung dengan deskripsi ini, cukup lihat persamaan di atas. Sebuah persamaan terkadang lebih bermakna dari seribu kata 😐.) 

Fungsi yang memenuhi prinsip superposisi inilah yang disebut sebagai <u>fungsi linear</u>.

Perhatikan kembali bagian $$f(\alpha x+\beta y)=\alpha f(x)+\beta f(y)$$ di (2). Ada hal yang menarik di sini. Bagian di sebelah kiri sama dengan, yakni $$\alpha x+\beta y$$, melibatkan perkalian <u>skalar-vektor</u> dan penjumlahan <u>vektor-vektor</u>. Sementara bagian di sebelah kanan sama dengan, yakni $$\alpha f(x)+\beta f(y)$$, melibatkan perkalian skalar-skalar dan penjumlahan skalar-skalar. Uniknya adalah perubahan pola ini tidak merubah nilai fungsi.

Persamaan (2) mendeskripsikan prinsip superposisi yang melibatkan dua vektor argumen $$x$$ dan $$y$$, masing-masing dengan skalar pemberat $$\alpha$$ dan $$\beta$$. Kita bisa melebarkan prinsip superposisi ini untuk jumlah vektor yang lebih banyak. Jadi, selama $$f$$ adalah fungsi linear, prinsip superposisi berlaku untuk kombinasi linear dari banyak vektor, berapapun jumlahnya. Secara matematis, prinsip ini dinyatakan sebagai berikut,

$$\begin{equation}
f(\alpha_1x_1, \alpha_2x_2,...\alpha_kx_k)=\alpha_1f(x_1)+\alpha_2f(x_2)+...+\alpha_kf(x_k)
\end{equation}$$

untuk sembarang vektor-vektor $$x_1,...,x_k$$ dan sembarang skalar-skalar $$\alpha_1,...,\alpha_k$$. Intinya, ekspresi (3) merupakan generalisasi dari (2).

Lebih jauh, prinsip superposisi dapat dipecah menjadi dua properti. Satu properti melibatkan perkalian skalar-vektor dan properti lainnya melibatkan penjumlahan vektor. Sebuah fungsi $$f:\mathbb{R}^n\rightarrow\mathbb{R}$$ disebut linear apabila memenuhi dua properti tersebut. Kedua properti tersebut adalah

- *Homogenitas*. Untuk sembarang vektor $$x$$ dan sembarang skalar $$\alpha$$, berlaku $$f(\alpha x)=\alpha f(x)$$
- *Additif*. Untuk sembarang vektor $$x$$ dan sembarang vektor $$y$$, berlaku $$f(x+y)=f(x)+f(y)$$

Prinsip homogenitas mengatakan bahwa scaling pada argumen vektor sama dengan *scaling* pada nilai fungsi, sedangkan prinsip additif mengatakan bahwa penjumlahan dua (atau lebih) argumen vektor sama dengan penjumlahan dua (atau lebih) nilai fungsi.

## 3. Representasi Perkalian Titik Fungsi Linear

Kita telah melihat bahwa sebuah fungsi yang merepresentasikan perkalian titik merupakan fungsi linear atau kombinasi linear. *Mafhum mukholafah*-nya, jika sebuah fungsi merupakan fungsi linear, maka ia bisa direpresentasikan sebagai perkalian titik antara argumen vektor-nya dan vektor bobot-nya. 

Kembali kita gunakan fungsi linear sebagaimana di (2), yakni $$f(\alpha x+\beta y)=\alpha f(x)+\beta f(y)$$. Karena $$f(x)$$ di sini linear, maka akan ada vektor $$a$$ sehingga $$f(x)=a^Tx$$. Bentuk $$a^Tx$$ inilah yang disebut sebagai representasi perkalian titik dari $$f$$. 

Ingat kembali pelajaran mengenai vektor identitas di catatan sebelumnya. Apabila argumen vektor $$x$$ diekspresikan menggunakan vektor identitas, yakni $$x=x_1e_1+...+x_ne_n$$, maka $$f(x)$$ dapat dinyatakan sebagai berikut,

$$\begin{split}
f(x)&=f(x_1e_1+...+x_ne_n)\\
&=x_1f(e_1)+...+x_nf(e_n)\\
&=a^Tx
\end{split}$$

dimana $$a=(f(e_1),f(e_2),...,f(e_n))$$. Jadi, bentuk umum representasi perkalian titik fungsi linear adalah sebagai berikut,

$$\begin{equation}
f(x)=x_1f(e_1)+x_2f(e_2)+...+x_nf(e_n)
\end{equation}$$

Contoh:

*Nilai rata-rata*. Nilai rata-rata dari sebuah vektor $$x$$ dengan $$n$$ elemen adalah

$$f(x)=(x_1+x_2+...+x_n)/n$$

dan biasa dinotasikan dengan $$\bar{x}$$. Bisa kita lihat bahwa nilai rata-rata sebuah vektor adalah fungsi linear. Sesuai prinsip di atas, fungsi ini bisa dinyatakan dengan $$\bar{x}=a^Tx$$ dengan

$$a=(1/n,...,1/n)=\mathbf{1}/n$$

*Nilai maksimum*. Nilai maksimum sebuah vektor $$x$$ dengan $$n$$ elemen ($$n\neq 1$$) adalah

$$f(x)=\max{(x_1,...,x_n)}$$

Dapatkah anda tebak ini fungsi linear atau bukan? 

## 4. Fungsi Affine

Fungsi linear yang terdapat tambahan konstanta dalam ekspresinya disebut sebagai **fungsi affine**. Sebuah fungsi $$f:\mathbb{R}^n\rightarrow\mathbb{R}$$ dikatakan sebagai fungsi affine <u>jika dan hanya jika</u> dapat diekspresikan dalam bentuk $$f(x)=a^Tx+b$$. $$b$$ adalah skalar dan terkadang disebut juga sebagai "offset". Dari sini bisa kita lihat bahwa fungsi affine merupakan bentuk khusus dari fungsi linear. Contoh fungsi affine adalah sebagai berikut,

$$f(x)=2+4x_1+5x_2-6x_3$$

Fungsi di atas adalah fungsi affine dengan $$a=(4,5,-6)$$ dan $$b=2$$.

Hampir mirip dengan fungsi linear secara umum, fungsi affine juga memenuhi prinsip superposisi tetapi dengan kriteria khusus,

$$f(\alpha x+\beta y)=\alpha f(x)+\beta f(y)$$

untuk semua vektor $$x$$ dan $$y$$ serta semua skalar $$\alpha$$ dan $$\beta$$ yang memenuhi $$\alpha+\beta=1$$. Jadi, untuk fungsi linear skalar $$\alpha$$ dan $$\beta$$ bisa bernilai berapa saja, sementara untuk fungsi affine jumlahan koefisien/bobot ini harus sama dengan 1. Pembuktiannya adalah sebagai berikut,

$$\begin{split}
f(\alpha x+\beta y)&=a^T(\alpha x+\beta y)+b\\
&=\alpha a^Tx+\beta a^Ty+(\alpha+\beta)b\\
&=\alpha(a^Tx+b)+\beta(a^Ty+b)\\
&=\alpha f(x)+\beta f(y)
\end{split}$$

Dapat dilihat bahwa persamaan superposisi $$f(\alpha x+\beta y)=\alpha f(x)+\beta f(y)$$ hanya bisa didapat apabila kita menetapkan $$\alpha+\beta=1$$ (lihat baris kedua). *Mafhum mukholafah*-nya, kalau kita diberi vektor $$x$$ dan $$y$$ serta skalar $$\alpha$$ dan $$\beta$$ dengan $$\alpha+\beta=1$$, tetapi $$f(\alpha x+\beta y)\neq\alpha f(x)+\beta f(y)$$, maka fungsi $$f$$ di sini bukan fungsi affine.

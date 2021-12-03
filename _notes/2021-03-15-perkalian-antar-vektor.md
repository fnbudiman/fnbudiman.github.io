---
layout: post
title: Perkalian Antar Vektor
collection: notes
---

Setelah sebelumnya kita membahas perkalian antara skalar dan vektor, kali ini kita berpindah ke perkalian antar vektor. Perkalian antar vektor disebut juga <b>perkalian dalam (<i>inner product</i>)</b>, <b>perkalian standar (<i>standard product</i>)</b>, atau <b>perkalian titik (<i>dot product</i>)</b>. Mari kita pelajari aturan main perkalian antar vektor ini dan kita lihat contoh-contohnya.

Misalkan kita punya dua vektor $$x$$ dan $$y$$. Perkalian titik antara $$x$$ dan $$y$$ dituliskan dengan beberapa notasi, yaitu $$x^Ty$$, $$\langle x,y\rangle$$, $$\langle x\vert y \rangle$$, $$(x,y)$$, dan $$x\cdot y$$. Kita akan gunakan penulisan yang pertama disebut, yaitu $$x^Ty$$. Apabila $$x$$ dan $$y$$ masing-masing memiliki $$n$$ elemen, $$x^Ty$$ dapat dijabarkan dalam persamaan skalar berikut,

$$x^Ty=x_1y_1+x_2y_2+...+x_ny_n$$

Huruf $$T$$ superscript pada $$x$$ di atas merepresentasikan operasi "transpose". Dalam konteks vektor ini, transpose adalah operasi pengubahan vektor dari vektor kolom menjadi vektor baris tanpa mengubah urutan elemen-elemennya. Sebagai contoh, kita akan melakukan operasi perkalian titik antara vektor $$(4,2,-5)$$ dan vektor $$(-1,3,7)$$. Penjabarannya adalah sebagai berikut,

$$\begin{split}
\begin{bmatrix}
4\\
2\\
-5\\
\end{bmatrix}^T
\begin{bmatrix}
-1\\
3\\
7\\
\end{bmatrix}
&=
\begin{bmatrix}
4 & 2 & -5\\
\end{bmatrix}
\begin{bmatrix}
-1\\
3\\
7\\
\end{bmatrix}\\
&=(4)(-1)+(2)(3)+(-5)(7)\\
&=-33
\end{split}$$

Perhatikan bahwa hasil perkalian titik antara dua vektor adalah skalar. Jangan sampai keliru ya 😐. 

Selanjutnya, sebagaimana operasi perkalian skalar-vektor, operasi perkalian titik antar vektor juga memiliki beberapa sifat. Misalkan kita punya tiga vektor $$x$$, $$y$$, dan $$z$$, serta sebuah skalar $$\alpha$$, sifat-sifat operasi perkalian dapat dijelaskan sebagai berikut,

- Sifat komutatif, yakni $$x^Ty=y^Tx$$
- Sifat asosiatif (melibatkan perkalian dengan skalar), yakni $$(\alpha x)^Ty=\alpha(x^Ty)$$, yang bisa juga ditulis $$\alpha x^Ty$$
- Sifat distributif, yakni $$(x+y)^Tz=x^Tz+y^Tz$$

Kombinasi dari sifat-sifat tersebut bisa menghasilkan sifat/identitas yang lain, misalnya

- $$x^T(\alpha y)=\alpha (x^Ty)$$ $$ $$
- $$x^T(y+\alpha z)=x^Ty+\alpha x^Tz$$ $$ $$
- $$(w+x)^T(y+z)=$$ $$w^Ty+w^Tz+x^Ty+x^Tz$$

Mari kita ambil satu contoh untuk membuktikan identitas yang disebut terakhir di atas. Misalnya kita punya empat vektor berikut,

$$w=
\begin{bmatrix}
1\\
2\\
3\\
\end{bmatrix},
x=
\begin{bmatrix}
2\\
3\\
4\\
\end{bmatrix},
y=
\begin{bmatrix}
3\\
4\\
5\\
\end{bmatrix},
z=
\begin{bmatrix}
4\\
5\\
6\\
\end{bmatrix}$$

Mari kita hitung $$(w+x)^T(y+z)$$ terlebih dahulu

$$\begin{split}
(w+x)^T(y+z)&=
\left(\begin{bmatrix}
1\\
2\\
3\\
\end{bmatrix}+
\begin{bmatrix}
2\\
3\\
4\\
\end{bmatrix}\right)^T
\left(\begin{bmatrix}
3\\
4\\
5\\
\end{bmatrix}+
\begin{bmatrix}
4\\
5\\
6\\
\end{bmatrix}\right)\\
&=
\begin{bmatrix}
3\\
5\\
7\\
\end{bmatrix}^T
\begin{bmatrix}
7\\
9\\
11\\
\end{bmatrix}\\
&=(3)(7)+(5)(9)+(7)(11)\\
&=143
\end{split}$$

Kemudian, mari hitung $$w^Ty+w^Tz+x^Ty+x^Tz$$,

$$\begin{split}
w^Ty+& w^Tz+x^Ty+x^Tz\\
&=
\begin{bmatrix}
1\\
2\\
3\\
\end{bmatrix}^T
\begin{bmatrix}
3\\
4\\
5\\
\end{bmatrix}
+
\begin{bmatrix}
1\\
2\\
3\\
\end{bmatrix}^T
\begin{bmatrix}
4\\
5\\
6\\
\end{bmatrix}
+
\begin{bmatrix}
2\\
3\\
4\\
\end{bmatrix}^T
\begin{bmatrix}
3\\
4\\
5\\
\end{bmatrix}
+
\begin{bmatrix}
2\\
3\\
4\\
\end{bmatrix}^T
\begin{bmatrix}
4\\
5\\
6\\
\end{bmatrix}\\
&=
26+32+38+47\\
&=143
\end{split}$$

Terbukti bukan kalau hasilnya sama. Dengan cara serupa, pembuktian sifat-sifat yang lain silakan bisa dicoba sendiri. Dan selalu ingat ya bahwa hasil dari operasi-operasi di atas adalah skalar.

*Next*, kita akan melihat bagaimana operasi perkalian titik yang melibatkan vektor-vektor spesial. Perhatikan poin-poin berikut,

- <u>Vektor unit</u>: $$e_i^Tx=x_i$$. Perkalian titik antara vektor $$x$$ dengan vektor unit ke-$$i$$ menghasilkan elemen ke-$$i$$ dari vektor $$x$$
- <u>Jumlahan</u>: $$\mathbf{1}^Tx=x_1+...+x_n$$. Perkalian titik antara vektor $$x$$ dengan vektor satu menghasilkan jumlahan dari elemen-elemen vektor $$x$$ itu sendiri
- <u>Rata-rata</u>: $$(\mathbf{1}/n)^Tx=(x_1+...+x_n)/n$$. Perkalian titik antara vektor $$x$$ dengan vektor $$(\mathbf{1}/n)$$ menghasilkan rata-rata (average) dari elemen-elemen vektor $$x$$. Nilai rata-rata dari elemen-elemen $$x$$ ini biasa dinotasikan dengan $$\mathbf{avg}(x)$$, atau kadang-kadang dengan huruf yunani $$\mu$$
- <u>Jumlahan kuadrat</u>: $$a^Ta=a_1^2+...+a_n^2$$. Perkalian titik antara vektor $$x$$ dengan dirinya sendiri menghasilkan jumlahan kuadrat (sum of squares) dari elemen-elemen vektor $$x$$ tersebut
- <u>Jumlahan selektif</u>. Misalkan $$y$$ adalah vektor yang elemen-nya hanya berupa angka 0 atau 1. Maka $$y^Tx$$ adalah jumlahan dari elemen-elemen vektor $$x$$ dimana $$y_i=1$$
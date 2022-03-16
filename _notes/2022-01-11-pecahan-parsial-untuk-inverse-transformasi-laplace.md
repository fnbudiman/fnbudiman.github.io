---
layout: post
title: Pecahan Parsial untuk Inverse Tranformasi Laplace
collection: notes
---

Dalam kuliah sistem kendali, salah satu konsep yang penting adalah mengenai inverse transformasi Laplace. Gunanya adalah untuk mengubah kembali fungsi dalam domain Laplace ke domain waktu. Nah, teknik yang sering dipakai untuk keperluan ini adalah teknik pecahan parsial (_partial fraction_). Kita akan belajar bagaimana menggunakan pecahan parsial ini untuk meng-handle dua contoh fungsi dengan karakteristik _pole_ yang berbeda.

### Contoh 1

Transformasikan fungsi berikut ke domain waktu!

$$\boxed{F(s)=\frac{2}{s^2+3s+2}}$$

Contoh pertama ini adalah contoh yang paling mudah karena sistem di atas memiliki _pole_ yang berbeda. Tahapan pengerjaannya adalah sebagai berikut.

1. Lakukan faktorisasi pada penyebut dari fungsi di atas, yaitu $$s^2+3s+2$$. Faktorisasi akan menghasilkan bentuk berikut.

    $$\begin{equation}F(s)=\frac{2}{(s+1)(s+2)}\end{equation}$$

2. 'Pisahkan' faktor-faktor pada penyebut, yaitu

    $$\begin{equation}F(s)=\frac{A}{s+1}+\frac{B}{s+2}\end{equation}$$

    Pemisahan menghasilkan dua bilangan yang belum diketahui. Kita sebut saja bilangan-bilangan tersebut $$A$$ dan $$B$$, sebagaimana yang tertulis di Persamaan (2).

3. 'Gabungkan' kembali Persamaan (2) namun dengan melibatkan $$A$$ dan $$B$$. Ingat kembali teknik "menyamakan penyebut" dalam operasi penjumlahan pecahan. Hasil penggabungan dengan teknik "menyamakan penyebut" tersebut adalah sebagai berikut.

    $$\begin{equation}F(s)=\frac{A(s+2)+B(s+1)}{(s+1)(s+2)}\end{equation}$$

4. Hitung $$A$$ dan $$B$$ dengan mensubstitusi nilai _pole_ sistem. Lihat Persamaan (1) dan (3) dan perhatikan bahwa kedua persamaan tersebut memiliki penyebut yang sama, yaitu $$(s+1)(s+2)$$. Oleh karenanya, kita dapatkan hubungan berikut.

    $$\begin{equation}A(s+2)+B(s+1)=2\end{equation}$$

    _Pole_ sistem (bisa dilihat dari Persamaan (1)) adalah -1 dan -2. Nilai-nilai ini yang akan kita substitusi ke Persamaan (4).

    $$\begin{split}s=-1 \hspace{10pt}\rightarrow \hspace{10pt} &A(-1+2)+B(-1+1)=2\\
    &A(1)+B(0)=2\\
    &\boxed{A=2}\end{split}$$

    $$\begin{split}s=-2 \hspace{10pt}\rightarrow \hspace{10pt} &A(-2+2)+B(-2+1)=2\\
    &A(0)+B(-1)=2\\
    &\boxed{B=-2}\end{split}$$

5. Substitusi nilai $$A$$ dan $$B$$ ke Persamaan (2) dan kemudian ubah ke domain waktu. Hasil substitusi adalah sebagai berikut.

    $$\begin{equation}F(s)=\frac{2}{s+1}+\frac{-2}{s+2}\end{equation}$$

    Persamaan (5) adalah bentuk yang siap ditransformasi ke domain waktu dengan mudah. Dengan mengasumsikan transformasi Laplace unilateral, hasil transformasinya adalah sebagai berikut.

    $$\boxed{f(t)=\left[2e^{-t}-2e^{-2t}\right]u(t)}$$

    Perhatikan bahwa fungsi step $$u(t)$$ ditambahkan untuk mengakomodir transformasi Laplace unilateral.

### Contoh 2

Transformasikan fungsi berikut ke domain waktu!

$$\boxed{F(s)=\frac{10}{s^2(s^2+3s+2)}}$$

Berbeda dengan fungsi di Contoh 1. Di Contoh 2 ini, kita perlu berhati-hati karena sistem yang diobservasi memiliki empat _pole_ dan dua diantaranya sama. Detail tahapan pengerjaannya adalah sebagai berikut.

1. Faktorisasi penyebut:

    $$\begin{equation}F(s)=\frac{5}{s^2(s+1)(s+2)}\end{equation}$$

2. 'Pemisahan' fungsi:

    $$\begin{equation}F(s)=\frac{A}{s^2}+\frac{B}{s}+\frac{C}{s+2}+\frac{D}{s+1}\end{equation}$$

    Perhatikan bahwa kita mempunyai empat bagian (bukan tiga) karena terdapat dua _pole_ (meskipun sama) yang terindikasi dari $$s^2$$. Ini sekaligus menjadi kaidah umum dalam pemisahan fungsi, yakni fungsi dengan $$n$$ _pole_ dipecah menjadi $$n$$ bagian.

3. Perhitungan nilai $$A, B, C, D$$.

    Dari Persamaan (6) dan (7), kita mempunyai hubungan berikut.

    $$\begin{equation}\frac{5}{s^2(s+1)(s+2)}=\frac{A}{s^2}+\frac{B}{s}+\frac{C}{s+2}+\frac{D}{s+1}\end{equation}$$

    Kita mulai dengan menghitung nilai $$A$$. Perhatikan bahwa $$A$$ mempunyai penyebut $$s^2$$. Kita perlu menghilangkan penyebut ini. Caranya adalah dengan mengalikan kedua sisi di Persamaan (8) dengan $$s$$ tersebut. Prosesnya adalah sebagai berikut.

    $$\begin{equation}
    \frac{5}{s^2(s+1)(s+2)}\times s^2=\left[\frac{A}{s^2}+\frac{B}{s}+\frac{C}{s+2}+\frac{D}{s+1}\right]\times s^2
    \end{equation}$$

    atau

    $$\begin{equation}
    \frac{5}{(s+1)(s+2)}=A+\frac{Bs^2}{s}+\frac{Cs^2}{s+2}+\frac{Ds^2}{s+1}
    \end{equation}$$

    Nilai $$A$$ didapatkan dengan substitusi _pole_ pertama, yakni $$s=0$$.

    $$\begin{split}
    A&=\left.\frac{5}{(s+1)(s+2)}\right\rvert_{s=0}\\
    &=\frac{5}{2}
    \end{split}$$

    Perhitungan $$B$$ kita lewati dulu karena tidak bisa menggunakan cara sebagaimana di (9). Dengan $$s=0$$, kita akan dapatkan $$B=\infty$$ (silakan dicoba sendiri). Nilai ini tentu tidak valid.

    Kita beralih ke perhitungan nilai $$C$$. Dengan proses sebagaimana di (9), kita mempunyai

    $$\begin{equation}
    \frac{5}{s^2(s+1)(s+2)}\times (s+2)=\left[\frac{A}{s^2}+\frac{B}{s}+\frac{C}{s+2}+\frac{D}{s+1}\right]\times (s+2)
    \end{equation}$$

    atau

    $$\begin{equation}
    \frac{5}{s^2(s+1)}=\frac{A(s+2)}{s^2}+\frac{B(s+2)}{s}+C+\frac{D(s+2)}{s+1}
    \end{equation}$$

    Dengan $$s=-2$$,

    $$\begin{split}
    C&=\left.\frac{5}{s^2(s+1)}\right\rvert_{s=-2}\\
    &=-\frac{5}{4}
    \end{split}$$

    Proses yang sama digunakan untuk menghitung $$D$$,

    $$\begin{equation}
    \frac{5}{s^2(s+1)(s+2)}\times (s+1)=\left[\frac{A}{s^2}+\frac{B}{s}+\frac{C}{s+2}+\frac{D}{s+1}\right]\times (s+1)
    \end{equation}$$

    atau

    $$\begin{equation}
    \frac{5}{s^2(s+2)}=\frac{A(s+1)}{s^2}+\frac{B(s+1)}{s}+\frac{C(s+1)}{s+2}+D
    \end{equation}$$

    Dengan $$s=-1$$,

    $$\begin{split}
    C&=\left.\frac{5}{s^2(s+2)}\right\rvert_{s=-1}\\
    &=5
    \end{split}$$

    $$A$$, $$C$$, dan $$D$$ telah diketahui, tersisa $$B$$. Untuk menghitung $$B$$, kembalikan/substitusi $$A$$, $$C$$, dan $$D$$ ke (8),

    $$\begin{equation}\frac{5}{s^2(s+1)(s+2)}=\frac{5/2}{s^2}+\frac{B}{s}+\frac{-5/4}{s+2}+\frac{5}{s+1}\end{equation}$$

    atau

    $$\begin{equation}\frac{5}{s^2(s+1)(s+2)}=\frac{(5/2)(s+1)(s+2)+Bs(s+1)(s+2)-(5/4)s^2(s+1)+5s^2(s+2)}{s^2(s+1)(s+2)}\end{equation}$$

    Proses selanjutnya bisa diringkas sebagai berikut.

    $$\begin{equation}\begin{split}
    &(5/2)(s+1)(s+2)+Bs(s+1)(s+2)-(5/4)s^2(s+1)+5s^2(s+2)=5\\
    &\iff 10(s+1)(s+2)+4Bs(s+1)(s+2)-5s^2(s+1)+20s^2(s+2)=20\\
    &\iff 10s^2+30s+20+4Bs^3+12Bs^2+8Bs-5s^3-5s^2+20s^3+40s^2=20\\
    &\iff (4B+15)s^3+(12B+45)s^2+(8B+30)s+20=20
    \end{split}\end{equation}$$

    Perhatikan bahwa bagian terakhir dari (17) bisa ditulis

    $$\begin{equation}
    (4B+15)s^3+(12B+45)s^2+(8B+30)s+20=0s^3+0s^2+0s+20
    \end{equation}$$

    yang dari situ kita dapatkan 3 persamaan yang identik, yaitu $$4B+15=0$$, $$12B+45=0$$, dan $$8B+30=0$$. Nilai $$B$$ dengan mudah kita hitung, yaitu

    $$B=-\frac{15}{4}$$

4. Substitusi nilai $$A, B, C, D$$ ke Persamaan (7):

    $$\begin{equation}F(s)=\frac{5/2}{s^2}+\frac{-15/4}{s}+\frac{-5/4}{s+2}+\frac{5}{s+1}\end{equation}$$

    Persamaan (19) dengan mudah ditransformasi ke domain waktu sebagai berikut.

    $$\boxed{f(t)=\left[\frac{5}{2}t-\frac{15}{4}-\frac{5}{4}e^{-2t}+5e^{-t}\right]u(t)}$$

Demikian, semoga bermanfaat.
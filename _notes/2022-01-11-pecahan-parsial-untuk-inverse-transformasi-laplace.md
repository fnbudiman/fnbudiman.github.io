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

    $$\begin{equation}F(s)=\frac{A}{s}+\frac{B}{s^2}+\frac{C}{s+2}+\frac{D}{s+1}\end{equation}$$

    Perhatikan bahwa kita mempunyai empat bagian (bukan tiga) karena terdapat dua _pole_ (meskipun sama) yang terindikasi dari $$s^2$$. Ini sekaligus menjadi kaidah umum dalam pemisahan fungsi, yakni fungsi dengan $$n$$ _pole_ dipecah menjadi $$n$$ bagian.

3. Perhitungan nilai $$A, B, C, D$$.

    Dari Persamaan (6) dan (7), kita mempunyai hubungan berikut.

    $$\begin{equation}\frac{5}{s^2(s+1)(s+2)}=\frac{A}{s}+\frac{B}{s^2}+\frac{C}{s+2}+\frac{D}{s+1}\end{equation}$$

    Karena fungsi yang diobservasi sedikit lebih rumit, kita akan menggunakan teknik yang sedikit berbeda dari yang kita gunakan di Contoh 1. Teknik ini bisa juga diaplikasikan pada fungsi di Contoh 1. Karena $$A$$ dan $$B$$ terasosiasi dengan penyebut yang menghasilkan dua _pole_ identik, kita akan menghitung $$C$$ dan $$D$$ terlebih dahulu.

    Untuk $$C$$, karena penyebutnya $$(s+2)$$, kita kalikan kedua sisi di Persamaan (8) dengan $$(s+2)$$ sehingga didapatkan bentuk berikut.

    $$\begin{equation}\frac{5}{s^2(s+1)}=\frac{A(s+2)}{s}+\frac{B(s+2)}{s^2}+C+\frac{D(s+2)}{s+1}\end{equation}$$

    Dengan substitusi nilai _pole_ $$s=-2$$ ke Persamaan (9), didapatkan $$\boxed{C=-\frac{5}{4}}$$.

    Untuk $$D$$, karena penyebutnya $$(s+1)$$, kita kalikan kedua sisi di Persamaan (8) dengan $$(s+1)$$ sehingga didapatkan bentuk berikut.

    $$\begin{equation}\frac{5}{s^2(s+2)}=\frac{A(s+1)}{s}+\frac{B(s+1)}{s^2}+\frac{C(s+1)}{s+2}+D\end{equation}$$

    Dengan substitusi nilai _pole_ $$s=-1$$ ke Persamaan (10), didapatkan $$\boxed{D=5}$$.

    Untuk $$A$$ dan $$B$$, kita tidak bisa langsung mengalikan kedua sisi dengan $$s$$ atau $$s^2$$ karena akan menimbulkan error di perhitungan (silakan dicoba sendiri). Yang bisa kita lakukan adalah mensubstitusikan dua nilai $$s$$ sembarang (selain nol) ke Persamaan (8). Di sini kita akan mengambil angka yang sederhana saja, yakni $$s=1$$ dan $$s=2$$. Substitusi keduanya serta substitusi $$C$$ dan $$D$$ ke Persamaan (8) menghasilkan

    $$\begin{equation}\begin{split}s=1 \hspace{10pt}\rightarrow \hspace{10pt} &\frac{5}{6}=\frac{A}{1}+\frac{B}{1}-\frac{5}{12}+\frac{5}{2}\\
    &A+B=-\frac{5}{4}\end{split}\end{equation}$$

    $$\begin{equation}\begin{split}s=2 \hspace{10pt}\rightarrow \hspace{10pt} &\frac{5}{48}=\frac{A}{2}+\frac{B}{4}-\frac{5}{16}+\frac{5}{3}\\
    &2A+B=-5\end{split}\end{equation}$$

    Kombinasi Persamaan (11) dan (12) menghasilkan $$\boxed{A=-\frac{15}{4}}$$ dan $$\boxed{B=\frac{5}{2}}$$.

4. Substitusi nilai $$A, B, C, D$$ ke Persamaan (7):

    $$\begin{equation}F(s)=-\frac{15/4}{s}+\frac{5/2}{s^2}-\frac{5/4}{s+2}+\frac{5}{s+1}\end{equation}$$

    Persamaan (13) dengan mudah ditransformasi ke domain waktu sebagai berikut.

    $$\boxed{f(t)=\left[-\frac{15}{4}+\frac{5}{2}t-\frac{5}{4}e^{-2t}+5e^{-t}\right]u(t)}$$

Demikian, semoga bermanfaat.
---
layout: post
title: Dekomposisi QR pada Matriks
collection: notes
---

Dalam aljabar linear, dekomposisi \\(QR\\) pada matriks merupakan salah satu konsep yang sangat penting. Salah satu penggunaannya adalah untuk fitting polinomial. Di tulisan ini akan dibahas salah satu contoh sederhana bagaimana menggunakannya.

## Soal

Sebagai contoh, misalnya kita mempunyai sepasang dataset, katakanlah \\(\mathbf{x}\\) dan \\(\mathbf{y}\\), sebagai berikut

$$\mathbf{x}=[0,1,2,3,4]$$

$$\mathbf{y}=[0,1,4,6,9]$$

(data didapatkan dari <a href="http://pfister.ee.duke.edu/courses/ece586/ex_proj_2008.pdf" target="_blank">sini</a>)

Diinginkan untuk menyusun *least square* fit menggunakan polinomial berderajat tiga (fungsi kubik).

## Penyelesaian

Dalam fitting polinomial menggunakan algoritma *least square*, koefisien-koefisien polinomial yang akan kita cari adalah nilai estimasi *least square* \\(\mathbf{x}_{ls}\\). Jadi, yang akan kita lakukan adalah mencari estimasi nilai \\(\mathbf{y}\\) menggunakan bentuk polinomial

$$y_{est}=x_{ls,1}+x_{ls,2}x+x_{ls,3}x^2+x_{ls,4}x^3$$

Langkah-langkah pengerjaannya adalah sebagai berikut:

### 1. Susun matriks \\(A\\)

Untuk \\(\mathbf{x}\in\mathbb{R}^m\\) dan derajat polinomial \\((n-1)\\), formula umum untuk matriks \\(A\\) adalah sebagai berikut,

$$A=\begin{bmatrix}x_1^0 & x_1^1 & \dots & x_1^{n-1}\\ x_2^0 & x_2^1 & \dots & x_2^{n-1}\\ \vdots & \vdots & \ddots & \vdots\\ x_m^0 & x_m^1 & \dots & x_m^{n-1}\end{bmatrix}$$

dimana \\(A\in\mathbb{R}^{m\times n}\\). Dengan menggunakan data \\(\mathbf{x}\\) di atas, matriks \\(A\\) kita adalah

$$A=\begin{bmatrix} 1 & 0 & 0 & 0\\ 1 & 1 & 1 & 1\\ 1 & 2 & 4 & 8\\ 1 & 3 & 9 & 27\\ 1 & 4 & 16 & 64\end{bmatrix}$$ 

## 2. Lakukan dekomposisi \\(QR\\) pada matriks \\(A\\)

Matriks \\(A\\) yang kita dapatkan di atas akan kita gunakan untuk menghitung $$\mathbf{x}_{ls}$$ dari persamaan $$\mathbf{y}=A\mathbf{x}_{ls}$$. Sebenanrnya cara yang paling mudah adalah dengan operasi inverse matriks: $$\mathbf{x}_{ls}=A^{-1}\mathbf{y}$$. Namun ini hanya berlaku apabila matriks $$A$$ adalah matriks persegi, sementara matriks $$A$$ kita bukanlah matriks persegi. Salah satu prosedur yang bisa dilakukan adalah dengan dekomposisi $$QR$$ pada matriks $$A$$, yaitu memfaktorkan matriks $$A$$ menjadi matriks $$Q$$ dan matriks $$R$$, 

$$A=QR$$

dimana $$Q\in\mathbb{R}^{m\times n}$$ dan $$R\in\mathbb{R}^{n\times n}$$. $$Q$$ adalah matriks ortonormal dan $$R$$ adalah matriks segitiga atas. 

Sebelum mencari matriks $$Q$$, mari kita nyatakan matriks $$A$$ dan $$Q$$ ke bentuk berikut,

$$\begin{split}A&=[\mathbf{a}_1 \,\, \mathbf{a}_2 \,\, \dots \,\, \mathbf{a}_n]\\
Q&=[\mathbf{q}_1 \,\, \mathbf{q}_2 \,\, \dots \,\, \mathbf{q}_n]\end{split}$$

Setelah itu, matriks $$Q$$ dicari menggunakan prosedur Gram-Schmidt. Dalam prosedur ini, perhitungan matriks $$Q$$ dilakukan melalui dua tahap, yaitu tahap ortogonalisasi dan tahap ortonormalisasi. Prosesnya adalah sebagai berikut,

#### Tahap ortogonalisasi

Di tahap ortogonalisasi, kita mendefinisikan matriks $$\hat{Q}$$ yang kolomnya dihitung sebagai berikut,

$$\hat{\mathbf{q}}_k=\mathbf{a}_k-\sum_{i=1}^{k-1}\frac{\langle\mathbf{a}_k,\hat{\mathbf{q}}_i\rangle}{||\hat{\mathbf{q}}_i||^2}\hat{\mathbf{q}}_i \hspace{20pt} \forall k\in [1,n]$$

$$\hat{\mathbf{q}}_k$$ adalah vektor-vektor yang ortogonal satu sama lain.

Untuk matriks $$A$$ kita, proses ortogonalisasinya sebagai berikut,

$$\begin{split} \hat{\mathbf{q}}_1&=\mathbf{a}_1=[1,1,1,1,1]\\ 
\hat{\mathbf{q}}_2&=\mathbf{a}_2-\frac{\langle\mathbf{a}_2,\hat{\mathbf{q}}_1\rangle}{||\hat{\mathbf{q}}_1||^2}\hat{\mathbf{q}}_1\\
&=[-2,-1,0,1,2]\\ 
\hat{\mathbf{q}}_3&=\mathbf{a}_3-\frac{\langle\mathbf{a}_3,\hat{\mathbf{q}}_1\rangle}{||\hat{\mathbf{q}}_1||^2}\hat{\mathbf{q}}_1-\frac{\langle\mathbf{a}_3,\hat{\mathbf{q}}_2\rangle}{||\hat{\mathbf{q}}_2||^2}\hat{\mathbf{q}}_2\\
&=[2,-1,-2,-1,2]\\ 
\hat{\mathbf{q}}_4&=\mathbf{a}_4-\frac{\langle\mathbf{a}_4,\hat{\mathbf{q}}_1\rangle}{||\hat{\mathbf{q}}_1||^2}\hat{\mathbf{q}}_1-\frac{\langle\mathbf{a}_4,\hat{\mathbf{q}}_2\rangle}{||\hat{\mathbf{q}}_2||^2}\hat{\mathbf{q}}_2-\frac{\langle\mathbf{a}_4,\hat{\mathbf{q}}_3\rangle}{||\hat{\mathbf{q}}_3||^2}\hat{\mathbf{q}}_3\\
&=[-1.2,2.4,0,-2.4,1.2] \end{split}$$

#### Tahap ortonormalisasi

Tahap ortonormalisasi dilakukan dengan membagi $$\hat{\mathbf{q}}_k$$ dengan panjang/norm-nya. Secara matematis,

$$\mathbf{q}_k=\frac{\hat{\mathbf{q}}_k}{||\hat{\mathbf{q}}_k||} \hspace{20pt} \forall k\in [1,n]$$

Maka vektor $$\mathbf{q}_k$$ merupakan vektor-vektor yang saling ortonormal satu sama lain. Untuk matriks $$A$$ kita, perhitungannya adalah sebagai berikut,

$$\begin{split} \mathbf{q}_1&=\frac{\hat{\mathbf{q}}_1}{||\hat{\mathbf{q}}_1||}\\
&=\frac{[1,1,1,1,1]}{\sqrt{5}}\\
&=[0.4472,0.4472,0.4472,0.4472,0.4472]\\  
\mathbf{q}_2&=\frac{\hat{\mathbf{q}}_2}{||\hat{\mathbf{q}}_2||}\\
&=\frac{[-2,-1,0,1,2]}{\sqrt{10}}\\
&=[-0.6325,-0.3162,0,0.3162,0.6325]\\ 
\mathbf{q}_3&=\frac{\hat{\mathbf{q}}_3}{||\hat{\mathbf{q}}_3||}\\
&=\frac{[[2,-1,-2,-1,2]}{\sqrt{14}}\\
&=[0.5345,-0.2673,-0.5345,-0.2673,0.5345]\\ 
\mathbf{q}_4&=\frac{\hat{\mathbf{q}}_4}{||\hat{\mathbf{q}}_4||}\\
&=\frac{[-1.2,2.4,0,-2.4,1.2]}{3.7947}\\
&=[-0.3162,0.6325,0,-0.6325,0.3162] \end{split}$$

Setelah mendapatkan matriks $$Q$$, langkah selanjutnya adalah menghitung matriks $$R$$. Formulanya sangat simpel, yaitu

$$R=Q^TA$$

Maka, dengan data matriks $$A$$ and $$Q$$ di atas didapatkan matriks $$R$$ sebagai berikut

$$R=\begin{bmatrix} 2.2361 & 4.4721 & 13.4164 & 44.7214\\ 0 & 3.1623 & 12.6491 & 48.6991\\ 0 & 0 & 3.7417 & 22.4499\\ 0 & 0 & 0 & 3.7947 \end{bmatrix}$$

## 3. Hitung nilai estimasi *least square* $$\mathbf{x}_{ls}$$

Estimasi least square $$\mathbf{x}_{ls}$$ dihitung sebagai berikut

$$\mathbf{x}_{ls}=R^{-1}Q^Ty$$

Menggunakan data matriks $$Q$$ dan $$R$$ yang telah kita dapatkan sebelumnya, nilai $$\mathbf{x}_{ls}$$ adalah

$$\mathbf{x}_{ls}=[-0.0714,0.7262,0.7143,-0.0833]$$

Sehingga persamaan polinomial untuk soal yang diberikan di atas adalah sebagai berikut,

$$y_{est}=-0.0714+0.7262x+0.7143x^2-0.0833x^3$$
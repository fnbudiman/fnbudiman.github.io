---
layout: post_blog
title: Properti dan Pasangan Transformasi Fourier
categories: [Science and Technical]
tags: [aljabar_linear]
---

Tabel properti:

|          Properti         |                      $$\boldsymbol{f(t)}$$                      |                       $$\boldsymbol{F(\omega)}$$                       |
|:-------------------------:|:--------------------------------------------------:|:---------------------------------------------------------:|
| Linearity                 | $$a_1f_1(t)+a_2f_2(t)$$                            | $$a_1F_1(\omega)+a_2F_2(\omega)$$                         |
| Scaling                   | $$f(at)$$                                          | $$\frac{1}{\|a\|}f\left(\frac{\omega}{a}\right)$$         |
| Time shift                | $$f(t-a)$$                                         | $$e^{-j\omega a}F(\omega)$$                               |
| Frequency shift           | $$e^{j\omega_0 t}f(t)$$                            | $$F(\omega-\omega_0)$$                                    |
| Modulation                | $$\cos(\omega_0 t)f(t)$$                           | $$\frac{1}{2}[F(\omega+\omega_0)+F(\omega-\omega_0)]$$    |
| Time differentiation      | $$\frac{df}{dt}$$<br/><br/> $$\frac{d^n f}{dt^n}$$ | $$j\omega F(\omega)$$<br/><br/> $$(j\omega)^n F(\omega)$$ |
| Time integration          | $$\int_{-\infty}^{t}f(t)\,d(t)$$              | $$\frac{F(\omega)}{j\omega}+\pi F(0)\delta(\omega)$$      |
| Frequency differentiation | $$t^nf(t)$$                                        | $$(j)^n\frac{d^n}{d\omega ^n}F(\omega)$$                  |
| Reversal                  | $$f(-t)$$                                          | $$F(-\omega)$$ or $$F^*(\omega)$$                         |
| Duality                   | $$F(t)$$                                           | $$2\pi f(-\omega)$$                                       |
| Convolution in $$t$$      | $$f_1(t)*f_2(t)$$                                  | $$F_1(\omega)F_2(\omega)$$                                |
| Convolution in $$\omega$$ | $$f_1(t)f_2(t)$$                                   | $$\frac{1}{2\pi}F_1(\omega)*F_2(\omega)$$                 |

Tabel pasangan:

|       $$\boldsymbol{f(t)}$$      |                 $$\boldsymbol{F(\omega)}$$                 |
|:--------------------------------:|:----------------------------------------------------------:|
|          $$\delta (t)$$          |                            $$1$$                           |
|               $$1$$              |                   $$2\pi\delta(\omega)$$                   |
|             $$u(t)$$             |           $$\pi\delta(\omega)+\frac{1}{j\omega}$$          |
|      $$u(t+\tau)-u(t-\tau)$$     |             $$2\frac{\sin \omega\tau}{\omega}$$            |
|             $$\|t\|$$            |                  $$\frac{-2}{\omega ^2}$$                  |
|         $$\text{sgn}(t)$$        |                    $$\frac{2}{j\omega}$$                   |
|          $$e^{-at}u(t)$$         |                   $$\frac{1}{a+j\omega}$$                  |
|          $$e^{at}u(-t)$$         |                   $$\frac{1}{a-j\omega}$$                  |
|        $$t^n e^{-at}u(t)$$       |              $$\frac{n!}{(a+j\omega)^{n+1}}$$              |
|          $$e^{-a\|t\|}$$         |                $$\frac{2a}{a^2+\omega ^2}$$                |
|        $$e^{j\omega_0 t}$$       |              $$2\pi\delta (\omega-\omega_0)$$              |
|        $$\sin \omega_0 t$$       | $$j\pi [\delta(\omega+\omega_0)-\delta(\omega-\omega_0)]$$ |
|        $$\cos \omega_0 t$$       |  $$\pi [\delta(\omega+\omega_0)+\delta(\omega-\omega_0)]$$ |
| $$e^{-at}\sin \omega_0 t\,u(t)$$ |       $$\frac{\omega_0}{(a+j\omega)^2 +\omega_0^2}$$       |
| $$e^{-at}\cos \omega_0 t\,u(t)$$ |       $$\frac{a+j\omega}{(a+j\omega)^2 +\omega_0^2}$$      |
## Introduction

The aim of our project is to make end to end simulation of Direct Sequence Spread Spectrum (DSSS) technique. It’s a technique that message signal is multiplied by a pseudo-random sequence to spread message bandwidth so energy of message signal expand a wider spectrum, and it appears as noise. The motivation of DSSS technique comes from channel-capacity theorem. It says that we can have good communication performance by increasing bandwidth even when signal-to-noise power is low. [1] DSSS increases transmit signal bandwidth to remove intersymbol interference (ISI) and narrowband interference. It provides security of transmission because receiver must know pseudo-random sequence to get transmitted data signal. Otherwise, receiver can’t detect original message signal, and it only sees transmitted signal as a noise. This property of DSSS technique make it suitable to use for military communication systems. DSSS also enables to usage of a bandwidth by multiple users because each user multiply its message signal by different pseudo-random sequence, and a receiver gets its message signal if it has transmitter pseudo-random sequence. The process of DSSS is shown below.  
![](https://github.com/mahmut-aksakalli/DirectSequenceSpreadSpectrum/blob/master/images/1.png)

<p align="center"><b>Figure 1:</b> Block diagram of Spread Spectrum System [2]</p>

## Experimental Work
In our project, end to end simulation of DSSS modulation started with generation of message signal at transmitter. We generated 8 bits message signal for better understanding of given figures below. Each bit has 0.1 seconds bit duration. Then, we generated pseudo-random code that has 4 times higher frequency than message signal. This means that each message bit coded by 4 randomly generated bit at DSSS signal. To represent binary data, we used non-return-to-zero (NRZ) line code scheme because we chose BPSK modulation to transmit our signal. BPSK modulation has 180 degree phase shift between carriers of binary 0 and 1 so binary-1 represented as 1 while binary-0 represented as -1. We obtained DSSS signal with multiplying message signal and pseudo-random code. The receiver must be aware of this pseudo-random code. Otherwise, it can’t get transmitted message signal, and transmitted signal appears as a noise at receiver. Figure 2 shows generated 8 bits message signal, pseudo-random code and modulated DSSS signal.
![](https://github.com/mahmut-aksakalli/DirectSequenceSpreadSpectrum/blob/master/images/1x.png)

<p align="center"><b>Figure 2:</b>Message, pseudo-random code and DSSS modulated signal</p>

Channel-capacity theorem says that increasing bandwidth improves error performance of communication even if SNR is low. DSSS modulation uses advantage of this theorem so message spectrum spread over higher bandwidth while message power decreases noise level. We can observe effects of DSSS modulation at frequency spectrum. Figure 3 shows frequency spectrum of 8 bits message signal, pseudo-random code and modulated DSSS signal. We observed that bandwidth of message expanded, and power of message spread over higher bandwidth than original message signal.  
![](https://github.com/mahmut-aksakalli/DirectSequenceSpreadSpectrum/blob/master/images/2.png)

<p align="center"><b>Figure 3:</b>Frequency Spectrums</p>

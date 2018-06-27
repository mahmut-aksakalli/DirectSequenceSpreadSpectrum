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

Final step of DSSS modulation at transmitter is multiplying DSSS signal with carrier of BPSK. We handled phase difference between carriers of binary-0 and bnary-1 using non-return-to-zero coding so we just multiplied DSSS signal with a carrier that has 100 Hz frequency. We analyzed effects of noise in performance evaluation step so we didn’t add any noise at channel. At receiver, we multiplied received signal with pseudo-random code. Then, we multiplied encoded signal with carrier to demodulate signal, and send it to decision device. The critical issue at this point is that the receiver must have same pseudo-random code with transmitter otherwise, it can’t reach original message. This feature of DSSS modulation makes it suitable for secure communication. Non-authorized listeners can’t decode message because they don’t have pseudo-random code. Last plot at Figure 4 shows received message when receiver uses different pseudo-random code than transmitter. It’s obvious that receiver can’t decode original message.

 ![](https://github.com/mahmut-aksakalli/DirectSequenceSpreadSpectrum/blob/master/images/3.png)
<p align="center"><b>Figure 4:</b>Original Message and results with true and wrong key at receiver</p>

Decision device integrates signal over a bit duration intervals, and determine binary value of received signal using a threshold value between binary-0 and binary-1. The result of decision device is shown above in Figure 4.

## Results

After we obtain the message signal at receiver with zero error rate, we first tested DSSS modulation with Additive White Gaussian Noise. Results are obtained in terms of Bit Error Rate (BER).  BER is nothing but a ratio of number of error bits and total number of bits transmitted during a specific period. While SNR value decreases, we checked BER and analyzed. We expected to get good BER because DSSS modulation is known for its higher resistance to noise. We repeated each calculation 1000 times and got average value. As a result, we obtained Monte Carlo analyses of BER with different SNR values. Figure5 shows BER vs SNR plot while message signal has length of 100 bits. 

 ![](https://github.com/mahmut-aksakalli/DirectSequenceSpreadSpectrum/blob/master/images/6.png)
<p align="center"><b>Figure 5:</b>Additive White Gaussian Noise performance</p>

It is easy to see that the more pseudo-number bits using, the better BER results obtaining. While SNR value is under -30 dB, BER approaches its max value 0.5. Theoretical values are marked with “x” on the plot.

Next, we analyzed DSSS modulation performance with fading channel effects. In wireless communication channel, there are multiple paths between transmitter and receiver and it has reflective effect on transferred signal. Such multipath fading effect result with receiving signal and its delated versions.  Beside, signal is being exposed to scattering on a local scale in each path. Modeling such channel effect differs according to different multipath propagation scenarios. We used Rayleigh and Rician models for evaluating performance. 

In Rayleigh fading channel model there are one or more major reflected paths from transmitter to receiver. BER vs SNR plot of DSSS is given below while signal is transmitted through Rayleigh fading channel.

 ![](https://github.com/mahmut-aksakalli/DirectSequenceSpreadSpectrum/blob/master/images/7.png)
<p align="center"><b>Figure 6:</b>Rayleigh fading channel performance</p>

 Rician fading channel model is similar to Rayleigh, except it has direct line-of-sight path in addition. That is why, we expected better result compared to Rayleigh fading channel. BER vs SNR plot of DSSS is given below while signal is transmitted through Rician fading channel.
 
 ![](https://github.com/mahmut-aksakalli/DirectSequenceSpreadSpectrum/blob/master/images/8.png)
<p align="center"><b>Figure 7:</b>Rician fading channel performance</p>

 ![](https://github.com/mahmut-aksakalli/DirectSequenceSpreadSpectrum/blob/master/images/9.png)
<p align="center"><b>Figure 8:</b>Performance evaluation for all considered situations</p>

In the last plot, all of three conditions plotted in same graph while each message bit represented by 3 pseudo-random numbers. 

## Conclusion

In this project we work on end to end simulation of DSSS modulation. We used message signal modulated by BPSK modulation technique. Every message bit represented by different number of pseudo-number code for performance evaluation to see its effect clearly. We multiplied message signal and randomly generated pseudo-random sequence and obtained signal with spread spectrum. Because bandwidth increased, its resistance became strong against noise or channel fading effect. First we assumed that we transmitted and received signal without any channel effect. We demodulated received signal and obtained message signal. At the last step, we analyzed BER vs SNR plots by considering different situations which are Additive White Gaussian Noise, Rayleigh fading channel and Rician fading channel effects respectively. We repeated entire process 1000 times to draw Monte Carlo simulation distribution plots. While we increased number of pseudo-random code, we obtained better BER results. On the other hand, our modulation has higher resistance against Additive White Gaussian Noise and lower resistance against Rayleigh fading channel compared to others as expected. 

### References
- https://people.cs.clemson.edu/~westall/851/spread-spectrum.pdf

- A. Goldsmith, Wireless Communication. Stanford University Press, 2004. (p341)

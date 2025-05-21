# MODULATION:
Modulation means a change. In communication engineering modulation is a process of changing some
characteristics of a carrier signal in accordance with the instantaneous value of a message signal. A carrier signal is
a high frequency high powered periodic signal used to carry a low frequency low powered message signal to a far
point. A message signal or modulating signal is a low frequency low powered signal which does not have the
capability to propagate to a far point alone. Now during modulation some characteristics like phase, frequency,
amplitude etc. of a carrier wave changes so as to generate a new signal which has the capability of movement or
propagate to a larger distance. This newly generated signal is known as modulated signal which has the property
that it can carry the information of message signal within it.

## Need of Modulation
In modern communication most of the communication system needs to transmit a low frequency message signal
to a large distance, very quickly, without any interference with utmost security. For this modulation plays an
important role in designing of a system and achieving some requirements.
The following are the major points for which modulation is essential, those are

1. Practicality of Antenna
2. Reduction of Interference
3. Reduction of Noise
4. Multiplexing

## Practicality of Antenna
In modern wireless communication, antennas play a crucial role in transmitting modulated signals as electromagnetic (radio) waves through space. At the transmitter, the antenna converts electrical signals into electromagnetic waves, and at the receiver, it performs the reverse.

The antenna's size depends on the signal's frequency and wavelength—longer wavelengths (lower frequencies) require larger antennas, with the basic length being λ/4. Transmitting low-frequency signals directly would need large, costly antennas that are hard to install.

To overcome this, modulation is used to shift the signal to a higher frequency, allowing the use of smaller, more practical antennas.

## Reduction of Interference
Interference is the process of mixing of two or more number of signals among themselves. In wireless
communication when a signal propagates through open space, there is always a probability of interference with
external signals. If a message signal which is generally comes under audio frequency range is transmitted through
an open space then it can easily be attenuated when interfered by external signal. By modulation, frequency
translation of audio frequency message signal occurs from low band to a high band so the modulated signal can not
be easily interfered or affected by the external signals.

## Reduction of Noise
Noise is the unwanted signal when intermix with the transmitted signal the power level of the transmitted signal
gets attenuated. In open space communication the mixing of unwanted noise is maximum in probability so the
probability of loss of transmitted signal is also high.
To avoid such probability the power level of the transmitted signal must be kept as high as possible. So incase of
transmitting modulated signal in place of low frequency message signal the probability of loss of power can be
minimise.

## Multiplexing
It is a phenomenon of transmitting more than one number of signal simultaneously at a time. But if we transmit
multiple message signal simultaneously without modulation then there will be the interference of all the Signals
and any low frequency message signal may get lost. Now when a message signal is modulated with a carrier signal
an envelope forms which secures the message within it. So if different message signals modulates with different
carriers then they will attain different envelopes. After which if the signals will be transmitted simultaneously then
there will be no interference.

## Classification of Modulation
The process of modulation can be classified according to the type of message signal or modulating signal used
along with the type of carrier signal used.

## Tree of modulation:

![image](https://github.com/user-attachments/assets/2aad773f-e43b-439d-928e-d1497bee5159)

Modulation can be classified into Analogue Modulation and Digital Modulation in terms of message signal used.
Similarly modulation can be classified into Analogue Modulation and Pulse Modulation in terms of the carrier
signal used.

## Analogue Modulation or Continuous Wave Modulation
It is the category of modulation in which both the message signal and carrier signal are analog in nature.Here
message signal is analog in nature which changes some characteristics like amplitude, frequency and phase of an
analogue carrier signal. Hence an analogue modulation can be classified into Amplitude Modulation, Frequency
Modulation and Phase Modulation. The amplitude modulation is called as Linear Modulation. Whereas the
frequency modulation and phase modulation combinely called as Angle Modulation.

## Amplitude Modulation
It is the process in which the amplitude of a sinusoidal carrier signal changes in accordance with the instantaneous
value of message signal on modulating signal.

## Frequency Modulation
It is the process in which the frequency of sinusoidal carrier wave or carrier signal changes in accordance with the
instantaneous value of a message or modulating signal.

## Phase Modulation
It is the process in which the phase angle of sinusoidal carrier wave changes in accordance with the instantaneous
value of a message or modulating signal.

## Pulse Modulation or Pulse Wave Modulation
It is the category of modulation in which the message signal that used may be of analog type or Digital type but
the carrier signal that used is always of digital type or train of pulses. When the message signal is of analog type
along with digital type carrier signal then the pulse modulation is called as Analogue Pulse Modulation. Similarly
when message signal is of digital type along with digital type carrier signal then the pulse modulation is called as
Digital Pulse Modulation. Depending upon three characteristics of digital type or pulse type carrier signal the
analogue pulse modulation is of three types those are:
1. Pulse Amplitude Modulation (PAM)
2. Pulse Width Modulation (PWM)
3. Pulse Position Modulation (PPM

## Pulse Amplitude Modulation (PAM)
It is the process in which the amplitude of rectangular pulses varies in accordance with the instantaneous value of
sinusoidal signal or modulating signal.

## Pulse Width Modulation (PWM)
It is the process in which the width of rectangular pulses varies in accordance with the instantaneous value of a
sinusoidal message or modulating signal.

## Pulse Position Modulation (PPM)
It is the process in which the position of the pulses or gap between the pulses varies in accordance with the
instantaneous value of a sinusoidal message or modulating signal.

## Pulse Code Modulation
It is the process in which a digital type carrier signal changes in accordance with a digital form or binary form of
sinusoidal message signal or modulating signal.

## Digital Modulation
It is the category of modulation in which the message signal is digital in nature where as a carrier signal is analogue
in nature. Depending upon the change in amplitude, phase and frequency of analog carrier signal digital modulation
is of three types, those are

1. Amplitude Shift Keying
2. Phase Shift Keying
3. Frequency Shift Keying

## Amplitude Shift Keying
It is the process in which the amplitude of sinusoidal carrier wave changes in accordance with the digital message
signal which is in the form of sequence of binary bits.

## Phase Shift Keying
It is the process in which the phase of a sinusoidal carrier changes in accordance with the digital message signal
which is in the form of a sequence of binary bits.

## Frequency Shift Keying
It is the process in which the frequency of a sinusoidal carrier changes in accordance with the digital message signal
which is in the form of a sequence of binary bits.

# Amplitude Modulation
A continuous-wave goes on continuously without any intervals and it is the baseband message signal, which contains the information. This wave has to be modulated.

According to the standard definition, The amplitude of the carrier signal varies in accordance with the instantaneous amplitude of the modulating signal. Which means, the amplitude of the carrier signal containing no information varies as per the amplitude of the signal containing information, at each instant. This can be well explained by the following figures.

![image](https://github.com/user-attachments/assets/ccac4efe-9aee-455c-9d4f-a886fdf56e65)

The first figure shows the modulating wave, which is the message signal. The next one is the carrier wave, which is a high frequency signal and contains no information. While, the last one is the resultant modulated wave.

It can be observed that the positive and negative peaks of the carrier wave, are interconnected with an imaginary line. This line helps recreating the exact shape of the modulating signal. This imaginary line on the carrier wave is called as Envelope. It is the same as that of the message signal.

## Mathematical Expressions
Following are the mathematical expressions for these waves.

Time-domain Representation of the Waves
Let the modulating signal be,

m(t)=Amcos(2πfmt)

and the carrier signal be,

c(t)=Accos(2πfct)

Where,
Am and Ac are the amplitude of the modulating signal and the carrier signal respectively.
fm and fc are the frequency of the modulating signal and the carrier signal respectively.

Then, the equation of Amplitude Modulated wave will be

s(t)=[Ac+Amcos(2πfmt)]cos(2πfct)                   (Equation 1)

## Modulation Index
A carrier wave, after being modulated, if the modulated level is calculated, then such an attempt is called as Modulation Index or Modulation Depth. It states the level of modulation that a carrier wave undergoes.

Rearrange the Equation 1 as below.

s(t)=Ac[1+(AmAc)cos(2πfmt)]cos(2πfct)

⇒s(t)=Ac[1+μcos(2πfmt)]cos(2πfct)                 (Equation 2)

Where, μ is Modulation index and it is equal to the ratio of Am and Ac. Mathematically, we can write it as

μ=Am/Ac                                             (Equation 3)

Hence, we can calculate the value of modulation index by using the above formula, when the amplitudes of the message and carrier signals are known.

Now, let us derive one more formula for Modulation index by considering Equation 1. We can use this formula for calculating modulation index value, when the maximum and minimum amplitudes of the modulated wave are known.

Let Amax and Amin be the maximum and minimum amplitudes of the modulated wave.
We will get the maximum amplitude of the modulated wave, when cos(2πfmt) is 1.

⇒Amax=Ac+Am                                        (Equation 4)

![image](https://github.com/user-attachments/assets/f41d01e2-b667-411c-808f-430cd65ab216)

Therefore, Equation 3 and Equation 8 are the two formulas for Modulation index. The modulation index or modulation depth is often denoted in percentage called as Percentage of Modulation. We will get the percentage of modulation, just by multiplying the modulation index value with 100.

For a perfect modulation, the value of modulation index should be 1, which implies the percentage of modulation should be 100%.

For instance, if this value is less than 1, i.e., the modulation index is 0.5, then the modulated output would look like the following figure. It is called as Under-modulation. Such a wave is called as an under-modulated wave

![image](https://github.com/user-attachments/assets/cb2d4523-8f0a-4943-9968-8fe051fa689f)

If the value of the modulation index is greater than 1, i.e., 1.5 or so, then the wave will be an over-modulated wave. It would look like the following figure.

![image](https://github.com/user-attachments/assets/5730760f-d349-4e50-8574-166b136f7731)

As the value of the modulation index increases, the carrier experiences a 180o phase reversal, which causes additional sidebands and hence, the wave gets distorted. Such an over-modulated wave causes interference, which cannot be eliminated.

## Bandwidth of AM Wave

![image](https://github.com/user-attachments/assets/3c94a231-c933-4eb2-bca3-0a4d269d2c55)

## Power Calculations of AM Wave

![image](https://github.com/user-attachments/assets/c594606d-013b-4500-817e-8c40deceea52)

![image](https://github.com/user-attachments/assets/877b9555-e73c-4aa8-b6b2-85ed1b568475)

We can use the above formula to calculate the power of AM wave, when the carrier power and the modulation index are known.

If the modulation index μ=1 then the power of AM wave is equal to 1.5 times the carrier power. So, the power required for transmitting an AM wave is 1.5 times the carrier power for a perfect modulation.

# AM Modulator

## Square Law Modulator

![image](https://github.com/user-attachments/assets/daece5a5-0188-4b04-b5d4-8df86c7ab39f)

Let the modulating and carrier signals be denoted as m(t) and Acos(2πfct) respectively. These two signals are applied as inputs to the summer (adder) block. This summer block produces an output, which is the addition of the modulating and the carrier signal. Mathematically, we can write it as

![image](https://github.com/user-attachments/assets/df7d8fff-7f9f-4890-a17e-f4b042591501)

## Square Law Demodulator
Square law demodulator is used to demodulate low level AM wave. Following is the block diagram of thesquare law demodulator.

![image](https://github.com/user-attachments/assets/698d960a-2462-4c27-9304-839b80998550)

![image](https://github.com/user-attachments/assets/677acba7-cac7-47bf-abe7-af91b97adbb4)

## Envelope Detector
Envelope detector is used to detect (demodulate) high level AM wave. Following is the block diagram of the envelope detector.

![image](https://github.com/user-attachments/assets/d1d15432-2565-484d-ad2a-125f67caa830)

This envelope detector consists of a diode and low pass filter. Here, the diode is the main detecting element. Hence, the envelope detector is also called as the diode detector. The low pass filter contains a parallel combination of the resistor and the capacitor.

The AM wave s(t) is applied as an input to this detector.

We know the standard form of AM wave is

![image](https://github.com/user-attachments/assets/ced7a63b-f9d0-49b0-a92b-632246139fb4)

In the positive half cycle of AM wave, the diode conducts and the capacitor charges to the peak value of AM wave. When the value of AM wave is less than this value, the diode will be reverse biased. Thus, the capacitor will discharge through resistor R till the next positive half cycle of AM wave. When the value of AM wave is greater than the capacitor voltage, the diode conducts and the process will be repeated.

We should select the component values in such a way that the capacitor charges very quickly and discharges very slowly. As a result, we will get the capacitor voltage waveform same as that of the envelope of AM wave, which is almost similar to the modulating signal.

# DSBSC Modulation
In the process of Amplitude Modulation, the modulated wave consists of the carrier wave and two sidebands. The modulated wave has the information only in the sidebands. Sideband is nothing but a band of frequencies, containing power, which are the lower and higher frequencies of the carrier frequency.

The transmission of a signal, which contains a carrier along with two sidebands can be termed as Double Sideband Full Carrier system or simply DSBFC. It is plotted as shown in the following figure.

![image](https://github.com/user-attachments/assets/e8bb8af5-b2e6-448e-bbca-7b18357d9a2c)

However, such a transmission is inefficient. Because, two-thirds of the power is being wasted in the carrier, which carries no information.

If this carrier is suppressed and the saved power is distributed to the two sidebands, then such a process is called as Double Sideband Suppressed Carrier system or simply DSBSC. It is plotted as shown in the following figure.

![image](https://github.com/user-attachments/assets/066eb91f-93b6-4591-ae93-ed6ec8bb6d59)

**Mathematical Expressions**

![image](https://github.com/user-attachments/assets/c036198c-508b-412b-8ef8-e5bcb731a948)

## Bandwidth of DSBSC Wave

![image](https://github.com/user-attachments/assets/2a800460-7033-4188-80e8-885e6f5dd5fb)

## Power Calculations of DSBSC Wave

![image](https://github.com/user-attachments/assets/923fe6bc-bb42-43c3-9867-ce16045d0387)

## Ring Modulator

![image](https://github.com/user-attachments/assets/bae27728-efb0-425b-8d9a-ff3b2b92dd5a)

In this diagram, the four diodes D1, D2, D3 and D4 are connected in the ring structure. Hence, this modulator is called as the ring modulator. Two center tapped transformers are used in this diagram. The message signal m(t) is applied to the input transformer. Whereas, the carrier signals c(t) is applied between the two center tapped transformers.

For positive half cycle of the carrier signal, the diodes D1 and D3 are switched ON and the other two diodes D2 and D4 are switched OFF. In this case, the message signal is multiplied by +1.

For negative half cycle of the carrier signal, the diodes D2 and D4 are switched ON and the other two diodes D1 and D3 are switched OFF. In this case, the message signal is multiplied by -1. This results in 1800 phase shift in the resulting DSBSC wave.

From the above analysis, we can say that the four diodes D1, D2, D3 and D4 are controlled by the carrier signal. If the carrier is a square wave, then the Fourier series representation of c(t) is represented as

![image](https://github.com/user-attachments/assets/cccf5ecd-c634-49c7-a642-315780e9fc75)

## DSBSC Demodulators
The process of extracting an original message signal from DSBSC wave is known as detection or demodulation of DSBSC. The following demodulators (detectors) are used for demodulating DSBSC wave.

1. Coherent Detector
2. Costas Loop

## Coherent Detector
Here, the same carrier signal (which is used for generating DSBSC signal) is used to detect the message signal. Hence, this process of detection is called as coherent or synchronous detection. Following is the block diagram of the coherent detector.

![image](https://github.com/user-attachments/assets/3a5e8ec8-77a1-46fe-b849-be39c38b17c2)

In this process, the message signal can be extracted from DSBSC wave by multiplying it with a carrier, having the same frequency and the phase of the carrier used in DSBSC modulation. The resulting signal is then passed through a Low Pass Filter. Output of this filter is the desired message signal.

Let the DSBSC wave be

![image](https://github.com/user-attachments/assets/168d5d9c-90e1-4328-9881-ede6809e25c8)

## Costas Loop
Costas loop is used to make both the carrier signal (used for DSBSC modulation) and the locally generated signal in phase. Following is the block diagram of Costas loop.

![image](https://github.com/user-attachments/assets/2c2dfe14-c305-4187-bc9b-e4f811c5e4b7)

Costas loop consists of two product modulators with common input s(t), which is DSBSC wave. The other input for both product modulators is taken from Voltage Controlled Oscillator (VCO) with −900 phase shift to one of the product modulator as shown in figure.

We know that the equation of DSBSC wave is

![image](https://github.com/user-attachments/assets/9317150a-b7c5-458a-8846-a59c22eee892)

![image](https://github.com/user-attachments/assets/25a1e7fb-451c-47bd-ad59-bad13d8a4849)

The output of this Low pass filter has −900 phase difference with the output of the upper low pass filter.

The outputs of these two low pass filters are applied as inputs of the phase discriminator. Based on the phase difference between these two signals, the phase discriminator produces a DC control signal.

This signal is applied as an input of VCO to correct the phase error in VCO output. Therefore, the carrier signal (used for DSBSC modulation) and the locally generated signal (VCO output) are in phase.

## Frequency Modulation
In amplitude modulation, the amplitude of the carrier signal varies. Whereas, in Frequency Modulation (FM), the frequency of the carrier signal varies in accordance with the instantaneous amplitude of the modulating signal.

Hence, in frequency modulation, the amplitude and the phase of the carrier signal remains constant. This can be better understood by observing the following figures.

![image](https://github.com/user-attachments/assets/a2200b88-2984-4c3f-a9a3-88c061123e67)

The frequency of the modulated wave increases, when the amplitude of the modulating or message signal increases. Similarly, the frequency of the modulated wave decreases, when the amplitude of the modulating signal decreases. Note that, the frequency of the modulated wave remains constant and it is equal to the frequency of the carrier signal, when the amplitude of the modulating signal is zero.

**Mathematical Representation**

![image](https://github.com/user-attachments/assets/85ea5e8c-4614-431a-a5a4-7ef7ea881c98)

## Narrowband FM
Following are the features of Narrowband FM.

1. This frequency modulation has a small bandwidth when compared to wideband FM.
2. The modulation index β is small, i.e., less than 1.
3. Its spectrum consists of the carrier, the upper sideband and the lower sideband.
4. This is used in mobile communications such as police wireless, ambulances, taxicabs, etc.

## Wideband FM
Following are the features of Wideband FM.

1. This frequency modulation has infinite bandwidth.
2. The modulation index β is large, i.e., higher than 1.
3. Its spectrum consists of a carrier and infinite number of sidebands, which are located around it.
4. This is used in entertainment, broadcasting applications such as FM radio, TV, etc.

## FM Modulators

## Generation of NBFM
We know that the standard equation of FM wave is

![image](https://github.com/user-attachments/assets/1071fb12-5130-4939-a640-0881cfcdad06)

Here, the integrator is used to integrate the modulating signal m(t). The carrier signal Accos(2πfct) is the phase shifted by −90 degree to get Acsin(2πfct) with the help of −900 phase shifter. The product modulator has two inputs ∫m(t)dt and Acsin(2πfct). It produces an output, which is the product of these two inputs.

This is further multiplied with 2πkf by placing a block 2πkf in the forward path. The summer block has two inputs, which are nothing but the two terms of NBFM equation. Positive and negative signs are assigned for the carrier signal and the other term at the input of the summer block. Finally, the summer block produces NBFM wave.

## Generation of WBFM
The following two methods generate WBFM wave.

1. Direct method
2. Indirect method

## Direct Method
This method is called as the Direct Method because we are generating a wide band FM wave directly. In this method, Voltage Controlled Oscillator (VCO) is used to generate WBFM. VCO produces an output signal, whose frequency is proportional to the input signal voltage. This is similar to the definition of FM wave. The block diagram of the generation of WBFM wave is shown in the following figure.

![image](https://github.com/user-attachments/assets/8afc35f5-89ed-4052-bbb7-4323713b09c7)

## Indirect Method
This method is called as Indirect Method because we are generating a wide band FM wave indirectly. This means, first we will generate NBFM wave and then with the help of frequency multipliers we will get WBFM wave. The block diagram of generation of WBFM wave is shown in the following figure

![image](https://github.com/user-attachments/assets/d290a588-4b40-4fee-8a19-5d9f5fed6a2c)

This block diagram contains mainly two stages. In the first stage, the NBFM wave will be generated using NBFM modulator. We have seen the block diagram of NBFM modulator at the beginning of this chapter. We know that the modulation index of NBFM wave is less than one. Hence, in order to get the required modulation index (greater than one) of FM wave, choose the frequency multiplier value properly.

## FM Demodulators
The following two methods demodulate FM wave.

1. Frequency discrimination method
2. Phase discrimination method

## Frequency Discrimination Method

![image](https://github.com/user-attachments/assets/1b62ec04-c40a-422a-adee-5a22bb7501ee)

In the above equation, the amplitude term resembles the envelope of AM wave and the angle term resembles the angle of FM wave. Here, our requirement is the modulating signal m(t). Hence, we can recover it from the envelope of AM wave.

The following figure shows the block diagram of FM demodulator using frequency discrimination method.

![image](https://github.com/user-attachments/assets/80fc376e-2a9b-4714-9b77-2d6d268b2af0)

This block diagram consists of the differentiator and the envelope detector. Differentiator is used to convert the FM wave into a combination of AM wave and FM wave. This means, it converts the frequency variations of FM wave into the corresponding voltage (amplitude) variations of AM wave. We know the operation of the envelope detector. It produces the demodulated output of AM wave, which is nothing but the modulating signal.

## Phase Discrimination Method
The following figure shows the block diagram of FM demodulator using phase discrimination method.

![image](https://github.com/user-attachments/assets/da780eee-013c-4325-8d32-26ea49021ad3)

This block diagram consists of the multiplier, the low pass filter, and the Voltage Controlled Oscillator (VCO). VCO produces an output signal v(t), whose frequency is proportional to the input signal voltage d(t). Initially, when the signal d(t) is zero, adjust the VCO to produce an output signal v(t), having a carrier frequency and −90 degree phase shift with respect to the carrier signal.

FM wave s(t) and the VCO output v(t) are applied as inputs of the multiplier. The multiplier produces an output, having a high frequency component and a low frequency component. Low pass filter eliminates the high frequency component and produces only the low frequency component as its output.

This low frequency component contains only the term-related phase difference. Hence, we get the modulating signal m(t) from this output of the low pass filter.

## Noise
## What is Noise?
Noise is an unwanted signal, which interferes with the original message signal and corrupts the parameters of the message signal. This alteration in the communication process, leads to the message getting altered. It most likely enters at the channel or the receiver.

The noise signal can be understood by taking a look at the following figure.

![image](https://github.com/user-attachments/assets/c7c4e49e-b403-4ed6-a522-2933fa730a2f)

Hence, it is understood that the noise is some signal which has no pattern and no constant frequency or amplitude. It is quite random and unpredictable. Measures are usually taken to reduce it, though it cant be completely eliminated.

Most common examples of noise are −

1. Hiss sound in radio receivers
2. Buzz sound amidst of telephone conversations
3. Flicker in television receivers, etc

## SNR Calculations

## Signal to Noise Ratio
Signal-to-Noise Ratio (SNR) is the ratio of the signal power to noise power. The higher the value of SNR, the greater will be the quality of the received output.

Signal-to-Noise Ratio at different points can be calculated using the following formulas.

![image](https://github.com/user-attachments/assets/373481f7-3322-4292-a11d-c2a03305ce7b)

## Figure of Merit
The ratio of output SNR and input SNR can be termed as Figure of Merit. It is denoted by F. It describes the performance of a device.

![image](https://github.com/user-attachments/assets/1641a7d9-51c0-4c28-812f-4f488be4d956)

## SNR Calculations in AM System
Consider the following receiver model of AM system to analyze noise.

![image](https://github.com/user-attachments/assets/45413157-f00e-4a61-968e-5cab4088c1a5)

![image](https://github.com/user-attachments/assets/1c4e71ca-2245-4624-a5fa-4f4ec61829db)

Assume the band pass noise is mixed with AM wave in the channel as shown in the above figure. This combination is applied at the input of AM demodulator. Hence, the input of AM demodulator is.

![image](https://github.com/user-attachments/assets/cad83c1c-0e28-4f46-bf8c-a89cae838fb9)

## Sampling
So far, we have discussed about continuous-wave modulation. We will discuss about pulse modulation in the next chapter. These pulse modulation techniques deal with discrete signals. So, now let us see how to convert a continuous time signal into a discrete one.

The process of converting continuous time signals into equivalent discrete time signals, can be termed as Sampling. A certain instant of data is continually sampled in the sampling process.

The following figure shows a continuous-time signal x(t) and the corresponding sampled signal xs(t). When x(t) is multiplied by a periodic impulse train, the sampled signal xs(t) is obtained.

![image](https://github.com/user-attachments/assets/5bf8b51f-b219-4144-bc69-b014d3f2ed36)

A sampling signal is a periodic train of pulses, having unit amplitude, sampled at equal intervals of time Ts, which is called as sampling time. This data is transmitted at the time instants Ts and the carrier signal is transmitted at the remaining time.

## Sampling Rate
To discretize the signals, the gap between the samples should be fixed. That gap can be termed as the sampling period T. Reciprocal of the sampling period is known as sampling frequency or sampling rate fs.

Mathematically, we can write it as

![image](https://github.com/user-attachments/assets/e97cd745-162a-473d-b4f8-9f2bb577e9fc)

## Sampling Theorem
The sampling rate should be such that the data in the message signal should neither be lost nor it should get over-lapped. The sampling theorem states that, a signal can be exactly reproduced if it is sampled at the rate fs, which is greater than or equal to twice the maximum frequency of the given signal W.

Mathematically, we can write it as

![image](https://github.com/user-attachments/assets/d49da0f7-79e0-4182-891b-b510263e13d4)

If the sampling rate is equal to twice the maximum frequency of the given signal W, then it is called as Nyquist rate.

The sampling theorem, which is also called as Nyquist theorem, delivers the theory of sufficient sample rate in terms of bandwidth for the class of functions that are bandlimited.

For continuous-time signal x(t), which is band-limited in the frequency domain is represented as shown in the following figure.

![image](https://github.com/user-attachments/assets/028d72f3-a00b-40b8-be87-ad918c0ba5d6)

We can observe from the above pattern that there is over-lapping of information, which leads to mixing up and loss of information. This unwanted phenomenon of over-lapping is called as Aliasing.

Aliasing can be referred to as the phenomenon of a high-frequency component in the spectrum of a signal, taking on the identity of a low-frequency component in the spectrum of its sampled version.

Hence, the sampling rate of the signal is chosen to be as Nyquist rate. If the sampling rate is equal to twice the highest frequency of the given signal W, then the sampled signal would look like the following figure.

![image](https://github.com/user-attachments/assets/ccb82def-d19e-4437-9819-aa2e58655dc6)

## Pulse Modulation
After continuous wave modulation, the next division is Pulse modulation. In this chapter, let us discuss the following analog pulse modulation techniques.

1. Pulse Amplitude Modulation
2. Pulse Width Modulation
3. Pulse Position Modulation

## Pulse Amplitude Modulation
In Pulse Amplitude Modulation (PAM) technique, the amplitude of the pulse carrier varies, which is proportional to the instantaneous amplitude of the message signal.

The pulse amplitude modulated signal will follow the amplitude of the original signal, as the signal traces out the path of the whole wave. In natural PAM, a signal sampled at Nyquist rate can be reconstructed, by passing it through an efficient Low Pass Filter (LPF) with exact cutoff frequency.

The following figures explain the Pulse Amplitude Modulation.

![image](https://github.com/user-attachments/assets/68812063-fa26-4e39-a151-23845fd912a8)

Though the PAM signal is passed through a LPF, it cannot recover the signal without distortion. Hence, to avoid this noise, use flat-top sampling. The flat-top PAM signal is shown in the following figure.

## Pulse Width Modulation
In Pulse Width Modulation (PWM) or Pulse Duration Modulation (PDM) or Pulse Time Modulation (PTM) technique, the width or the duration or the time of the pulse carrier varies, which is proportional to the instantaneous amplitude of the message signal.

The width of the pulse varies in this method, but the amplitude of the signal remains constant. Amplitude limiters are used to make the amplitude of the signal constant. These circuits clip off the amplitude to a desired level, and hence the noise is limited.

The following figure explains the types of Pulse Width Modulations.

![image](https://github.com/user-attachments/assets/ec07fb3a-de34-403b-b31a-5033e3eda2c0)

There are three types of PWM.

1. The leading edge of the pulse being constant, the trailing edge varies according to the message signal. The waveform for this type of PWM is denoted as (a) in the above figure.

2. The trailing edge of the pulse being constant, the leading edge varies according to the message signal. The waveform for this type of PWM is denoted as (b) in the above figure.

3. The center of the pulse being constant, the leading edge and the trailing edge varies according to the message signal. The waveform for this type of PWM is denoted as (c) shown in the above figure.

## Pulse Position Modulation
Pulse Position Modulation (PPM) is an analog modulation scheme in which, the amplitude and the width of the pulses are kept constant, while the position of each pulse, with reference to the position of a reference pulse varies according to the instantaneous sampled value of the message signal.

The transmitter has to send synchronizing pulses (or simply sync pulses) to keep the transmitter and the receiver in sync. These sync pulses help to maintain the position of the pulses. The following figures explain the Pulse Position Modulation.

![image](https://github.com/user-attachments/assets/8c959a54-52f1-49bb-9e73-eba649e7f288)

Pulse position modulation is done in accordance with the pulse width modulated signal. Each trailing edge of the pulse width modulated signal becomes the starting point for pulses in PPM signal. Hence, the position of these pulses is proportional to the width of the PWM pulses.

**Advantage**
As the amplitude and the width are constant, the power handled is also constant.

**Disadvantage**
The synchronization between the transmitter and the receiver is a must.

## Comparison between PAM, PWM, and PPM

![image](https://github.com/user-attachments/assets/b7855d87-97b0-4123-a377-a5d8deb25aa7)

## Line Codes
A line code is the code used for data transmission of a digital signal over a transmission line. This process of coding is chosen so as to avoid overlap and distortion of signal such as inter-symbol interference.

## Properties of Line Coding
Following are the properties of line coding −

1. As the coding is done to make more bits transmit on a single signal, the bandwidth used is much reduced.
2. For a given bandwidth, the power is efficiently used.
3. The probability of error is much reduced.
4. Error detection is done and the bipolar too has a correction capability.
5. Power density is much favorable.
6. The timing content is adequate.
7. Long strings of 1s and 0s is avoided to maintain transparency.

**Types of Line Coding**
There are 3 types of Line Coding

1. Unipolar
2. Polar
3. Bi-polar

## Unipolar Signaling
Unipolar signaling is also called as On-Off Keying or simply OOK.

The presence of pulse represents a 1 and the absence of pulse represents a 0.

There are two variations in Unipolar signaling −

1. Non Return to Zero (NRZ)
2. Return to Zero (RZ)

## Unipolar Non-Return to Zero (NRZ)
In this type of unipolar signaling, a High in data is represented by a positive pulse called as Mark, which has a duration T0 equal to the symbol bit duration. A Low in data input has no pulse.

The following figure clearly depicts this.

![image](https://github.com/user-attachments/assets/c3f8a3ed-6c51-4bcf-a518-21c66319d585)

## Unipolar Return to Zero (RZ)
In this type of unipolar signaling, a High in data, though represented by a Mark pulse, its duration T0 is less than the symbol bit duration. Half of the bit duration remains high but it immediately returns to zero and shows the absence of pulse during the remaining half of the bit duration.

It is clearly understood with the help of the following figure.

![image](https://github.com/user-attachments/assets/8c28aa6e-5dc0-434c-b658-9a2e539e537f)

## Polar Signaling
There are two methods of Polar Signaling. They are −

1. Polar NRZ
2. Polar RZ

## Polar NRZ
In this type of Polar signaling, a High in data is represented by a positive pulse, while a Low in data is represented by a negative pulse. The following figure depicts this well.

![image](https://github.com/user-attachments/assets/f1b534fb-ed73-4c85-bcae-4a6c7456d0ec)

## Polar RZ
In this type of Polar signaling, a High in data, though represented by a Mark pulse, its duration T0 is less than the symbol bit duration. Half of the bit duration remains high but it immediately returns to zero and shows the absence of pulse during the remaining half of the bit duration.

However, for a Low input, a negative pulse represents the data, and the zero level remains same for the other half of the bit duration. The following figure depicts this clearly.

![image](https://github.com/user-attachments/assets/f7f115d6-95bf-45ad-ab5a-ce53aafe16dd)

## Bipolar Signaling
This is an encoding technique which has three voltage levels namely &plus;, - and 0. Such a signal is called as duo-binary signal.

An example of this type is Alternate Mark Inversion (AMI). For a 1, the voltage level gets a transition from &plus; to or from to &plus;, having alternate 1s to be of equal polarity. A 0 will have a zero voltage level.

Even in this method, we have two types.

1. Bipolar NRZ
2. Bipolar RZ

From the models so far discussed, we have learnt the difference between NRZ and RZ. It just goes in the same way here too. The following figure clearly depicts this.

![image](https://github.com/user-attachments/assets/4f0d2540-28ea-44c4-bb4b-cedcf5cb5a0c)

## Manchester Encoding
Manchester encoding is a method of data transmission used in computer networks and telecommunications. It works by combining the clock and data signals into one stream, making it easier to synchronize the data. Each bit of data is represented by a transition; a change from high to low or low to high in the signal. This helps ensure that the data is correctly interpreted by the receiving device. It is widely used in Ethernet technology and other digital communication systems due to its reliability and simplicity.

In Manchester, the duration of a bit is divided into two halves. The voltage remains the same at one level during the first half & moves to the other level. The transition in the middle of the bit provides synchronization. Differential Manchester, on the other hand, combines the idea of RZ and NRZ-I. There is always a transition in the middle of the bit, but the bit values are determined at the beginning of the bit. if the next bit is zero there is a transition if next bit is 1 there is none. 

![image](https://github.com/user-attachments/assets/3dae8cdf-8459-4a4b-baf5-f4fb0fbe612f)

## Phase Shift Keying
Phase Shift Keying (PSK) is the digital modulation technique in which the phase of the carrier signal is changed by varying the sine and cosine inputs at a particular time. PSK technique is widely used for wireless LANs, bio-metric, contactless operations, along with RFID and Bluetooth communications.

PSK is of two types, depending upon the phases the signal gets shifted. They are −

## Binary Phase Shift Keying (BPSK)
This is also called as 2-phase PSK or Phase Reversal Keying. In this technique, the sine wave carrier takes two phase reversals such as 0° and 180°.

BPSK is basically a Double Side Band Suppressed Carrier (DSBSC) modulation scheme, for message being the digital information.

## Quadrature Phase Shift Keying (QPSK)
This is the phase shift keying technique, in which the sine wave carrier takes four phase reversals such as 0°, 90°, 180°, and 270°.

If this kind of techniques are further extended, PSK can be done by eight or sixteen values also, depending upon the requirement.

## BPSK Modulator
The block diagram of Binary Phase Shift Keying consists of the balance modulator which has the carrier sine wave as one input and the binary sequence as the other input. Following is the diagrammatic representation.

![image](https://github.com/user-attachments/assets/a6d6ab04-4b36-4c88-83ec-ff96fce729f9)

The modulation of BPSK is done using a balance modulator, which multiplies the two signals applied at the input. For a zero binary input, the phase will be 0° and for a high input, the phase reversal is of 180°.

Following is the diagrammatic representation of BPSK Modulated output wave along with its given input.

![image](https://github.com/user-attachments/assets/287355a5-8d7a-4949-b8ce-d0461c8894cd)

## Quadrature Phase Shift Keying
The Quadrature Phase Shift Keying (QPSK) is a variation of BPSK, and it is also a Double Side Band Suppressed Carrier (DSBSC) modulation scheme, which sends two bits of digital information at a time, called as bigits.

Instead of the conversion of digital bits into a series of digital stream, it converts them into bit pairs. This decreases the data bit rate to half, which allows space for the other users.

## QPSK Modulator
The QPSK Modulator uses a bit-splitter, two multipliers with local oscillator, a 2-bit serial to parallel converter, and a summer circuit. Following is the block diagram for the same.

![image](https://github.com/user-attachments/assets/2e4350f5-9828-45c1-bdfa-e3f9e7244904)

At the modulators input, the message signals even bits (i.e., 2nd bit, 4th bit, 6th bit, etc.) and odd bits (i.e., 1st bit, 3rd bit, 5th bit, etc.) are separated by the bits splitter and are multiplied with the same carrier to generate odd BPSK (called as PSKI) and even BPSK (called as PSKQ). The PSKQ signal is anyhow phase shifted by 90° before being modulated.

The QPSK waveform for two-bits input is as follows, which shows the modulated result for different instances of binary inputs.

![image](https://github.com/user-attachments/assets/075c4f53-2e5e-44be-bb02-1da094c16018)

## QPSK Demodulator
The QPSK Demodulator uses two product demodulator circuits with local oscillator, two band pass filters, two integrator circuits, and a 2-bit parallel to serial converter. Following is the diagram for the same.

![image](https://github.com/user-attachments/assets/48f747a9-1b72-4afb-90b5-a5c7500a7c13)

The two product detectors at the input of demodulator simultaneously demodulate the two BPSK signals. The pair of bits are recovered here from the original data. These signals after processing, are passed to the parallel to serial converter.

## Frequency Shift Keying
Frequency Shift Keying (FSK) is the digital modulation technique in which the frequency of the carrier signal varies according to the digital signal changes. FSK is a scheme of frequency modulation.

The output of a FSK modulated wave is high in frequency for a binary High input and is low in frequency for a binary Low input. The binary 1s and 0s are called Mark and Space frequencies.

The following image is the diagrammatic representation of FSK modulated waveform along with its input.

![image](https://github.com/user-attachments/assets/19eb7acd-334c-443f-8787-d33dca7b6798)

To find the process of obtaining this FSK modulated wave, let us know about the working of a FSK modulator.

## FSK Modulator
The FSK modulator block diagram comprises of two oscillators with a clock and the input binary sequence. Following is its block diagram.

![image](https://github.com/user-attachments/assets/1d8ad0b0-f02e-46c8-855e-b88b74b3a09b)

The two oscillators, producing a higher and a lower frequency signals, are connected to a switch along with an internal clock. To avoid the abrupt phase discontinuities of the output waveform during the transmission of the message, a clock is applied to both the oscillators, internally. The binary input sequence is applied to the transmitter so as to choose the frequencies according to the binary input.

## FSK Demodulator
There are different methods for demodulating a FSK wave. The main methods of FSK detection are asynchronous detector and synchronous detector. The synchronous detector is a coherent one, while asynchronous detector is a non-coherent one.

## Asynchronous FSK Detector
The block diagram of Asynchronous FSK detector consists of two band pass filters, two envelope detectors, and a decision circuit. Following is the diagrammatic representation.

![image](https://github.com/user-attachments/assets/9665e429-a9a7-4cb5-ae67-2aa7f77acbcc)

The FSK signal is passed through the two Band Pass Filters (BPFs), tuned to Space and Mark frequencies. The output from these two BPFs look like ASK signal, which is given to the envelope detector. The signal in each envelope detector is modulated asynchronously.

The decision circuit chooses which output is more likely and selects it from any one of the envelope detectors. It also re-shapes the waveform to a rectangular one.

## Synchronous FSK Detector
The block diagram of Synchronous FSK detector consists of two mixers with local oscillator circuits, two band pass filters and a decision circuit. Following is the diagrammatic representation.

![image](https://github.com/user-attachments/assets/6b9b650b-f14c-40fd-8265-ffc254a5f7b3)

The FSK signal input is given to the two mixers with local oscillator circuits. These two are connected to two band pass filters. These combinations act as demodulators and the decision circuit chooses which output is more likely and selects it from any one of the detectors. The two signals have a minimum frequency separation.

For both of the demodulators, the bandwidth of each of them depends on their bit rate. This synchronous demodulator is a bit complex than asynchronous type demodulators.








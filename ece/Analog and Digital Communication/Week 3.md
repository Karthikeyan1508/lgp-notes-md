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



















































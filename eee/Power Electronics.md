# **Power Electronics**
Power Electronics is the study and application of electronic devices and circuits to control and convert electric power from one form to another.

**Applications:**
- Industrial Drives – Speed control of motors.
- Electric Vehicles (EVs) – Battery charging, motor control.
- HVDC Systems – Long-distance high-voltage power transmission.
- Power Supplies – SMPS (Switched Mode Power Supply), UPS.
- Renewable Energy – Solar inverters, wind converters.

## Power Devices and Their Control Characteristics

### **SCR (Silicon Controlled Rectifier)**
A 4-layer (PNPN), 3-junction semiconductor device with 3 terminals: Anode (A), Cathode (K), and Gate (G).
Conducts when triggered by gate current and continues conducting until the current drops below holding current.
- Latching Current (IL): Minimum anode current to maintain conduction after gate trigger.
- Holding Current (IH): Minimum anode current below which SCR turns off.

### TRIAC (Triode for AC)
Bidirectional equivalent of SCR.
Controls power in both halves of the AC cycle.
Used in fan regulators, light dimmers.

### MOSFET (Metal-Oxide-Semiconductor FET)
Voltage-controlled unipolar device.
High switching speed, low gate current.
Used in low-power, high-frequency circuits (DC-DC converters).

### IGBT (Insulated Gate Bipolar Transistor)
Combines advantages of BJT (high current) and MOSFET (voltage control).
High input impedance, good for medium and high power applications.
Used in inverters, UPS, motor drives.

## Types of Power Electronic Circuits

| Type           | Conversion                  | Application Example  |
| -------------- | --------------------------- | -------------------- |
| Rectifier      | AC to DC                    | Battery Chargers     |
| Inverter       | DC to AC                    | Solar Inverter, UPS  |
| Chopper        | DC to DC                    | EV speed control     |
| AC Controller  | AC to Controlled AC         | Fan speed regulators |
| Cycloconverter | AC to AC (Frequency change) | Low-speed AC motors  |

## Power Diode Characteristics and Recovery Time

**Forward and Reverse Bias:**
- In forward bias, diode conducts with low voltage drop (~0.7V for silicon).
- In reverse bias, diode blocks current ideally (except for leakage).

**Reverse Recovery Time (trr):**
- Time taken by diode to switch from forward conducting to reverse blocking mode.
- Affects efficiency and heat dissipation.
- Important in high-frequency applications.

## Thyristor Characteristics

**Static Characteristics:**
- Describes the V-I behavior during ON and OFF states.
- Forward Blocking → Forward Conduction → Reverse Blocking.

**Dynamic Characteristics:**
- Describe switching behavior:
- Turn-On Time
- Turn-Off Time
- Reverse Recovery

## Two-Transistor Model of SCR

**SCR can be modeled as:**
A PNP and NPN transistor connected in a regenerative feedback loop.

**Working Principle:**
Gate current triggers Q2 (NPN), which in turn activates Q1 (PNP), resulting in a latching effect.

## di/dt and dv/dt Protection of Thyristors

**di/dt Protection:**
Protects SCR from sudden high surge current when turned ON.
Why needed? Localized overheating can damage device.
Solution: Use inductors in series.

**dv/dt Protection:**
Protects against accidental triggering due to rapid voltage changes across SCR when OFF.
Solution: Use snubber circuits (RC networks).

## Series and Parallel Operation of SCRs

**Series Operation:**
Increases voltage rating.
Needs voltage equalizing resistors to ensure uniform voltage sharing.

**Parallel Operation:**
Increases current handling capacity.
Needs current sharing inductors/resistors.

Note: Perfect matching is difficult due to manufacturing tolerances.

## Thyristor Firing Circuits

**R Firing Circuit:**
Simple phase control using resistor.
Limited control range (~90°).

**RC Firing Circuit:**
Provides better control (0°–180°).
Uses RC network for phase delay.

**UJT Firing Circuit:**
Generates sharp gate pulses.
Uses Unijunction Transistor (UJT) and relaxation oscillator.
Efficient and widely used.

# Controlled Rectifiers
A controlled rectifier is a circuit that converts AC to DC using power semiconductor devices (like SCRs), and allows control over the output voltage by varying the firing angle (α). Unlike uncontrolled rectifiers (which use diodes), controlled rectifiers use thyristors for flexible control.

## Types of Controlled Rectifiers

### 1) Single-Phase Controlled Rectifiers

**a) Half-Controlled Rectifier (Semi-Converter)**

Circuit Elements:
- 1 SCR and 1 Diode (per half-cycle)
- Single-phase AC source
- Load: R, RL, or RLE

Working:
- Positive Half: SCR conducts after α; diode conducts naturally
- Negative Half: Diode conducts freely
- Output Voltage Control:
- Controlled only in one half-cycle
- Lower control range

Waveform:
Output Voltage: ___/‾‾‾‾\___/‾‾‾‾\___  (non-symmetrical)

**b) Fully-Controlled Rectifier (Full-Converter)**

Circuit Elements:
- 4 SCRs in bridge configuration
- Full-wave AC input
- Load: R, RL, or RLE

Working:
- All four SCRs are controlled
- Can operate in both rectification and inversion modes

Advantages:
- Better control over output
- Higher efficiency
- Output Voltage Equation:
![image](https://github.com/user-attachments/assets/ba19295b-2bbe-4407-9ec3-1704f37d07a1)
where 𝑉𝑚​ = peak of AC input, α = firing angle

### 2) Three-Phase Controlled Rectifiers

**a) Semi-Converter (3-phase)**
Uses 3 SCRs and 3 diodes
Provides 6-pulse output
Less harmonic distortion than single-phase

**b) Full-Converter (3-phase)**
Uses 6 SCRs
Produces 6 pulses per cycle
Higher output voltage and power

Output Equation:
![image](https://github.com/user-attachments/assets/7216544e-6634-4a2e-aaf8-5cc9b24c6e2b)

## Load Types and Their Effects

**a) R Load (Resistive)**
- Output current = output voltage
- No storage or delay
- Output voltage follows SCR conduction

**b) RL Load (Inductive)**
- Current lags voltage
- Causes continuous current flow even after SCR voltage becomes negative
- Requires freewheeling diode to handle energy stored in inductor

**c) RLE Load (Motors)**
- Load has resistance, inductance, and back EMF
- Seen in DC motor drives
- Output voltage must overcome EMF

## Free-Wheeling Diode (FWD)

**Purpose:**
Provides path for inductive load current when SCR turns OFF
Avoids high voltage spikes
Reduces voltage ripple

**Placement:**
Across the load
Cathode to positive end of load, Anode to negative

**Effect:**
Protects SCR
Increases power factor
Smoothens output

## Output Voltage Analysis and Waveforms

For Single Phase Full-Controlled Rectifier with R Load:
Output Voltage Waveform:
Starts at angle α instead of 0°
Follows AC sine from α to π, then repeats from π+α to 2π

Average Output Voltage:
![image](https://github.com/user-attachments/assets/cd0eef9a-69ad-498c-a64a-b40e3fdfbc30)

RMS Output Voltage:
![image](https://github.com/user-attachments/assets/e014506a-9027-46d4-ba77-8e085be8a66b)

Effect of α:
As α increases, output voltage decreases
At α = 90°, output voltage is zero
At α > 90°, circuit can operate in inverter mode if load allows

## Discontinuous and Continuous Conduction
Continuous Conduction Mode (CCM): Current flows throughout the cycle (usually RL/RLE load)
Discontinuous Conduction Mode (DCM): Current becomes zero in part of the cycle (light load or R-load)

# Inverters
An inverter is a power electronic circuit that converts DC power to AC power at desired voltage and frequency. Inverters are widely used in UPS systems, motor drives, renewable energy systems (solar/wind), electric vehicles, etc.

## Types of Inverters

Inverters are classified based on:
**Output waveform:** Square wave, quasi-square, sine wave
**Configuration:** Single-phase or three-phase
**Operation mode:** Voltage Source Inverter (VSI) or Current Source Inverter (CSI)

## Single-Phase Inverters

**a) Half-Bridge Inverter**

Circuit Components:
- Two switches (SCRs, MOSFETs, or IGBTs)
- Two capacitors (C/2 each for voltage division)
- Load: resistive or inductive

Operation:
- Switch T1 ON → +Vdc/2 to load
- Switch T2 ON → –Vdc/2 to load
- Output waveform: square wave

Output Voltage Waveform:
+Vdc/2 ___|‾‾‾‾‾‾|___|‾‾‾‾‾‾|___
         T1    T2    T1   T2...
-Vdc/2 ___|______|___|______|___

**b) Full-Bridge Inverter**

Circuit Components:
- 4 switches (T1 to T4)
- Load connected between center nodes

Working:
- T1 & T4 ON → +Vdc across load
- T2 & T3 ON → –Vdc across load
- High power applications

Output Voltage:
![image](https://github.com/user-attachments/assets/87aa7eac-4ba2-46f7-934f-f5d3dcffc47d)

Advantage:
- No need for center-tapped supply
- Higher voltage swing across load

## Three-Phase Bridge Inverter

Circuit Configuration:
- 6 switches (T1 to T6)
- 3 outputs (A, B, C) to load
- Typically 120° mode or 180° mode switching

Working Principle:
- Generates 3-phase AC from DC source
- Switching sequence determines phase voltages

Line Voltage:
![image](https://github.com/user-attachments/assets/cc0fbbe7-a6eb-4a5c-b8f5-ce39bbecbbea)

Applications:
- 3-phase motor drives
- Grid-connected solar inverters

## PWM (Pulse Width Modulation) Inverters

- Square waves contain harmonics
- PWM generates waveform close to sine wave
- Reduces THD (Total Harmonic Distortion)

Working:
- Modulates the width of each pulse based on reference sine wave
- Carrier wave = high-frequency triangular wave
- Reference = desired sinusoidal signal

Types:
- Single Pulse PWM
- Multiple PWM
- Sinusoidal PWM (SPWM) – most commonly used

Advantages of SPWM:
- Output approximates sine wave
- Better control over frequency and amplitude
- Lower filter requirement

## Voltage Source Inverter (VSI) vs Current Source Inverter (CSI)
| Feature      | VSI                  | CSI                     |
| ------------ | -------------------- | ----------------------- |
| Input        | Constant DC voltage  | Constant DC current     |
| Output       | AC voltage           | AC current              |
| Applications | UPS, motor drives    | Induction heating, HVDC |
| Devices Used | MOSFET, IGBT         | GTO, Thyristors         |
| Control      | Easier (voltage PWM) | More complex            |

## Output Voltage Control Techniques

**1) External Control:**
Adjust DC input voltage to change output

**2) Internal Control (Preferred):**
Use PWM to regulate output
Varies duty cycle to control average output

**Duty Cycle (D):**
![image](https://github.com/user-attachments/assets/29956894-833b-423c-8dc2-33f09c349cec)

## Harmonics in Inverters

Sources:
- Non-sinusoidal switching
- Sharp voltage transitions

Effects:
- Overheating of motors
- EMI issues
- Low efficiency

Reduction Methods:
- PWM techniques
- Output filters (LC filters)
- Using sinusoidal reference in SPWM

## Applications of Inverters
- UPS (Uninterruptible Power Supply)
- Solar and Wind Energy Systems
- Electric Vehicles
- HVDC Transmission
- AC Motor Drives (VFDs)

# Choppers and Cycloconverters

Power electronics converters such as choppers and cycloconverters are used to control voltage, current, and frequency.
**Chopper:** A DC-DC converter that controls the output DC voltage.
**Cycloconverter:** An AC-AC converter that changes the frequency of the input power supply without intermediate DC conversion.

## DC–DC Converters (Choppers)
A chopper is a static device that converts fixed DC to variable DC voltage. It works as a high-speed ON/OFF switch, often using IGBTs, MOSFETs, or SCRs.

### Classification of Choppers

**Based on Quadrant Operation**
| Type   | Output Voltage | Output Current | Application                    |
| ------ | -------------- | -------------- | ------------------------------ |
| Type A | Positive       | Positive       | Motoring – 1st quadrant        |
| Type B | Positive       | Negative       | Regenerative braking – 2nd     |
| Type C | Positive       | Bidirectional  | Motoring & braking – 1st & 2nd |
| Type D | Bidirectional  | Positive       | Bidirectional – 1st & 4th      |
| Type E | Bidirectional  | Bidirectional  | Four quadrant control          |

**Based on Operation**
- Step-down (Buck) chopper: Lowers output voltage
- Step-up (Boost) chopper: Increases output voltage
- Step-up/Step-down (Buck-Boost): Both possible

## Control Techniques in Choppers

**Time Ratio Control (TRC):**
Fixed frequency, variable TON/OFF
Output voltage depends on duty cycle

**Current Limit Control:**
Maintains output current within safe range

**Frequency Modulation Control:**
Varies frequency, keeps duty cycle fixed

## Cycloconverters (AC–AC Converters)
A cycloconverter converts AC power at one frequency to AC at a lower frequency directly, without DC conversion.
Used for low-speed AC drives, like large motors in cement mills, rolling mills, etc.

### Types of Cycloconverters
| Type                    | Input   | Output             | Frequency Conversion  |
| ----------------------- | ------- | ------------------ | --------------------- |
| Step-down               | AC      | AC                 | High to low frequency |
| Step-up (not practical) | AC      | AC                 | Low to high frequency |
| Single-phase            | 1-phase | 1-phase            |                       |
| Three-phase             | 3-phase | 1-phase or 3-phase |                       |

### Principle of Operation
Cycloconverter uses SCRs to construct output waveform by piecing together portions of input waveform.
Example: 3-phase to 1-phase Cycloconverter:
- Uses 6–12 SCRs
- Each output half-cycle is built from sections of 3-phase input
- Output frequency is a sub-multiple of input frequency

### Operation Modes
- Circulating Current Mode: Both converters (positive & negative group) operate simultaneously with a reactor in between.
- Non-Circulating Current Mode: Only one converter operates at a time, depending on polarity of output current.

### Waveforms and Harmonics
- Output waveform is stepped and approximates sine wave
- Significant harmonic content present
- Filters are required for waveform smoothing

### Applications of Cycloconverters
- Synchronous motor control
- Variable frequency drives (VFDs)
- Ship propulsion
- Rolling mills, cement plants

### Choppers vs Cycloconverters
| Feature          | Chopper                | Cycloconverter                    |
| ---------------- | ---------------------- | --------------------------------- |
| Type             | DC–DC                  | AC–AC                             |
| Input            | Fixed DC               | Fixed AC                          |
| Output           | Variable DC            | Variable AC (low freq)            |
| Devices          | IGBT, MOSFET           | SCR, Thyristors                   |
| Frequency Change | Not applicable         | Output < Input frequency          |
| Use Case         | DC motor speed control | AC motor drive (low-speed motors) |














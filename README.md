# n555-metronome
An analogue metronome built around the versatile NE555 timer IC. This project utilises the IC in astable mode to generate a consistent pulse that drives an audible buzzer and a visual LED indicator, with an adjustable tempo ranging from approximately 30 to 240 BPM

### Components used
1x NE555 timer IC
1x Active Buzzer
2x 10kΩ Potentiometers
Resistors: values mentioned in the circuit diagram
Capacitors: 68µF (timing capacitor), 10nF (control pin decoupling)

In this project, the NE555 is configured as an astable multivibrator: it oscillates between high and low states indefinitely without an external trigger.

### NE555 in astable mode
-circuit diagram-
-equations-

### Calculations
-Resistor and capacitor values based on equations and target bpm-

Equations - incorrect
Based on the standard NE555 formulas:
Time High (tH): 0.693×(RA + RB) × C
Time Low (tL): 0.693×RB × C
Total Period (T): tH + tL = 0.693 × (RA + 2RB) × C
Frequency (f): T1 ≈ (RA + 2RB)×C 1.44

### Final circuit diagram and picture
-as title-




WARNING: PROTOTYPE CONTENT AHEAD IS AI-GENERATED

Circuit Logic
The timing cycle is determined by the charging and discharging of capacitor C through resistors RA and RB :
Charge Path (tH): Current flows through RA and RB to charge capacitor C.
Discharge Path (tL): The capacitor discharges only through RB into the IC’s discharge pin (Pin 7).

​
Calculations
To achieve a target metronome range of 30 BPM to 240 BPM, the frequency (f = 60 BPM) must range from 0.5 Hz to 4.0 Hz.
Component Selection:
Using a fixed capacitor (C) of 68µF and a small fixed resistor (RA) of 220Ω, we calculate the necessary resistance for RB:
For 240 BPM (f≈4.0Hz): RB needs to be approximately 2.6 kΩ.
For 30 BPM (f≈0.5Hz): RB needs to be approximately 21.2 kΩ
.
Final Implementation
To cover this range, R 
B
​
  is composed of a fixed 2.5 kΩ resistance in series with two 10 kΩ potentiometers (x and y), allowing for a total R 
B
​
  range that spans the calculated requirements
:
f 
max
​
 : ≈4.05 Hz (≈243 BPM)
f 
min
​
 : ≈0.468 Hz (≈28 BPM)
Final Circuit Diagram
The final configuration uses the following connections
:
Pin 8 (V 
CC
​
 ) & Pin 4 (Reset): Connected to positive supply.
Pin 1 (GND): Connected to ground.
Pin 7 (Discharge): Connected between R 
A
​
  and R 
B
​
 .
Pin 2 (Trigger) & Pin 6 (Threshold): Tied together and connected between R 
B
​
  and Capacitor C.
Pin 3 (Output): Drives the active buzzer and Blue LED in series/parallel with appropriate current-limiting resistors.

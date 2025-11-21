# SSB

EXP NO: 3	SSB-SC-AM MODULATION using SCILAB

AIM:

To write a program to perform SSBSC modulation and demodulation using SCI LAB and study its spectral characteristics

EQUIPMENTS REQUIRED

•	Computer with i3 Processor

•	SCI LAB

Note: Keep all the switch faults in off position


Algorithm
1.	Define Parameters:
•	Fs: Sampling frequency.
•	T: Duration of the signal.
•	Fc: Carrier frequency.
•	Fm: Frequency of the message signal.
•	Amplitude: Maximum amplitude of the message signal.
2.	Generate Signals:
•	Message Signal: The baseband signal that will be modulated.
•	Carrier Signal: A high-frequency signal used for modulation.
•	Analytic Signal: Constructed using the Hilbert transform to get the in-phase and quadrature components.
3.	SSBSC Modulation:
•	Modulated Signal: Create the SSBSC signal using the in-phase and quadrature components, modulated by the carrier.
4.	SSBSC Demodulation:
•	Mixing: Multiply the SSBSC signal with the carrier to retrieve the message signal.
•	Low-pass Filtering: Apply a low-pass filter to remove high-frequency components and recover the original message signal.
5.	Visualization:
•	Plot the message signal, carrier signal, SSBSC modulated signal, and the recovered signal after demodulation.


PROCEDURE

•	Refer Algorithms and write code for the experiment.
•	Open SCILAB in System
•	Type your code in New Editor
•	Save the file
 
•	Execute the code
•	If any Error, correct it in code and execute again
•	Verify the generated waveform using Tabulation and Model Waveform

Model Waveform

<img width="704" height="178" alt="image" src="https://github.com/user-attachments/assets/32ee29b3-0d95-4192-9762-972d50c05c90" />
<img width="706" height="167" alt="image" src="https://github.com/user-attachments/assets/bff0d8fd-d679-444e-af37-0b34585853c1" />

Program

Am=9.2;
fm=400;
Ac=18.4;
fc=4000;
fs=400000;
t=0:1/fs:2/fm;
Em=Am*sin(2*3.14*fm*t);
subplot(4,1,1);
plot(t,Em);
xgrid;
Ec=Ac*sin(2*3.14*fc*t);
subplot(4,1,2);
plot(t,Ec);
xgrid;
Edsbsc1=(Am/2.*cos(2*3.14*fc*t-2*3.14*fm*t))-(Am/2.*cos(2*3.14*fc*t+2*3.14*fm*t));
Edsbsc2=(Am/2.*cos(2*3.14*fc*t-2*3.14*fm*t))+(Am/2.*cos(2*3.14*fc*t+2*3.14*fm*t));
Elsb=Edsbsc1+Edsbsc2;
subplot(4,1,3);
plot(t,Elsb);
Eusb=Edsbsc1-Edsbsc2;
subplot(4,1,4);
plot(t,Eusb);
xgrid;
exp 4
Am=10.2;
Fm=410;
b = 4.1;
Ac=20.4;
Fc=4100;
Fs=4100000;
t=0:1/Fs:2/Fm;
em = Am*cos(2*3.14*Fm*t);
subplot(3,1,1);
plot(t,em);
xgrid;
ec = Ac*cos(2*3.14*Fc*t);
subplot(3,1,2);
plot(t,ec);
xgrid;
efm = Ac * cos((2*3.14*Fc*t) + ( b*sin(2*3.14*Fm*t)));
subplot(3,1,3);
plot(t,efm);
xgrid;
Exp 5
How is PSD used in analysing the bandwidth requirements of an AM or FM signal?
Ans.
The Power Spectral Density (PSD) describes how the power of a signal is distributed across
different frequencies. In communication systems, PSD analysis is crucial for determining the
bandwidth requirements of modulation schemes like Amplitude Modulation (AM) and Frequency
Modulation (FM).
PSD analysis provides a frequency-domain view of how power is distributed in AM and FM signals,
helping to determine the necessary bandwidth for efficient communication.
import numpy as np 
import matplotlib.pyplot as plt 
Am = 14.4
Fm = 450  
Ac = 28.8 
Fc = 4500 
Fs = 4500000 
t = np.arange(0, 2/Fm, 1/Fs) 
em = Am * np.sin(2 * np.pi * Fm * t) 
plt.subplot(3, 1, 1) 
plt.plot(t, em) 
plt.grid() 
ec = Ac * np.sin(2 * np.pi * Fc * t) 
plt.subplot(3, 1, 2) 
plt.plot(t, ec) 
plt.grid() 
edsbsc=((Am/2)*np.cos((2*np.pi*Fc*t)-(2*np.pi*Fm*t)))
((Am/2)*np.cos((2*np.pi*Fc*t)+(2*np.pi*Fm*t))) 
plt.subplot(3, 1, 3) 
plt.plot(t, edsbsc) 
plt.grid() 
plt.tight_layout() 
plt.show()
exp 9
import numpy as np
import matplotlib.pyplot as plt
Am = 15.2
Fm = 460
B = 5.8
Ac = 30.4
Fc = 4600
Fs = 4600000
t = np.arange(0, 2/Fm, 1/Fs)
em = Am * np.cos(2 * np.pi * Fm * t)
plt.subplot(3, 1, 1)
plt.plot(t, em)
plt.grid()
ec = Ac * np.cos(2 * np.pi * Fc * t)
plt.subplot(3, 1, 2)
plt.plot(t, ec)
plt.grid()
efm = Ac * np.cos((2*np.pi*Fc*t) + ( B*np.sin(2*np.pi*Fm*t)))
plt.subplot(3, 1, 3)
plt.plot(t, efm)
plt.tight_layout()
plt.show()

OUTPUT WAVEFORM

<img width="610" height="460" alt="image" src="https://github.com/user-attachments/assets/22b254ee-ced5-4265-a719-62f89b1791d4" />


TABULATION

<img width="1600" height="1477" alt="image" src="https://github.com/user-attachments/assets/7d66f93c-302e-495f-b041-72453222b807" />


RESULT:

Thus, the SSB-SC-AM Modulation and Demodulation is experimentally done and the output is verified.






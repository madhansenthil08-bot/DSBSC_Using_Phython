# DSBSC_Using_Python


Aim


To implement and analyze DSBSC modulation and demodulation  using Python's NumPy and Matplotlib libraries. 

Apparatus Required

1.	Software: Python with NumPy and Matplotlib libraries
2.	Hardware: Personal Computer
  
Theory

Double Sideband Suppressed Carrier (DSBSC) modulation is a type of amplitude modulation in which the carrier signal is suppressed, and only the two sidebands containing the information are transmitted. In DSBSC, the transmitted signal consists of the upper sideband (USB) and the lower sideband (LSB) components, which carry the same information as the carrier but without wasting power on the carrier itself.


Algorithm


1.	Initialize Parameters: Set the values for carrier frequency, message frequency, sampling frequency, and frequency deviation.
2.	Generate Time Axis: Create a time vector for the signal duration.
3.	Generate Message Signal: Define the message signal as a cosine wave.
4.	Compute the Integral of the Message Signal: Calculate the integral of the message signal over time.
5.	Generate DSBSC Signal: Apply the DSBSC modulation formula to obtain the modulated signal.
6.	Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signals.

Program
```
import numpy as np
import matplotlib.pyplot as plt
Am = 6.7
fm = 564
Ac = 13.4
fc = 5640
fs = 56400
t = np.arange(0, 3/fm, 1/fs)
m1 = Am * np.cos(2 * np.pi * fm * t)
m2 = Am * np.cos(1.57 - 2 * np.pi * fm * t)
c1 = Ac * np.cos(2 * np.pi * fc * t)
c2 = Ac * np.cos(1.57 - 2 * np.pi * fc * t)
s1 = c1 * m1
s2 = c2 * m2
Slsb = s1 + s2
Susb = s1 - s2
plt.figure(figsize=(10, 8))
plt.subplot(4, 1, 1)
plt.plot(t, m1)
plt.subplot(4, 1, 2)
plt.plot(t, c1)
plt.subplot(4, 1, 3)
plt.plot(t, Slsb)
plt.subplot(4, 1, 4)
plt.plot(t, Susb)
plt.tight_layout()
plt.show()
```

Output Waveform

<img width="1062" height="844" alt="Screenshot 2025-10-24 173844" src="https://github.com/user-attachments/assets/bd509d22-afab-42b0-b0d4-4c37c93fa1cd" />

Tabular Column

![WhatsApp Image 2025-11-28 at 21 21 17_a746dd24](https://github.com/user-attachments/assets/9c434798-9d31-4b8c-95be-3031d91fdacc)

Result


Thus the DSB-SC-AM Modulation and Demodulation is generated.

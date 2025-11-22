# AM-using-python

Aim


To implement and analyze amplitude modulation (AM) using Python's NumPy and Matplotlib libraries. 

Apparatus Required

1.	Software: Python with NumPy and Matplotlib libraries
2.	Hardware: Personal Computer
  
Theory

Amplitude Modulation (AM) is a method of transmitting information over a carrier wave by varying its amplitude in accordance with the instantaneous amplitude of the input signal (message signal). The frequency and phase of the carrier wave remain constant while its amplitude changes proportionally to the message signal.



Algorithm


1.	Initialize Parameters: Set the values for carrier frequency, message frequency, sampling frequency, and frequency deviation.
2.	Generate Time Axis: Create a time vector for the signal duration.
3.	Generate Message Signal: Define the message signal as a cosine wave.
4.	Compute the Integral of the Message Signal: Calculate the integral of the message signal over time.
5.	Generate AM Signal: Apply the AM modulation formula to obtain the modulated signal.
6.	Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

Program
```
import numpy as np
import matplotlib.pyplot as plt

am = 4.2
fm = 368
ac = 8.4
fc = 3680
fs = 36800
beta = 3.3
t = np.arange(0, 2/fm, 1/fs)

m = am * np.cos(2 * np.pi * fm * t)
plt.subplot(3,1,1) 
plt.plot(t, m)
plt.title("Message Signal (m(t))") 

c = ac * np.cos(2 * np.pi * fc * t)
plt.subplot(3,1,2) # Changed to 3,1,2
plt.plot(t, c)
plt.title("Carrier Signal (c(t))") 


am_signal = ac * (1 + m/ac) * np.cos(2 * np.pi * fc * t)
plt.subplot(3,1,3) # Changed to 3,1,3
plt.plot(t, am_signal)
plt.title("AM Signal")


plt.tight_layout()
plt.show()
```


Output Waveform


<img width="630" height="470" alt="image" src="https://github.com/user-attachments/assets/ed1cdf8c-816f-4667-9539-dc49ba9f8b2f" />




Tabular Column & Calculation
![WhatsApp Image 2025-11-13 at 11 43 18 AM](https://github.com/user-attachments/assets/412ca594-51da-4c17-a1fa-efb8b1b761ef)








Result


The message signal, carrier signal, and frequency modulated (FM) signal will be displayed in separate plots. The modulated signal will show frequency variations corresponding to the amplitude of the message signal.

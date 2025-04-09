# EXP.NO.7-Simulation-of-Digital-Modulation-Techniques
7. Simulation of Digital Modulation Techniques Such as
   i) Amplitude Shift Keying (ASK)
   ii) Frequency Shift Keying (FSK)
   iii) Phase Shift Keying (PSK)

# AIM
To verify Amplitude Shift Keying (ASK),Frequency Shift Keying (FSK),Phase Shift Keying (PSK) using Python.
# SOFTWARE REQUIRED
Google Colab

# ALGORITHMS
Amplitude Shift Keying (ASK): Define binary data.

Set carrier frequency and sampling rate.

Generate time vector.

Generate message and carrier signals.

Modulate using ASK: Multiply carrier with data bits.

Plot message, carrier, and ASK signal.

Frequency Shift Keying (FSK): Define binary data.

Set two different frequencies for 1 and 0.

Create a time vector and message signal.

Generate modulated signal by selecting frequency according to the bit.

Plot message and FSK signal.

Phase Shift Keying (PSK): Define binary data.

Set carrier frequency and sampling rate.

Generate message and carrier signal.

Modulate using PSK: Use phase 0 for '1', phase π for '0'.

Plot message, carrier, and PSK signal.

# PROGRAM

#Amplitude Shift Keying (ASK)

import numpy as np

import matplotlib.pyplot as plt

data = [1, 0, 1, 0, 1, 1, 0, 1] # Binary data to be transmitted

bit_duration = 1 # Duration of each bit in seconds

fc = 10 # Carrier frequency in Hz

amplitude = 2 # Carrier amplitude

sampling_rate = 1000 # Number of samples per second

t = np.arange(0, bit_duration * len(data), 1/sampling_rate)

message_signal = np.repeat(data, sampling_rate * bit_duration)

carrier_signal = amplitude * np.sin(2 * np.pi * fc * t)

ask_signal = amplitude * message_signal * np.sin(2 * np.pi * fc * t)

plt.figure(figsize=(12, 8))

plt.subplot(3, 1, 1)

plt.plot(t, message_signal, 'b')

plt.title('Message Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.subplot(3, 1, 2)

plt.plot(t, carrier_signal, 'r')

plt.title('Carrier Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.subplot(3, 1, 3)

plt.plot(t, ask_signal, 'g')

plt.title('Amplitude Shift Keying Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.tight_layout()

plt.show()

#Frequency Shift Keying (FSK)

import numpy as np

import matplotlib.pyplot as plt

data = [1, 0, 1, 0, 1, 1, 0, 1] # Binary data to be transmitted

bit_duration = 1 # Duration of each bit in seconds

fc1 = 10 # Frequency for binary '1'

fc2 = 5 # Frequency for binary '0'

amplitude = 2 # Carrier amplitude

sampling_rate = 1000 # Samples per second

t = np.arange(0, bit_duration * len(data), 1/sampling_rate)

message_signal = np.repeat(data, sampling_rate * bit_duration)

fsk_signal = amplitude * (np.sin(2 * np.pi * fc1 * t) * message_signal + np.sin(2 * np.pi * fc2 * t) * (1 - message_signal))

plt.figure(figsize=(12, 8))

plt.subplot(3, 1, 1)

plt.plot(t, message_signal, 'b')

plt.title('Message Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.subplot(3, 1, 2)

plt.plot(t, amplitude * np.sin(2 * np.pi * fc1 * t), 'r', alpha=0.5, label="Carrier for 1")

plt.plot(t, amplitude * np.sin(2 * np.pi * fc2 * t), 'm', alpha=0.5, label="Carrier for 0")

plt.title('Carrier Signals (FSK)')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.legend()

plt.subplot(3, 1, 3)

plt.plot(t, fsk_signal, 'g')

plt.title('Frequency Shift Keying (FSK) Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.tight_layout()

plt.show()

#Phase Shift Keying (PSK)

import numpy as np

import matplotlib.pyplot as plt

data = [1, 0, 1, 0, 1, 1, 0, 1] # Binary data to be transmitted

bit_duration = 1 # Duration of each bit in seconds

fc = 10 # Carrier frequency in Hz

amplitude = 2 # Carrier amplitude

sampling_rate = 1000 # Samples per second

t = np.arange(0, bit_duration * len(data), 1/sampling_rate)

message_signal = np.repeat(data, sampling_rate * bit_duration)

carrier_signal = amplitude * np.sin(2 * np.pi * fc * t)

psk_signal = amplitude * np.sin(2 * np.pi * fc * t + np.pi * (1 - message_signal))

plt.figure(figsize=(12, 8))

plt.subplot(3, 1, 1)

plt.plot(t, message_signal, 'b')

plt.title('Message Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.subplot(3, 1, 2)

plt.plot(t, carrier_signal, 'r')

plt.title('Carrier Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.subplot(3, 1, 3)

plt.plot(t, psk_signal, 'g')

plt.title('Phase Shift Keying (PSK) Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.tight_layout()

plt.show()

# OUTPUT

![image](https://github.com/user-attachments/assets/c2df627e-11f2-4af4-9aca-75e42f9ae61f)

![image](https://github.com/user-attachments/assets/56ce83da-1a1d-47ce-8014-9298d2062e24)

![image](https://github.com/user-attachments/assets/05d284b5-3af0-4c1d-8137-4ea8253fb7f3)

# RESULT / CONCLUSIONS
Hence Amplitude Shift Keying (ASK),Frequency Shift Keying (FSK),Phase Shift Keying (PSK) verified using Python.

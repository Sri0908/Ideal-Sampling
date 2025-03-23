# Exp:1 Ideal Sampling
# Name: Sri Yoagavarshini R
# Reg. No.: 212223060270

### Aim:

To demonstrate ideal sampling of a continuous signal using Scilab, ensuring accurate signal reconstruction while avoiding aliasing.

### Tools required:

Python IDE with Numpy and Scipy.

### Program:

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import resample
fs = 100
t = np.arange(0, 1, 1/fs) 
f = 5
signal = np.sin(2 * np.pi * f * t)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal')
plt.title('Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
t_sampled = np.arange(0, 1, 1/fs)
signal_sampled = np.sin(2 * np.pi * f * t_sampled)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')
plt.title('Sampling of Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
reconstructed_signal = resample(signal_sampled, len(t))
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 100 Hz)')
plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
```

### Output Waveform:

![image](https://github.com/user-attachments/assets/16cf682d-b70f-4ea9-a5a7-985081972474)

![image](https://github.com/user-attachments/assets/02a9f804-6caa-483d-9ef5-4190a7d2c3ca)

![image](https://github.com/user-attachments/assets/1823d6cf-2ec5-4c5a-b1d6-f73b64f21e15)


### Result:

Ideal sampling captures a continuous signal at perfect intervals, ensuring accurate
reconstruction if sampled at twice the highest frequency (Nyquist rate). It’s a key
concept in digital signal processing and telecommunications. Practical systems
approximate ideal sampling with some limitations.

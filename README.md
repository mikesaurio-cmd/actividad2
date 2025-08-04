# actividad2

import numpy as np
import matplotlib.pyplot as plt

Fs = 1000  # Frecuencia de muestreo (Hz)
T = 1 / Fs
t = np.arange(0, 1, T)

# Pulso rectangular: activo entre 0.4 y 0.6 segundos
pulse = np.where((t >= 0.4) & (t <= 0.6), 1, 0)

# Función escalón unitario: cambia a 1 en t=0.5 segundos
step = np.where(t >= 0.5, 1, 0)

# Función senoidal: frecuencia 5 Hz
freq_sine = 5
sine = np.sin(2 * np.pi * freq_sine * t)

# Graficar señales
plt.figure(figsize=(12, 6))

plt.subplot(3,1,1)
plt.plot(t, pulse)
plt.title('Pulso Rectangular')
plt.ylabel('Amplitud')
plt.grid(True)

plt.subplot(3,1,2)
plt.plot(t, step)
plt.title('Función Escalón Unitario')
plt.ylabel('Amplitud')
plt.grid(True)

plt.subplot(3,1,3)
plt.plot(t, sine)
plt.title('Función Senoidal (5 Hz)')
plt.xlabel('Tiempo [s]')
plt.ylabel('Amplitud')
plt.grid(True)

plt.tight_layout()
plt.show()

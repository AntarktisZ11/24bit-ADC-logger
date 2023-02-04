The voltage reference has to fullfil the following basic electrical requirements:
- V<sub>REF</sub> = 5 V
- V<sub>IN max</sub> >10 V
- I<sub>load max</sub> >5 mA
- Battery friendly power consumption (somewhat subjective)

The most convenient unit for understanding how the reference error affects accuracy is in terms of the least significant bit (LSB) of the data converter. Parts-per-million (ppm) is the most common unit for reference accuracy error. Keep in mind that the reference error is seen as a gain error. This means the output-code error is twice that at full-scale than at mid-scale.

$$\text{LSB(ppm)} = 10^6 * (\frac{1}{2})^\text{NOB} \qquad \text{NOB : Number of Bits}$$

<center>

| **Bits** | **LSB (ppm)** |
|:--------:|:-------------:|
|     8    |      3906     |
|    10    |      977      |
|    12    |      244      |
|    14    |       61      |
|    16    |       15      |
|    20    |       ~1      |
|    24    |     ~0.06     |

</center>

Its use for a 20-24 bit ADC puts certain characteristic requirements on the device, mainly:
1. Low temperature coefficient (<5 ppm/°C)
2. Good initial output voltage accuracy and/or easy trimming
3. Low 0.1-10 Hz peak-to-peak noise

## **Combining error terms**
### *Maximum error values*
- ERROR I<sub>TEMP</sub> = TC * (T<sub>MAX</sub> - T<sub>MIN</sub>)

- ERROR I<sub>LOAD</sub> = LOAD_REG * (I<sub>LOAD_MAX</sub> - I<sub>LOAD_MIN</sub>)

- ERROR I<sub>LINE</sub> = LINE_REG * (V<sub>IN_MAX</sub> - V<sub>IN_MIN</sub>)

- ERROR I<sub>GUARANTEED</sub> = ERROR I<sub>INITIAL_ACCURACY</sub> + ERROR I<sub>TEMP</sub> + ERROR I<sub>LOAD</sub> + ERROR I<sub>LINE</sub>

### *Typical error values*

- ERROR I<sub>THERMAL_HYSTERESIS</sub> ≈ (Typ. Thermal Hysteresis)

- ERROR I<sub>LONG-TERM_STABILITY</sub> ≈ (Typ. Long-Term Stability)

- ERROR I<sub>LF_NOISE</sub> = $10^6 * (\frac{\text{0.1-10 Hz Peak-to-Peak}}{\text{V}_\text{REF}})$

- ERROR I<sub>TOT</sub> = ERROR I<sub>GUARANTEED</sub> + ERROR I<sub>THERMAL_HYSTERESIS</sub> + ERROR I<sub>LF_NOISE</sub>

**Example using REF5050**


# Resources
1. [Voltage Reference Selection Basics White Paper (Rev. A)](https://www.ti.com/lit/wp/slpy003a/slpy003a.pdf) by Texas Instruments
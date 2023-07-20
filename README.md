## PCB
[Schematic PDF](./pcb/docs/24bit-ADC-logger-schematic.pdf)

[CSV BoM](./pcb/docs/BoM/24bit-ADC-logger-bom.csv)

[Interactive BoM](./pcb/docs/BoM/24bit-ADC-logger-ibom.html)

### Top and bottom view of PCB
![PCB top-view SVG](./pcb/docs/24bit-ADC-logger-top.svg)
![PCB bottom-view SVG](./pcb/docs/24bit-ADC-logger-bottom.svg)

## Requirements

- Use two (2) 18650 batteries to keep it simple and battery charging easy to do separately without designing a new charger.

- 3D print battery holders keep design quick and inexpensive.

- Only use a linear voltage regulator to keep the design reliable and simple, improving measuring precision and accuracy.

- Input impedance should be high (>500 kΩ) to avoid affecting the device-under-test (DUT).

- Only have one measuring channel, keep usage simple to avoid unintended DUT interference.

- All test leads should be twisted pair and kept short to decrease differential mode interference.

- Max voltage should be around ±60 V

- Announce measurement via MQTT

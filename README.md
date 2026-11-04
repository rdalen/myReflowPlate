# myReflowPlate

A DIY controller for a hot plate, based on the [Elektor Reflow Plate article](https://www.elektormagazine.nl/articles/een-ventilator-voor-de-minireflow-plate).

The project started with the original Elektor design. I adapted the hardware and firmware to add some extra functionality and support both leaded and low-temperature solder paste.

<p align="center">
  <img width="75%" src="YOUR_REAL_MODEL_IMAGE" alt="myReflowPlate controller"/>
  <br/>
  <i>myReflowPlate controller</i>
</p>

## Hardware

### Controller modifications

I adapted the original schematic with a few additional circuits:

- A dedicated heating status LED.
- An RGB LED to indicate the reflow process status.
- A transistor circuit to control the cooling fan.
- Replaced the passive buzzer with an active buzzer.

For the controller, I used a cheap **LGT8F328P LQFP32 MiniEVB (Nano Style)** as an alternative to the Arduino Nano.

<img width="75%" alt="ReflowPlate schematic" src="https://github.com/user-attachments/assets/2c7f4d5e-f112-47a4-b8f3-24611b08fae5" />

<p align="center"><i>ReflowPlate schematic</i></p>

### PCB

I used the [Gerber files from the original Elektor PCB design](https://www.elektormagazine.nl/magazine/elektor-318/62355) as a starting point.

I ordered the original PCB layout and added the additional circuits to accommodate the controller modifications.

<img width="60%" alt="ReflowPlate controller PCB" src="https://github.com/user-attachments/assets/5dd8b555-f988-4740-bc97-8e442bbef233" />

<p align="center"><i>Modified ReflowPlate controller PCB</i></p>

### Enclosure

The enclosure is laser-cut and designed using [Onshape](https://cad.onshape.com/documents/f9842e5a0607c10c799405a4/w/c9b0513c447002e5fd45f673/e/24479710e199dccfacd098f1).

<img width="60%" alt="ReflowPlate enclosure" src="https://github.com/user-attachments/assets/77f5bb1a-195e-42f8-9a6c-986c2d47eecd" />

<p align="center"><i>ReflowPlate controller enclosure</i></p>

## Firmware

The original Arduino sketch is available from the [Elektor project page](https://www.elektormagazine.nl/magazine/elektor-318/62355).

I used this sketch as the starting point and adapted it for my hardware. The updated firmware is developed in **VS Code using PlatformIO** and is included in this repository.

### Main features

- Rotary encoder for menu navigation and temperature adjustment.
- Multiple soldering profiles.
- Dedicated preheater mode with adjustable temperature.
- PID-based temperature control.
- Active cooling using a controlled fan.
- RGB LED status indication.
- Buzzer feedback for user interaction.
- Thermocouple fault detection, with heating interruption and an error message.

### Soldering profiles

The firmware includes two reflow profiles:

- **LOW TEMP** – for SN42Bi58 low-temperature solder paste (melting point approximately 138 °C).
- **LEADED** – for conventional leaded solder paste.

The low-temperature profile was added because I use low-temperature solder paste in some of my projects.

<p align="center">
  <img width="90%" alt="ReflowPlate soldering profiles" src="https://github.com/user-attachments/assets/d5fbf348-5f41-424d-be0d-b32d96703110" />
  <br/>
  <i>LOW TEMP and LEADED soldering profiles</i>
</p>

The profiles define temperature setpoints over time. Actual temperatures may differ depending on the hot plate, PCB, component placement and thermal characteristics.

## Repository contents

The repository contains the PlatformIO firmware project and the related project resources.

## References

- [Original Elektor article – A fan for the Mini Reflow Plate](https://www.elektormagazine.nl/articles/een-ventilator-voor-de-minireflow-plate)
- [Elektor project files and original Arduino sketch](https://www.elektormagazine.nl/magazine/elektor-318/62355)
- [Onshape enclosure design](https://cad.onshape.com/documents/f9842e5a0607c10c799405a4/w/c9b0513c447002e5fd45f673/e/24479710e199dccfacd098f1)

---

*This is a personal DIY project, developed as an adaptation of the original Elektor design.*

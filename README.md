# myReflowPlate

A DIY controller for a hot plate, based on the [Elektor Reflow Plate article](https://www.elektormagazine.nl/articles/een-ventilator-voor-de-minireflow-plate).

The project started with the original Elektor design. I adapted both the hardware and firmware to add extra functionality and support different soldering profiles for leaded and low-temperature solder paste.

One issue I encountered was that the standard neodymium magnets supplied with the hot plate started losing their magnetism permanently at temperatures as low as 80 °C. The original mounting feet were modified by drilling larger holes and using longer screws to secure them to an old cooling plate salvaged from a faulty power supply.

<p align="center">
  <img width="75%" alt="myReflowPlate" src="https://github.com/user-attachments/assets/955d1253-36cf-41d0-a430-e6ea3b0ce15a" />
  <br/>
  <i>My ReflowPlate</i>
</p>

## Hardware

### Controller modifications

I adapted the original schematic with a few additional circuits:

- A dedicated heating status LED.
- An RGB LED to indicate the reflow process status.
- A transistor circuit to control the cooling fan.
- An active buzzer, replacing the original passive buzzer.

For the controller, I used an inexpensive Nano-style **LGT8F328P LQFP32 MiniEVB** as an alternative to the Arduino Nano. See [this article](https://wolles-elektronikkiste.de/en/lgt8f328p-lqfp32-boards) for more information about this board.

<img width="75%" alt="ReflowPlate schematic" src="https://github.com/user-attachments/assets/2c7f4d5e-f112-47a4-b8f3-24611b08fae5" />

<p align="center"><i>Modified ReflowPlate schematic</i></p>

### PCB

I used the [Gerber files from the original Elektor PCB design](https://www.elektormagazine.nl/magazine/elektor-318/62355) as a starting point.

I ordered the original PCB layout and added the additional circuits to accommodate my controller modifications.

<img width="60%" alt="Original ReflowPlate controller PCB" src="https://github.com/user-attachments/assets/5dd8b555-f988-4740-bc97-8e442bbef233" />

<p align="center"><i>Original ReflowPlate controller PCB</i></p>

The following pictures show the PCB with my additional circuits.

<p align="center">
  <img width="49%" alt="Modified ReflowPlate PCB" src="https://github.com/user-attachments/assets/d8567c9e-c781-468e-a535-424abc1a9211" />
  <img width="43%" alt="Modified ReflowPlate PCB detail" src="https://github.com/user-attachments/assets/217622d7-3abb-4f30-b1c0-c05ab8a9a377" />
  <br/>
  <i>The PCB with my additions</i>
</p>

### Enclosure

The enclosure is laser-cut and designed using [Onshape](https://cad.onshape.com/documents/f9842e5a0607c10c799405a4/w/c9b0513c447002e5fd45f673/e/24479710e199dccfacd098f1).

<img width="60%" alt="ReflowPlate enclosure" src="https://github.com/user-attachments/assets/77f5bb1a-195e-42f8-9a6c-986c2d47eecd" />

<p align="center"><i>ReflowPlate controller enclosure</i></p>

<img width="60%" alt="ReflowPlate assembly" src="https://github.com/user-attachments/assets/b0983567-3cd5-4fcd-8fd6-6321c63ee2d2" />

<p align="center"><i>The complete assembly</i></p>

## Firmware

The original Arduino sketch is available from the [Elektor project page](https://www.elektormagazine.nl/magazine/elektor-318/62355).

I used this sketch as the starting point and adapted it for my hardware. The updated firmware is developed in **VS Code using PlatformIO** and is included in this repository.

### Main features

- Rotary encoder for menu navigation and temperature adjustment.
- Two soldering profiles.
- Preheater mode with adjustable temperature.
- PID-based temperature control.
- Active cooling using a controlled fan.
- RGB LED status indication.
- Buzzer feedback for user interaction.
- Thermocouple fault detection, including heating interruption and an error message.

<img width="60%" alt="ReflowPlate controller display" src="https://github.com/user-attachments/assets/6ceb8deb-f187-4501-b507-428d1655def5" />

### Soldering profiles

The firmware includes two reflow profiles:

- **LOW TEMP** – for SN42Bi58 low-temperature solder paste (melting point approximately 138 °C).
- **LEADED** – for conventional leaded solder paste.

I added the low-temperature profile because I use low-temperature solder paste for some of my projects.

<p align="center">
  <img width="90%" alt="ReflowPlate soldering profiles" src="https://github.com/user-attachments/assets/d5fbf348-5f41-424d-be0d-b32d96703110" />
  <br/>
  <i>LOW TEMP and LEADED soldering profiles</i>
</p>

The profiles define temperature setpoints over time. Actual temperatures may differ depending on the hot plate, PCB, component placement and thermal characteristics.

## Repository contents

The repository is organized into the following main folders:

- `kicad files/` – Hardware design files, including schematics and PCB layout.
- `lasercut files/` – The enclosure design as svg.
- `src/` – Arduino firmware source code.
- `include/` and `lib/` – PlatformIO project resources, if required.

The root folder also contains the PlatformIO configuration file and project documentation.

## References

- The original Reflow Plate article appeared in the November/December 2023 issue of Elektor (page 120).
- [A fan for the Mini Reflow Plate – 240198-01](https://www.elektormagazine.nl/articles/een-ventilator-voor-de-minireflow-plate), published in the November/December 2025 issue of Elektor.
- [Elektor project files and original Arduino sketch](https://www.elektormagazine.nl/magazine/elektor-318/62355).
- [Onshape enclosure design](https://cad.onshape.com/documents/f9842e5a0607c10c799405a4/w/c9b0513c447002e5fd45f673/e/24479710e199dccfacd098f1).

---

*This is a personal DIY project, developed as an adaptation of the original Elektor design.*

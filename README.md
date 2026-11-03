# myReflowPlate

A DIY controller for a Hot Plate, based on this  [Elektor article](https://www.elektormagazine.nl/articles/een-ventilator-voor-de-minireflow-plate?utm_source=Klaviyo&utm_medium=email&utm_campaign=Draadloze%20ESP32-weegschalen%252C%20Van%20PAL%20tot%20FPGA%252C%2050-watt%20solar-laadregelaar%20en%20meer&_kx=gfqaxOySi4_My8IVnZu0zz7oQaEuES7QDWbDh4O1UtEVefTPhj8f0vZ4BP8w0ZLT.QQ33pb).

<img width="60%" alt="image" src="https://github.com/user-attachments/assets/77f5bb1a-195e-42f8-9a6c-986c2d47eecd" />
<p align="center"><i>ReflowPlate controller</i></p>

For this project, I adapted the original schematic with; 
- a "Heating LED
- a Refow proces RGB LED
- a transistor for the cooling fan

For the controller i used the LGT8F328P LQFP32 MiniEVB (Nano Style) as alternative for the Arduino Nano

<img width="75%" alt="image" src="https://github.com/user-attachments/assets/2c7f4d5e-f112-47a4-b8f3-24611b08fae5" />

<p align="center"><i>ReflowPlate schematic</i></p>

I used the [gerber files](https://www.elektormagazine.nl/magazine/elektor-318/62355) from the original PCB design, which I used to order the PCBs, and added the extra circuits to the PCBs.

<img width="60%" alt="image" src="https://github.com/user-attachments/assets/5dd8b555-f988-4740-bc97-8e442bbef233" />
<p align="center"><i>ReflowPlate controller PCB</i></p>

The laser cut enclosure is designed with [OnShape](https://cad.onshape.com/documents/f9842e5a0607c10c799405a4/w/c9b0513c447002e5fd45f673/e/24479710e199dccfacd098f1)

The [arduino sketch](https://www.elektormagazine.nl/magazine/elektor-318/62355) can be found on the on the Elektor site
Because I use low temperature solderpaste, I added a low temperature profile next to the leaded solder profile
The VS Code sketch can be found in the repository

<img width="60%" alt="image" src="https://github.com/user-attachments/assets/d5fbf348-5f41-424d-be0d-b32d96703110" />
<p align="center"><i>ReflowPlate profiles</i></p>

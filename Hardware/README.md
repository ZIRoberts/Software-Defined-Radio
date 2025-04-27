# Software-Defined-Radio Hardware
Here exists all PCB designs and electrical schematics for the Software Defined Radio. All symbols, schematics, footprints, and board layouts are designed in KI-CAD 8. 

# Overview

There is a single board in this sytem and it is broken up into 11 sections and A system diagram represented by their own respective schematic sheet. All sheets, artwork, and 3D models are displayed jere. Each sheet is paired with a brief explantion of it's function and design decisions.

# Top View
![SDR_PCB_TOPVIEW](https://github.com/user-attachments/assets/45ce893a-79f1-4a8d-bc1a-d4067f322ca8)

# Bottom View
![3D_ Bottom View](https://github.com/user-attachments/assets/ebf63a86-f803-459b-bbec-5217f04d7bfe)

# System Diagram
![SCHD_SYSDIAGRAM](https://github.com/user-attachments/assets/809b9ce8-3c4f-49c9-9a16-8345289737f5)

# Microcontroller Conncetions (SAME70)
The brains of the board is a Microchip SAME70 utlizaing ARM Cortex-M7 core. This IC was selected primarily because the available number of pins, native USB 2.0, and the Direct Memory Acess controller that can directly transfer the recieved signal from the input to the output buffer of the USB 2.0.
![SCHD_MCU](https://github.com/user-attachments/assets/1f876db1-ee9f-4488-8ea0-78eb6cae11c3)

# FPGA Connections (Lattice Machx02)
 The Lattice MACHX02 FPGA is not necessarily needed for the design but was added for future additions and the option to experiment with digital signal processing in the future. 
![SCHD_CPLD](https://github.com/user-attachments/assets/abe879bc-96c3-4bec-82a9-3dbc410a7d3e)

# Analog to Digital Converter 
![SCHD__ADC](https://github.com/user-attachments/assets/568a1607-430a-4cd3-b198-d7dc0347af2b)

# Base Band Filter
![SCHD_BBF](https://github.com/user-attachments/assets/5fe0f32a-5170-43e8-ab77-7528e1b5684f)

# Demodulator
![SCHD_DEMOD](https://github.com/user-attachments/assets/6854fbb7-ecf3-4fe4-b5a9-9713c1368882)

# Modulator
![SCHD_MOD](https://github.com/user-attachments/assets/33294671-da79-4f47-ab49-d9767ca30aba)

# Antenna I/O
![SCHD_ANT_IO](https://github.com/user-attachments/assets/0eab936b-f169-4f99-8dfc-42bcee9b4384)

# Clock_Generator
![SCHD_PLL](https://github.com/user-attachments/assets/1ff74f63-613c-4c41-b7e4-afda4df0f3d4)

# Local_Oscillator
![SCHD_LO](https://github.com/user-attachments/assets/f4de715b-07e9-47b5-b34f-a634eecd64e2)

# Power
![SCHD_POWER](https://github.com/user-attachments/assets/024ffe9b-9e78-4349-b10d-61359dc97b14)

# Connectors
![SCHD_CONN](https://github.com/user-attachments/assets/b7892687-fd28-4de4-adc5-fad25b52007b)

# Top Artwork (Signal/Controlled Impedance)
![Top_Copper](https://github.com/user-attachments/assets/f4428ba7-071f-4757-94b9-859b01b3fbd4)

# Inner Layer 1 (GND-Plane) Artwork 
![INNER_LAYER_1 Copper](https://github.com/user-attachments/assets/12d94a30-3ffb-49c5-a393-f946eca4fc28)

# Inner Layer 2 (Power-Plane) Artwork 
![Layer2_copper](https://github.com/user-attachments/assets/03bc0722-e517-437e-826e-11d6e5b3f49e)

# Inner Layer 3 (Signal) Artwork 
![Layer3 Copper](https://github.com/user-attachments/assets/232a6136-68d7-4d53-b8e1-5b4c18cfcc2d)

# Inner Layer 4 (GND-Plane) Artwork 
![layer 4 copper](https://github.com/user-attachments/assets/e1814f8c-8912-4b33-b7e7-2c14564476c4)

# Bottom Artwork (Signal/Controlled Impedance) Artwork 
![layer 5 copper](https://github.com/user-attachments/assets/e92f21d0-b0d5-4b78-8aa9-94f62620a995)

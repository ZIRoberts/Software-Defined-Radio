# Software-Defined-Radio Hardware
Here exists all PCB designs and electrical schematics for the Software Defined Radio. All symbols, schematics, footprints, and board layouts are designed in KI-CAD 8. 

# Overview

There is a single board in this sytem and it is broken up into 11 sections and A system diagram represented by their own respective schematic sheet. All sheets, artwork, and 3D models are displayed jere. Each sheet is paired with a brief explantion of it's function and design decisions.

# Top View
![SDR_PCB_TOPVIEW](https://github.com/user-attachments/assets/45ce893a-79f1-4a8d-bc1a-d4067f322ca8)

# Bottom View
![3D_ Bottom View](https://github.com/user-attachments/assets/ebf63a86-f803-459b-bbec-5217f04d7bfe)

# System Diagram

The system Diagrm shows the overall flow of data throughout the SDR. The MCU on the far left iterfaces with a computer through USB 2.0 allowing the user to iteract with the SDR and either transmit or recieve data. The FPGA currently has no special function and is acting as a passthrough. Future developments of this project will include moving the digital signal processing from the user's computer into the FPGA. The FPGA  recieved the data from the Analog to Digital Converter that reads  a differential output from the Base Band Filter driven by the Demodulator. The FPGA trasnmits a digital signal to a Digital to Analog converter within the Modulator sheet that then drive the modulator.

The The Clock generator 4 unqiue independant C-MOS clock signals to the FPGA, ADC, DAC, and Local Oscillator. The Local Oscillator is controller by the MCU and drives the Quadature Modulator and Quadatrue Demodulator. 

![SCHD_SYSDIAGRAM](https://github.com/user-attachments/assets/809b9ce8-3c4f-49c9-9a16-8345289737f5)

# Microcontroller Conncetions (SAME70)

The brains of the board is a Microchip SAME70 utlizaing an ARM Cortex-M7 core. This IC was selected primarily because the available number of pins, native USB 2.0, and the Direct Memory Acess controller that can directly transfer the recieved signal from the input to the output buffer of the USB 2.0.

![SCHD_MCU](https://github.com/user-attachments/assets/1f876db1-ee9f-4488-8ea0-78eb6cae11c3)

# FPGA Connections (Lattice Machx02)

 The Lattice MACHX02 FPGA is not necessarily needed for the design but was added for future additions and the option to experiment with digital signal processing in the future. 
 
![SCHD_CPLD](https://github.com/user-attachments/assets/abe879bc-96c3-4bec-82a9-3dbc410a7d3e)

# Analog to Digital Converter 

The ADC12D20 is a 10 bit, 20 MSPS differential ADC with 2 separate converters for I/Q signals. It is driven by 4, low noise, 50 MHz GBW OP-AMPs, and switches that can tie the ADC to Ground for offset calibration on start up.


![SCHD__ADC](https://github.com/user-attachments/assets/568a1607-430a-4cd3-b198-d7dc0347af2b)

# Base Band Filter

A Differential LC 6th order Chebyshev Filter was added between the Demodulator and ADC to prevent aliasing of the baseband signal. ADC_VCMO is a 1.2 V bias outputted by the ADC10D20 to ensure the incoming differential signals are within the ADC's specifications.

![SCHD_BBF](https://github.com/user-attachments/assets/5fe0f32a-5170-43e8-ab77-7528e1b5684f)

# Demodulator

The ADL5387APCZ is a Quadrature Demodulator that has an operating frequency range of 30 MHz to 2 GHz with a 240 MHz demodulation Bandwidth. It is driven by a differential signal created by passing the received RF wave through a BALUN transformer. Transistor Q2 is can add an optional BIAS to the demodulator. By lowering the resistance between the Bias pin and ground both the noise-figure and supply current of the demodulator decreases but so does the overall dynamic range.

![SCHD_DEMOD](https://github.com/user-attachments/assets/6854fbb7-ecf3-4fe4-b5a9-9713c1368882)

# Modulator

The modulator sheet contains both the Digital To Analog Converter MAX5185 and Quadrature Modulator ADL538APCZ. The ADL538APCZ modulator is sister part to the ADL5387PCZ demodulator and has an operating range of 30 MHz to 2.2 GHz. The MAX5185 is a 10 bit 40 MHz Digital to Analog Current converter with integrated output resistors.

![SCHD_MOD](https://github.com/user-attachments/assets/33294671-da79-4f47-ab49-d9767ca30aba)

# Antenna I/O

The Antenna I/O sheet controls the Transmitting/Receiving state of the SDR and has a built in Loop Back switch to permit in circuit testing and validation. Both the transmit and received lines have an optional 20 dB gain LNA. The AD8353 was selected for the LNA primarily based on cost, broadband operation, and that a Bias-T is not needed when operating at 5 VDC.

![SCHD_ANT_IO](https://github.com/user-attachments/assets/0eab936b-f169-4f99-8dfc-42bcee9b4384)

# Clock_Generator

The SI5351A clock generator is used to provide a stable and consistent clock signal to the FPGA, ADC, DAC, and PLL. It was chosen based on it's frequency range, and ease of use.

![SCHD_CLOCK_GEN](https://github.com/user-attachments/assets/c5ae32bb-6810-4f8a-86c5-c307f9c25c72)

# Local_Oscillator

The ADF4351 Phase-Lock-Loop was selected for the Local Oscillator due to the output frequency range of 40 MHz to 4 GHz allows for the full range of operation of both the Modulator and Demodulator Along with programable power outputs that will permit the user to offset the self-attenuation of the clock signal as it transmits across the board. A Fast Lock Typology was selected for the loop filter to maximize the operational frequency and minimize locking time.

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

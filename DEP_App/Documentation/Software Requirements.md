# Software requirements

## Main software environment

Please install [LabVIEW 32-bit 2024 Q1](https://www.ni.com/en/support/downloads/software-products/download.labview.html#) with following packages:

* LabVIEW 2024 Q1
* LabVIEW Real-Time Module 2024 Q1
* LabVIEW FPGA Module 2024 Q1
* LabVIEW FPGA Compile Farm Toolkit 2024 Q1
* LabVIEW FPGA Compilation Tool for Vivado 2021.1 2024 Q1
* All Drivers Section
* JKI VI Package Manager 2024 Q1

From Additional Items choose

* IVI Class Simulation Drivers 2024 Q1
* IVI Class Simulation Drivers Source 2024 Q1
* IVI Compliance Package Support for LabVIEW 2024 Q1
* LabVIEW Real-Time Trace-Viewer
* NI Certificates Installer 21.5.0
* NI CompactRIO Support for LabVIEW 2024 Q1
* NI Distributed System Manager 2024 Q1
* NI Functional Safety Editor May 2018 64-bit 17.7.1
* NI GigE Vision Driver 2023 Q1
* NI Hardware Configuration Importer 5.1.0
* NI Hardware Configuration Utility 2024 Q1
* NI I/O Trace 2023 Q3
* NI Industrial Controller Firmware for Linux Real-Time Embedded Targets 2023 Q1
* NI Industrial Controller MAX remote Provider 2023 Q1
* NI Industrial Controller Support for LabVIEW 2023 Q1
* NI LabVIEW Advanced Signal Processing Toolkit 2024 Q1
* NI LabVIEW Command Line Interface 2024 Q1
* NI LabVIEW Digital Filter Design Toolkit 2024Q1
* NI LabVIEW Report Generation Toolkit Support for LabVIEW 2024 Q1
* NI LabVIEW Unit Test Framework Toolkit Support for LabVIEW 2024 Q1
* NI LabVIEW VI Analyzer Toolkit Support for LabVIEW 2024 Q1
* NI Linux RT System Image Driver Support 2024 Q1
* NI R Series Support for LabVIEW 2024 Q1
* NI-488.2 MAX Support 2023 Q3
* NI-488.2 Utilities 2023 Q3
* NI-DAQmx Runtime with Configuration Support 2024 Q1
* NI-DAQmx Support for .NET Framework 4.0 Languages 2024 Q1
* NI-DAQmx Support for .NET Framework 4.5 Languages 2024 Q1
* NI-DAQmx Support for LabVIEW 2024 Q1
* NI-DMM Support for LabVIEW 2023 Q4
* NI-Embedded CAN for RIO Support for LabVIEW 2023 Q2
* NI-FGEN Support for LabVIEW 2023 Q4
* NI-RIO cRIO Firmware for NI Linux-RT Real-Time Embedded Targets 2024 Q1
* NI-Serial Configuration 2023 Q4
* NI-VISA.NET Development Support 2024 Q1
* NI-VISA.NET Runtime 2024 Q1
* NI-VISA Driver Development Wizard 2024 Q1
* NI-VISA Interactive Control 2024 Q1
* NI-VISA Support for LabVIEW 2024 Q1
* TDM Excel Add-In 21.5.1
* NI Linux RT System Image 2023 Q4

You should also install additional software for your FPGA and RT targets. [The appropriate driver can be found here](https://www.ni.com/en-gb/support/documentation/compatibility/21/ni-hardware-and-operating-system-compatibility.html). Learn more about the [FPGA Module](ni.com/labview/fpga).

*Optional:* To compile your code into the bitfile for your target, LabVIEW FPGA Module needs to connect to an installation of the Xilinx compilation tools. You can either use a local installation on this computer, an installation on a remote computer or, if entitled, the LabVIEW FPGA Compile Cloud Service. Refer to ni.com/info and enter the Info Code "XilinxCompileTools" for a list of NI hardware supported by each Xilinx compilation tool.

## Drivers for Signal Generators

### Siglent 2082X
Add drivers for Siglent SDG2082x by choosing following section at LabVIEW main menu bar - **Tools/Instrumentation/Find Instrument Drivers**. Then you can start **Scan for Instruments** if SDG2082x already connected to your PC or choose **Siglent Technologies** at **Manufacturer** and **SDG** at **Additional Keywords** and press **Search**

### Digilent Analog Discovery 2
Please install **AD2 Toolkit** from [Digilent](https://www.vipm.io/package/digilent_lib_ad2_toolkit/) or [National Instruments](https://www.ni.com/en/support/downloads/tools-network/download.analog-discovery-toolkit.html#374289) site. Please also install [Digilent WaveForms](https://digilent.com/shop/software/digilent-waveforms/).



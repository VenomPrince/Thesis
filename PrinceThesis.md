# Automated Test Environment for RIAA Amplifier with SCPI Commands, TestStand and LabVIEW

**Prince Khand Thakuri**  
Metropolia University of Applied Sciences  
Bachelor of Engineering  
Electronics Engineering  
Bachelor's Thesis  
25 May 2025  

---

## Abstract

**Author:** Prince Khand Thakuri  
**Title:** Automated Test Environment for RIAA Amplifier with SCPI Commands, TestStand and LabVIEW  
**Number of Pages:** xx pages + x appendices  
**Date:** 25 May 2025  
**Degree:** Bachelor of Engineering  
**Degree Programme:** Electronics Engineering  
**Professional Major:** Electronics Engineering  
**Supervisors:** First name Last name, Title (e.g. Project Manager)  
**Supervisors:** First name Last name, Title (e.g. Principal Lecturer)  

This thesis presents the development of an automated test environment for RIAA (Recording Industry Association of America) amplifiers using SCPI (Standard Commands for Programmable Instrumentation) commands, National Instruments TestStand, and LabVIEW. The project focuses on creating a comprehensive testing solution that can automatically control power supplies, measure output signals, and perform signal analysis including FFT (Fast Fourier Transform) to verify signal integrity and detect distortion in audio amplifier circuits.

The automated system integrates TENMA 72-13330 programmable power supply control through serial communication, oscilloscope measurements for signal analysis, and TestStand sequencing for systematic testing procedures. The implementation demonstrates how SCPI commands can be used to control test equipment without dedicated LabVIEW drivers, utilizing virtual serial port communication for instrument control.

**Keywords:** SCPI, RIAA amplifier, TestStand, LabVIEW, automated testing, FFT analysis

---

*The originality of this thesis has been checked using Turnitin Originality Check service.*

---

## Table of Contents

- [List of Abbreviations](#list-of-abbreviations)
- [1. Introduction](#1-introduction)
- [2. Theoretical Background](#2-theoretical-background)
  - [2.1 SCPI Standard and Commands](#21-scpi-standard-and-commands)
  - [2.2 RIAA Amplifier Theory](#22-riaa-amplifier-theory)
  - [2.3 Automated Test Systems](#23-automated-test-systems)
- [3. System Design and Implementation](#3-system-design-and-implementation)
  - [3.1 Hardware Setup](#31-hardware-setup)
  - [3.2 Software Development](#32-software-development)
  - [3.3 Signal Analysis and FFT Implementation](#33-signal-analysis-and-fft-implementation)
- [4. Testing and Results](#4-testing-and-results)
  - [4.1 Power Supply Control Validation](#41-power-supply-control-validation)
  - [4.2 Signal Integrity Analysis](#42-signal-integrity-analysis)
  - [4.3 Automated Test Sequence Results](#43-automated-test-sequence-results)
- [5. Discussion and Future Work](#5-discussion-and-future-work)
  - [5.1 System Performance Evaluation](#51-system-performance-evaluation)
  - [5.2 Limitations and Improvements](#52-limitations-and-improvements)
  - [5.3 Future Development Opportunities](#53-future-development-opportunities)
- [6. Conclusion](#6-conclusion)
- [References](#references)
- [Appendices](#appendices)

---

## List of Abbreviations

| Abbreviation | Description |
|--------------|-------------|
| **RIAA** | Recording Industry Association of America. Standard equalization curve for phonograph records. |
| **SCPI** | Standard Commands for Programmable Instrumentation. IEEE standard for controlling programmable test and measurement instruments. |
| **FFT** | Fast Fourier Transform. Algorithm for computing discrete Fourier transform and its inverse. |
| **TestStand** | National Instruments test management software for automated test systems. |
| **LabVIEW** | Laboratory Virtual Instrument Engineering Workbench. Graphical programming platform from National Instruments. |
| **COM** | Communication port. Serial communication interface for connecting devices. |
| **VI** | Virtual Instrument. LabVIEW program or subroutine. |

---

## 1. Introduction

The development of automated test environments for electronic circuits has become increasingly important in modern electronics manufacturing and research. This thesis focuses on creating an automated test system for RIAA amplifiers using industry-standard tools and protocols. The RIAA amplifier, essential in audio reproduction systems, requires precise testing to ensure signal fidelity and proper frequency response characteristics.

The primary objective of this project is to develop a comprehensive automated test environment that can control power supplies through SCPI commands, perform signal analysis using oscilloscope measurements, and execute systematic testing procedures through TestStand integration. The system addresses the challenge of testing audio amplifiers without dedicated instrument drivers by implementing direct SCPI communication through virtual serial ports.

The research builds upon preliminary work with TENMA 72-13330 power supply control, extending the implementation to include signal analysis capabilities and automated test sequencing. This approach demonstrates practical solutions for equipment integration in automated test environments where proprietary drivers may not be available.

---

## 2. Theoretical Background

### 2.1 SCPI Standard and Commands

The Standard Commands for Programmable Instrumentation (SCPI) defines a standard for syntax and commands to use in controlling programmable test and measurement instruments. SCPI commands provide a uniform method for controlling instruments from different manufacturers, reducing the complexity of test system development.

SCPI commands follow a hierarchical structure with a tree-like organization. Commands consist of keywords separated by colons, forming a path through the command tree. The implementation in this project utilizes SCPI commands for controlling the TENMA 72-13330 programmable power supply, which supports various output control, voltage setting, current limiting, and measurement functions.

The power supply control implementation discovered through reverse engineering includes comprehensive command sets for dual-channel operation, voltage and current stepping functions, and advanced parameter control.

#### Table 1. SCPI Command Categories for TENMA 72-13330 Power Supply

| Command Category | Function | Example Commands |
|------------------|----------|------------------|
| **Output Control** | Enable/disable channels | `OUT1:1`, `OUT2:0` |
| **Voltage Control** | Set and query voltage | `VSET1:12.0`, `VOUT1?` |
| **Current Control** | Set current limits | `ISET1:2.5`, `IOUT1?` |
| **Stepping Functions** | Automated parameter changes | `VUP1`, `VDOWN1`, `VASTEP1` |

### 2.2 RIAA Amplifier Theory

The RIAA amplifier implements the standardized equalization curve established by the Recording Industry Association of America for phonograph record reproduction. The RIAA curve compensates for the pre-emphasis applied during record cutting, providing flat frequency response in the audio reproduction chain.

The RIAA equalization curve features specific time constants that define the frequency response characteristics. The standard specifies turnover frequencies at 2122 Hz and 50 Hz, creating a high-frequency rolloff and low-frequency boost to compensate for the inverse characteristics applied during recording.

Testing RIAA amplifiers requires verification of frequency response accuracy, signal distortion levels, and proper gain characteristics across the audio spectrum. Traditional testing methods involve manual measurements at multiple frequencies, making automated testing particularly valuable for comprehensive characterization.

### 2.3 Automated Test Systems

Modern automated test systems combine hardware control, data acquisition, and analysis capabilities to provide comprehensive testing solutions. The integration of TestStand with LabVIEW creates a powerful platform for developing complex test sequences while maintaining modular software architecture.

TestStand provides test sequencing, reporting, and database connectivity features, while LabVIEW handles instrument communication and signal processing tasks. This division of responsibilities allows for efficient development and maintenance of automated test systems.

---

## 3. System Design and Implementation

### 3.1 Hardware Setup

The automated test environment consists of several key hardware components integrated through computer-controlled interfaces. The system architecture enables coordinated control of power supplies, signal generation, and measurement equipment for comprehensive RIAA amplifier testing.

#### 3.1.1 Power Supply Configuration

The TENMA 72-13330 dual-channel programmable power supply serves as the primary power source for the RIAA amplifier under test. The power supply connects to the control computer through a USB-to-serial adapter, enabling SCPI command communication through virtual COM port interfaces.

Initial configuration requires proper serial communication parameters including baud rate, data bits, stop bits, and parity settings. The power supply supports dual-channel operation with independent voltage and current control for each channel, providing flexibility for different amplifier configurations.

#### 3.1.2 RIAA Amplifier Under Test

The RIAA amplifier board represents the device under test (DUT) in the automated system. The amplifier requires proper power supply connections, input signal conditioning, and output measurement interfaces for comprehensive testing.

Signal routing considerations include input signal generation capabilities, output load conditions, and measurement point accessibility. The test setup must accommodate various amplifier configurations while maintaining signal integrity throughout the measurement process.

#### 3.1.3 Oscilloscope Integration

Oscilloscope integration provides signal analysis capabilities including waveform capture, frequency domain analysis through FFT processing, and distortion measurement functions. The oscilloscope connection enables automated signal quality verification beyond simple amplitude measurements.

The FFT analysis capability addresses the project requirement for automated signal distortion detection, replacing manual visual inspection with quantitative analysis methods. This enhancement significantly improves testing reliability and repeatability.

### 3.2 Software Development

#### 3.2.1 SCPI Command Implementation

The SCPI command implementation builds upon the reverse-engineered command set discovered during preliminary research. The LabVIEW implementation provides a comprehensive interface for power supply control including output enable/disable, voltage and current setting, and measurement functions.

**Basic SCPI Command Structure (LabVIEW VI pseudocode):**

```
// SCPI Command Structure
Open Serial Port (COM Port, Baud Rate, Parameters)
Send Command String (Command + Terminator)
If Query Command:
    Read Response (Timeout, Terminator)
    Parse Response Data
Close Serial Port
Handle Errors and Timeouts
```

The implementation includes error handling for communication failures, parameter validation for voltage and current limits, and status monitoring for proper equipment operation.

#### 3.2.2 LabVIEW Programming

The LabVIEW programming environment provides the primary interface for instrument control and data acquisition in the automated test system. The modular VI architecture enables reusable components for different testing requirements while maintaining consistent interfaces.

Key VIs include power supply control functions, signal measurement routines, and data analysis tools for FFT processing and distortion analysis. The programming approach emphasizes error handling, user interface clarity, and integration compatibility with TestStand sequences.

#### 3.2.3 TestStand Sequence Development

TestStand sequences coordinate the overall testing process, calling individual LabVIEW VIs in the proper order while managing test parameters, data logging, and result reporting. The sequence architecture provides flexibility for different test configurations and amplifier types.

The test sequence typically includes power supply setup, amplifier initialization, signal stimulus application, measurement acquisition, and results analysis phases. Each phase includes appropriate error checking and recovery procedures to ensure reliable test execution.

### 3.3 Signal Analysis and FFT Implementation

The FFT analysis implementation addresses the core requirement for automated signal quality verification. The system captures oscilloscope waveforms and processes them through FFT algorithms to identify signal distortion, harmonic content, and frequency response characteristics.

The analysis includes threshold-based detection of distortion levels, comparison with reference standards, and automated pass/fail determination based on predefined criteria. This capability eliminates subjective visual inspection while providing quantitative measurements for documentation and quality control.

---

## 4. Testing and Results

### 4.1 Power Supply Control Validation

The power supply control validation demonstrates successful implementation of SCPI commands for the TENMA 72-13330 unit. Testing verified proper operation of all discovered command functions including dual-channel control, voltage and current setting, and measurement capabilities.

Performance metrics include command response times, parameter accuracy, and communication reliability. The system demonstrates consistent operation across extended test periods with proper error handling for communication interruptions and parameter limit violations.

### 4.2 Signal Integrity Analysis

Signal integrity analysis validates the FFT implementation and automated distortion detection capabilities. Testing with known reference signals demonstrates proper frequency domain analysis and threshold-based distortion detection.

The analysis includes comparison with manual oscilloscope measurements to verify accuracy and correlation with traditional testing methods. Results show good agreement between automated measurements and manual verification, confirming the reliability of the automated approach.

### 4.3 Automated Test Sequence Results

Complete automated test sequences demonstrate the integration of power supply control, signal analysis, and TestStand coordination. The system successfully executes comprehensive RIAA amplifier testing with minimal operator intervention while providing detailed test reports and data logging.

Performance measurements include test execution time, repeatability, and error detection capabilities. The automated system significantly reduces testing time while improving measurement consistency and documentation quality.

---

## 5. Discussion and Future Work

### 5.1 System Performance Evaluation

The implemented automated test environment successfully meets the primary objectives of SCPI-based power supply control, signal analysis integration, and TestStand coordination. The system demonstrates practical solutions for equipment integration challenges while providing reliable automated testing capabilities.

Key achievements include successful reverse engineering and implementation of power supply SCPI commands, integration of FFT-based signal analysis, and development of comprehensive TestStand sequences for automated operation.

### 5.2 Limitations and Improvements

Current system limitations include dependency on specific hardware configurations, limited signal generation capabilities, and manual setup requirements for different amplifier types. Future improvements could address these limitations through enhanced hardware abstraction and configuration flexibility.

Additional enhancements might include expanded frequency response testing, temperature variation analysis, and integration with database systems for historical trending and statistical analysis.

### 5.3 Future Development Opportunities

Future development opportunities include expansion to other power supply models, integration with additional measurement instruments, and development of amplifier-specific test configurations. The modular architecture supports these extensions while maintaining compatibility with existing implementations.

Advanced features might include remote operation capabilities, web-based monitoring interfaces, and integration with manufacturing execution systems for production testing applications.

---

## 6. Conclusion

This thesis successfully demonstrates the development of an automated test environment for RIAA amplifiers using SCPI commands, TestStand, and LabVIEW. The implementation addresses practical challenges in equipment integration while providing comprehensive testing capabilities including power supply control, signal analysis, and automated test sequencing.

The project contributes practical solutions for automated test system development, particularly in situations where proprietary instrument drivers are not available. The SCPI command implementation and FFT-based signal analysis provide reliable foundations for expanded testing capabilities and future system enhancements.

The automated system significantly improves testing efficiency, measurement consistency, and documentation quality compared to manual testing methods, demonstrating the value of automation in electronic circuit testing applications.

---

## References

*[References would be formatted according to chosen citation style - Harvard or Vancouver as specified in template]*

National Instruments Corporation. TestStand User Manual. Austin, TX: National Instruments, 2024.

Institute of Electrical and Electronics Engineers. IEEE 488.2-1992 - IEEE Standard Codes, Formats, Protocols, and Common Commands for Use with IEEE Std 488.1-1987. New York: IEEE, 1992.

Recording Industry Association of America. RIAA Equalization Standard. Washington, DC: RIAA, 1954.

TENMA Test Equipment. 72-13330 Programmable DC Power Supply User Manual. Newark, NJ: TENMA, 2023.

---

## Appendices

### Appendix 1: SCPI Command Reference for TENMA 72-13330

This appendix provides the complete SCPI command reference discovered through reverse engineering of the TENMA 72-13330 programmable power supply.

#### Output Control Commands
- `OUT1:1` - Turns ON channel 1
- `OUT1:0` - Turns OFF channel 1  
- `OUT2:1` - Turns ON channel 2
- `OUT2:0` - Turns OFF channel 2
- `OUT12:0` - Turns OFF both channels

#### Voltage Control Commands
- `VSET1:<val>` - Sets voltage on channel 1
- `VSET2:<val>` - Sets voltage on channel 2
- `VOUT1?` - Queries voltage output on channel 1
- `VOUT2?` - Queries voltage output on channel 2

#### Current Control Commands
- `ISET1:<val>` - Set current limit on channel 1
- `ISET2:<val>` - Set current limit on channel 2
- `IOUT1?` - Measure output current on channel 1
- `IOUT2?` - Measure output current on channel 2

#### Advanced Stepping Commands
- `VSTEP1:<val>` - Sets voltage step size for channel 1
- `VUP1`/`VDOWN1` - Step voltage up/down on channel 1
- `VASTEP1:x,y,z,w` - Advanced stepping (start, stop, step size, interval)
- `VASTOP1` - Stop voltage stepping on CH1

#### System Commands
- `*IDN?` - Returns model info and firmware
- `*RST` - Resets the device
- `STATUS?` - Returns system status

### Appendix 2: LabVIEW VI Documentation

This appendix contains documentation for the key LabVIEW VIs developed for the automated test system, including power supply control VIs, signal analysis VIs, and TestStand integration components.

### Appendix 3: TestStand Sequence Screenshots

This appendix provides screenshots and documentation of the TestStand sequences developed for automated RIAA amplifier testing, including sequence flow diagrams and configuration parameters.
